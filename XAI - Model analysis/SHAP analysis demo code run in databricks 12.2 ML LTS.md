```
Demo code run in databricks 12.2 ML LTS
Shap version 0.41.0

import pandas as pd
import pickle
import shap
import lightgbm

print("Shap version", shap.__version__)

# Load schema :
data_path = "./xyz.parquet"
schema_path = "./xyz_schema.pkl"

with open(schema_path, 'rb') as f:
	schema = pickle.load(f)

  
# Load test data with the right data types
test_df = pd.read_parquet(data_path).astype(schema)

# Running shap analysis for bigger data set may not be feasible. For bigger datasets try : GpuTreeExplainer
test_df = test_df.head(10000) 

# Load model : 
path = "./model.txt"
model = lightgbm.Booster(model_file=path)
model.params['objective'] = "tweedie"

# Tree Explainer :
explainer = shap.TreeExplainer(model)
shap_values = explainer.shap_values(test_df)
shap_results = explainer(test_df)

# Testing if predictions and shap values match
lgbm_predict = model.predict(test_df.head(10), pred_contrib=True)
print(lgbm_predict[0,:4])
print(shap_values[0][:4])

# Bar plot :
shap.plots.bar(shap_results, max_display=20)

# Beeswarm plot :
shap.plots.beeswarm(shap_results, max_display=10)

# Force plot : 
import random
row_to_predict = random.randint(0, len(test_df))
print("Analyzing row number : ", row_to_predict)

# Display single item :

# NOTE : In order to match the model prediction with the one made in SHAP we should set the raw_score argument to True

shap_val_single_row = shap_values[row_to_predict,:].sum() + explainer.expected_value

prediction_single_row = model.predict(test_df.iloc[row_to_predict:row_to_predict+1], raw_score=True)[0]

print("Predicted volume ratio is : ", model.predict(test_df.iloc[row_to_predict:row_to_predict+1])[0])

print(f"f(x) for row {row_to_predict} (SHAP) : {(shap_val_single_row):.4f}")

print(f"Prediction for row {row_to_predict} (raw_score = True) : {(prediction_single_row):.4f}")

shap.force_plot(explainer.expected_value, shap_values[row_to_predict,:], test_df.iloc[row_to_predict,:], matplotlib=True, text_rotation=45)

import numpy as np
y_pred = model.predict(test_df)

print("Explore the 80th percentile volume ratio : ")
i_80 = np.argsort(y_pred)[int(len(y_pred)*0.8)]
shap.force_plot(explainer.expected_value, shap_values[i_80,:], test_df.iloc[i_80,:], matplotlib=True, text_rotation=45)

print("Explore the median index : ")
i_med = np.argsort(y_pred)[len(y_pred)//2]
shap.force_plot(explainer.expected_value, shap_values[i_med,:], test_df.iloc[i_med,:], matplotlib=True, text_rotation=45)

print("Explore the 20th percentile volume ratio : ")
i_40 = np.argsort(y_pred)[int(len(y_pred)*0.4)]
shap.force_plot(explainer.expected_value, shap_values[i_40,:], test_df.iloc[i_40,:], matplotlib=True, text_rotation=45)

# TODO: currently the html is downloaded from the blob storage and displayed in browser. Perhaps could be optimized

n_rows = 100 # Number of rows to display (TODO: to be parametarized)

p = shap.force_plot(explainer.expected_value, shap_values[:n_rows,:], test_df.iloc[:n_rows,:])

shap.save_html('./experimentation_sy/shap_plots/force_plot.html', p)

dbutils.fs.rm('blob_storage_path', True)
dbutils.fs.cp('dbfs_file_store_path', "blob_storage_path", recurse=True)

# NOTE : The Force plot and Waterfall differs. They should yield the same f(x).
# The force plots yields the right f(x). The same f(x) is yielded when the legacy_waterfall is used.
# print("Waterfall : ")
# shap.plots.waterfall(shap_results[row_to_predict])

  
print("Waterfall legacy version : ")
shap.plots._waterfall.waterfall_legacy(explainer.expected_value, shap_values[row_to_predict,:], test_df.iloc[row_to_predict,:], max_display=10, show=True)

# At the bottom of the plot, the observations converge at explainer.expected_value.

shap.decision_plot(explainer.expected_value, shap_values[row_to_predict],
feature_names=test_df.columns.tolist(),
highlight=0
)

# we can use shap.approximate_interactions to guess which features
# may interact with the feature in focus
inds = shap.approximate_interactions("day_of_week", shap_values, test_df)

# make plots colored by each of the top three possible interacting features
for i in range(3):
	shap.dependence_plot("day_of_week", shap_values, test_df, interaction_index=inds[i])

```

**TAGS :**
#SHAP
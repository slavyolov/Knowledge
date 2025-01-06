
Unity catalog

Loading the model with custom transformations

1. Train the model
2. Store the model into mlflow (unity catalog)
3. Predictions
	1. Load the model
		``` forecaster = mlflow.pyfunc.load_model(**f**"{self.model_path_prefix}/{self.registered_model_name}@champion")```

	2. Assign boost model attribute to DemandForecaster class_
		```self.demand_forecaster.boost_model = forecaster```

импортвам DemandForecaster, лоадвам Млфлоу модела, правя 

           

            _# Assign boost model attribute to DemandForecaster class_

            
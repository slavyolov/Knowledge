
# KModes
	- bining

- SHARE
	- work alone
	- the hardest article is the 2nd one
	- Статия 1 : Cross-sectional differences in the level of depression for elderly people in Europe
	- Статия 2 : The effect of activities as prevention tool for elderly people in Europe from depression
	
  
  **Казус : Cross-sectional differences in the level of depression for elderly people in Europe**
  
  - вълна 6  (mental health)
			- 12 questions -> EURO day index (kpi to measure depression)
			- факторен анализ 
				- два индекса (лека и тежка депресия)
		- https://bg.wikipedia.org/wiki/%D0%A4%D0%B0%D0%BA%D1%82%D0%BE%D1%80%D0%B5%D0%BD_%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D0%B7
	- Question codes :
		- ac014 (ac == module activity, question 014)
		- ac015 (ac == module activity, question 015)
	- Factor analysis
		- https://www.analyticsvidhya.com/blog/2020/10/dimensionality-reduction-using-factor-analysis-in-python/
		- https://www.analyticsvidhya.com/blog/2020/10/dimensionality-reduction-using-factor-analysis-in-python/
	- Scree plot
		- https://sanchitamangale12.medium.com/scree-plot-733ed72c8608


- x1 - xN (12 questions)
	- x1 == ac014
	- x2 == ac015
	- merch_id - id на човека, който е интервюиран
	- 1 до 5 - данните са ходирани (дори когато са дихотомни)

- като прилагаме факторен анализ трябва да си стандартизираме данните 
	- StandardScaler()
		- защото, ако имаме различни променливи тази с по-високи стойности ще окаже по-голяма тежест при определяне на теглата
		- m < p 
			- m == 2, базирано на scree plot (elbow curve)
			- p == 12, брой променливи
- Difference between PCA and factor analysis  (plus implementation in R and Python)
	- https://towardsdatascience.com/what-is-the-difference-between-pca-and-factor-analysis-5362ef6fa6f9#:~:text=Photo%20by%20Austin%20Distel%20on,in%20classes%20on%20Multivariate%20Statistics.
	- разпределението на двата фактора
	- кодиране : 5 високи стойности и 1 ниски
	 - стойност над/под О (МR1, MR2) означава, че степента на депресия е по-висока/ниска от средната
 - Какво се вижда в тези резултати ?
	 - в интерпретацията им
 - MR1 - лека депресия - отрицателни стойности означават повече депресия 
 - МR2 - тежка депресия - 

## Lecture 2 :

- DARPA
	- научни изследвания за военни цели (една от най-влиятелните институции)
	- почти всички напреднали военни технологии
	
- Driverless trains in the London tube
	- fuzzy logic (ако, то)
- Utilitarian vs Deontological
	- utilitarian -прави най-малкото зло (например убии 1 човек вместо 10)
	- deontological - никога не наранявай човешко същество
- Moral issues

- Проект Fraud Detection :
	- 1-3 slides до къде сме 
		- прогрес 
		- данни
		- проблeм
		- методология
	- интересен проблем -> процес от началото до края -> описание -> невронни мрежи -> статистика и т.н.

# Lecture 4

- полином и крива (където има чупка е на степен) -> 5 чупки => полином на 6та степен
- rule of thumb (maybe use networks up to 3th, 6th degree - polynoms)

- R^2 - мярка за определеност
	- f_черта - средна стойност
	- f_hat - предсказанието
	- R^2 - [0,1]
	- R - [-1, 1]
	- Определя най-сложния модел за най-добър, което е погрешно
		- този с най-много параметри (features)
	- Добри модели са тези, чиито параметри са много по-малко на брой от наличните наблюдения. (n >> m)
- adj R^2 
	- наказва модели, които имат повече на брой променливи спрямо броя параметри
- R^2 и adj R^2 са приблизително равни, когато броя на наблюденията е чувствително висок (например 500 хиляди или 1 милион наблюдения)
- AIC
- ! Никога няма да има единствен инструмент, който да се ползва за оценка на моделите 
- bootstrap
	- resample technique
	- https://machinelearningmastery.com/a-gentle-introduction-to-the-bootstrap-method/#:~:text=The%20bootstrap%20method%20is%20a,the%20mean%20or%20standard%20deviation.
	- 2 out of 10 and; 8 out of 10 example (combinatorics)
		- the answer is the same 45
			- n = 10 and r = 8
			- n = 10 and r = 2
			- https://www.calculatorsoup.com/calculators/discretemathematics/combinations.php
			- also valid for n = 10 and r either 6 or 4 OR r either 3 or 7
- Цел да попаднем в глобалния минимум на тестовите данни
	- голяма част от задачите в реални условия не са такива
- Академик Красимир Атанасов
	- https://biomed.bas.bg/bg/krassimir-atanassov/
	- https://biomed.bas.bg/bg/krassimir-atanassov/cv/


- Стохастична оптимизация
	- модел и данни - цел да извлечеш най-доброто от двете
	- ant colony model optimization
	- ефективността е по-малка спрямо невронните мрежи
- Simulated annealing
	- идва от металургията
	- отгряване 
		- нагряване на метала и бавно отхлаждане (безкрайно бавно с цел минимум грешки)
			- минимум вътрешни напрежения (няма да се чупи, ако го ударим)
	- минимален брой грешки/решетки
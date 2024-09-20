## taxi

Анализ временных рядов, обучение нескольких моделей для решения задачи регрессии, прогноз на один интервал вперёд с помощью лучшей модели. Библиотеки `pandas`, `numpy`, `matplotlib`, `statsmodels`, `sklearn`, `catboost`, `datetime`.  

# Прогнозирование заказов такси  

Компания «Чётенькое такси» собрала исторические данные о заказах такси в аэропортах. Чтобы привлекать больше водителей в период пиковой нагрузки, нужно спрогнозировать количество заказов такси на следующий час. Необходимо построить модель для такого предсказания.  

**Ход работы**  

1. Данные загружены, приведены к нужному формату, выполнено ресемплирование, а также проверка на пропуски.  
2. Выполнен анализ данных, в ходе которого выявлена общая тенденция роста числа заказов. Отмечена ярко выраженная сезонность в течение суток.  
3. Выявлена стационарность временного ряда, следовательно, ряд пригоден для прогнозирования.  
4. Созданы признаки: календарные признаки, отстающие значения, скользящее среднее.
5. Обучены и настроены модели `LinearRegression`, `DecisionTreeRegressor`, `CatBoostRegressor`, на кросс-валидации с использованием `TimeSeriesSplit` подобраны гиперпараметры, качество оценивалось метрикой `RMSE`.  
6. Лучшей моделью выбрана `CatBoostRegressor`, подобраны параметры признаков и гиперпараметры, величина средней ошибки модели соответствует условию заказчика.  

**Осноные выводы:** по историческим данным о количестве заказов такси построена модель, которая с учётом общего тренда и сезонности сможет предсказывать количество заказов на следующий час с требуемой точностью.
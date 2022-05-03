# Project_6  
Предсказание стоимости авто (Kaggle)  
Проект 6: "Выбираем авто выгодно."  

Ссылка на проект Kaggle: https://www.kaggle.com/code/matserams/baseline-sf-dst-car-price-prediction-v16.  
Login Kaggle: MATSERA_MS. Работу выполнил: студент DSPR-60 Мацера Максим.  
  
Цель: Предсказать цену на автомобиль по указанным объявлениям, основываясь на информации, представленной в объявлении.  

Задачи:  
EDA:  
  Анализ пропусков  
  Определение типов переменных  
  Извлекли все признаки из существующих данных  
  Дубликаты  
  Анализ Выбросов  
  Анализ взаимосвязи признаков между собой  
  Анализ взаимосвязи признаков с таргетом  
  Baseline (наивная базовая модель без ML, чтоб было от чего-то отталкиваться)  
  Выводы и идеи по генерации новых признаков  
  
 Извлечение признаков из текста (NLP):  
  Ключевые слова (поиск дилера)  
  Анализ тональности  
  Кластеризация по TF-IDF после лемматизации и стемматизации  

ML:  
  Используемые модели: kNN, Decision Tree, Extra Trees, Random Forest, Gradient Boosting, CatBoost, XGBoost, LightGBM  
  Оптимизация моделей по кросс-валидации с использованием Optuna.  
  Стекинг не повысил метрику. Подробнее в файле.  
  Чтобы не получать переобученные алгоритмы при оптимизации вводится штраф: np.mean(np.abs(mape_valid - mape_train))  
  Вследствие этого, находятся более стабильные алгоритмы, которые не так сильно учитывают шумы в данных.   
  Проблема в том, что лучшие решения на кагле скорее учитывают эти шумы как на обучающей, так и на тестовой выборках, отчего у них выше Score.  
  Проанализированы ошибки алгоритма на CatBoost.  
  
У меня не стояло задачи получить лучшую метрику в лидерборде. Проект исследовательский с задачей получения СТАБИЛЬНОЙ модели.  

ВАЖНАЯ ИНФОРМАЦИЯ:  

Код на Kaggle зачищен из-за импорта (его запускать слишком долго), смотреть только на GitHub. Ноутбук не откроется, поэтому придётся его скачать.  
Подгрузить pickle данные не представляется возможным из-за ограничения GitHub.  

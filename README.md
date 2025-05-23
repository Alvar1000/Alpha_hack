# Alpha_hack
Цель: Создать автоматизированное решение, которое 
позволит Альфа-Банку оценить кредитоспособность 
юридических лиц. Нужно данные             
с результатами кредитного скоринга, обучить модель      
и оцените качество модели и ее предсказаний 
по метрике roc-auc

## Описание решения
Это решение для задачи кредитного скоринга, предсказывающее вероятность дефолта заемщика. Модель достигла ROC-AUC 81.47, что близко к топ-3 результату (81.5) в соревновании.

### Основные компоненты
#### Алгоритм
- Используется градиентный бустинг на деревьях (LightGBM)
- Реализован метод Out-of-Fold (OOF) для кросс-валидации
- 10-кратная кросс-валидация с перемешиванием
#### Особенности реализации
- Ранняя остановка (200 раундов) для предотвращения переобучени
- Оптимизированные гиперпараметры модели, подобранные с помощью Optuna
- Предсказание вероятностей (а не бинарных классов)
- Усреднение предсказаний по всем фолдам
- Итоговый сабмит являлся ансамблем из XGBoost и LGBM
  
В какой-то момент держали топ1, но в итоге 8 место.

![photo_2024-11-03_02-45-21](https://github.com/user-attachments/assets/4e9014e2-f67d-46d7-9729-02910a875dc4)

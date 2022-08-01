## sber_housing_market

***Учебный проект с курса START ML школы Karpov.Courses***

Предсказание стоимости квартир из датасета Sberbank Russian Housing Market с [Kaggle](https://www.kaggle.com/competitions/sberbank-russian-housing-market/overview)

![img](https://sun9-85.userapi.com/impg/m--I02pUGPhRNqCQmfFC4443qqGmIJ0FBZIOUA/X8-HsMIm0NU.jpg?size=1403x346&quality=95&sign=b77540d88d0a5c229ace2bd123304dcd&type=album)

### **Описание датасета:**

- price_doc: sale price (this is the target variable)
- id: transaction id
- timestamp: date of transaction
- full_sq: total area in square meters, including loggias, balconies and other non-residential areas
- life_sq: living area in square meters, excluding loggias, balconies and other non-residential areas
- floor: for apartments, floor of the building
- max_floor: number of floors in the building
- material: wall material
- build_year: year built
- num_room: number of living rooms
- kitch_sq: kitchen area
- state: apartment condition
- product_type: owner-occupier purchase or investment
- sub_area: name of the district

> ***В соревновании использовалась несимметричная метрика RMSLE. По факту, это корень от MSLE, поэтому для упрощения расчетов я оптимизировала MSLE.***

### Содержание Jupiter-ноутбука [sber_housing_market.ipynb](sber_housing_market.ipynb):

1. Заполнение пропусков, проверка данных на констанстность и мультиколлинеарность.
Кодирование категориальных признаков
3. EDA - первичный анализ данных и визуализация
4. Обучение и TimeSeriesSplit-валидация моделей Линейной, Ridge и Lasso регрессии. Расчет MSLE
5. Сегментация и построение разных моделей для двух групп квартир из признака `product_type_OwnerOccupier`.
`product_type_OwnerOccupier` - бинарный признак, который показывает на первичном или вторичном рынке продается квартира.
6. Расчет взвешенной MSLE с учетом количества объектовв обоих типах жилья

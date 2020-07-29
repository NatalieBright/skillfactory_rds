![Title PNG "Skill Factory"](/GitHub_image/img_title.png)
# Проект №3. Выбираем авто выгодно.

# Задача

Создать модель, которая будет предсказывать стоимость автомобиля по его характеристикам.

**О данных**

Есть небольшой датасет с историей продаж. Для обучения модели этих данных недостаточно, поэтому они будут использоваться для теста. 
Остальные данные необходимо собрать самостоятельно.

# Этапы работы

## Сбор данных

Данные были собраны с трех источников:

- [auto.ru](https://auto.ru/)
- [avito.ru](https://www.avito.ru/rossiya)
- [drom.ru](https://www.drom.ru/)

В общей сложности было собрано около 16 тыс. объявлений. После обработки и всех манипуляций с данными, для построения модели было использованно около 10 тыс. объявлений.

**Датасеты**:

- ["cars_2.csv" auto.ru](https://drive.google.com/file/d/11F1v64GOFRHoGbDqLlEK0efSSaeOpT-O/view?usp=sharing)
- ["cars_avito.csv" avito.ru](https://drive.google.com/file/d/1FM3uSwAV4RXhJNNYLS9BnPpiwuw5n6ZS/view?usp=sharing)
- ["drom_cars.csv" drom.ru](https://drive.google.com/file/d/1nsHbwdbdrNxy9hPLw3YycMkenXwn8XT6/view?usp=sharing)

**Очищенный тестовый датасет**:

- ["cleaned_test.csv"](https://drive.google.com/file/d/15Drgy26XmSwH81p_abzbLm2Lqb2UsOjr/view?usp=sharing)

Данные датасеты использовались для обработки.

**Ноутбуки (папка Parsing)**:

- `parse_auto_ru.ipynb` - парсинг с сайта auto.ru
- `autoru_car_data_concat.ipynb` - доп. ноутбук для объединения данных собранных с auto.ru
- `autoru_data_preprocessing.ipynb` - первичная обратка данных c auto.ru
- `Parse_drom.ru_data.ipynb` - парсинг с сайта drom.ru
- `Parsing_avito(cars).ipynb` - парсинг с сайта avito.ru

## Подготовка данных

При первичной обработки данных все датасеты были объеденны в один датасет привидены к общему виду. Удалены пропуски и дубликаты. Добавлены новые признаки. Обработка предствленна в ноутбуке `united_dataset_3.ipynb` (папка Preprocessing).

- [united_3.csv](https://drive.google.com/file/d/1xH6KSIwfhgvE65ElrFMuXDzvVeUt-DRl/view?usp=sharing)

После объединения в общий датасет данные были еще раз обработаны. Уменьшено количиство уникальных значений для категориальных признаков там где это было возможно. После обработки получили новый датасет, который использовали при построении CatBoost модели:

Ноутбок:

- `united_eda.ipynb`

Датасет:

- [cars_new.csv](https://drive.google.com/file/d/1lkRG8V6O6TAVUZOEH0IXBZZw3jxig38a/view?usp=sharing)

## Построение моделей

### CatBoost

Ноутбук с моделью (папка Modeling):

- `catboost_model.ipynb`

При построении модели были подобраны оптимальные параметры с помощью метода `grid_search()` и ручного перебора. Так же была реализована кросс-валидация, которая помогла улучшить результат приблизительно на 1%. Итоговый результат модели на каггле **12.08%**.

Файл с результатом:

- [submission_blend_v2.csv](https://drive.google.com/file/d/151ZhZS1WG4q_XKGi0B_K_b7aUxAwsslR/view?usp=sharing)

### Stacking

Ноутбук с моделью (папка Modeling):

- `stacking_model.ipynb`

Для построения модели stacking использовали модели Random Forest, Bagging и CatBoost. Лучший результат **14.8%**.

Файл с результатом:

- [submission_stack_v1.csv](https://drive.google.com/file/d/1lZyVqpOKWP8Lpbf9n4ele54E8Qi5Jfhh/view?usp=sharing)

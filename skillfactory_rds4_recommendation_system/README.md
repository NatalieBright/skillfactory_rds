Основные цели и задачи проекта:
1 По известным оценкам товаров предсказать, какую оценку поставит пользователь новому для него товару
2 Дать рекомендации товаров пользователю

Краткая информация о данных:
Были даны 2 датасета: тренировочный с изветными рейтингами товаров, и тестовый, на котором рейтинг товаров необходимо было предстказать.
Оценки были даны по 5 бальной шкале, также в дата сете были данны по тексту отзыва, времени отзыва, верификации и голосованию за отзыв других пользователей (формат csv).
Также представлен файл с характеристиками товаров в формате json

Этапы работы над проектом:
1. Анализ и разведывательный анализ данных, создание новых признаков
2. Построение базовой модели из Baseline
3. Подбор параметров модели, регуляризация, добавление признаков товаров
4. Создание прототипа (рекомендации товаров по эмбеддингам)
	
Ваш никнейм на Kaggle: https://www.kaggle.com/natalievold

В описании ответьте на вопросы:

1. Какова была ваша роль в команде? Кратко опишите, что именно вы сделали в рамках командного проекта.
 - индивидуальный проект

2. Как вы оцениваете свой вклад в командную работу?
 -

3. Какой частью своей работы вы остались особенно довольны?
 - Получила значение метрики ROC AUC выше Baseline, смогла несколько раз улучшить результат.

4. Что не получилось сделать так, как хотелось? Над чем ещё стоит поработать?
 - было тяжело разобраться, как работать с item_features
 - создание прототипа требует закрепления материала. Модель, приведенная в примере, разительно отдичается от того, что нужно было сделать в проекте
 - непонятен момент с влиянием на скор параметров модели и добавления features. Получается, что на каггл
   самый лучший скор дала базовая модель без какого-либо тюнинга
 - нужно будет еще поработать с отзывами как с текстом (не хватило времени)


5. Что интересного и полезного вы узнали в этом модуле?
 - разобралась с созданием рекомендательной системы, многие адгоритмы подбора рекомендаций стали понятнее.

6. Что является вашим главным результатом при прохождении этого проекта?
 - создание работающей рекомендательной системы.
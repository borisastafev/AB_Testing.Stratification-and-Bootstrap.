# AB-testing-Bootstrap
# Основные даннные взяты с https://www.kaggle.com/datasets/zhangluyuan/ab-testing.

Данный дата-сет содержит наблюдения для контрольной группы(пользователям, которым был предложен старый дизайн сайта) и тестовая(которым доступен новый дизайн)
Также есть данные по конверсии для каждой из групп (какое-либо целевое действие), данные о времени эксперимента(он длится 22 дня).
Чтобы было больше данных для анализа метрик и применения различных иструментов при аб-тестировании - я  смоделировал данные о первой покупке для каждой группы пользователей. Данные имеют нормальное рапределение и у тестовой группы немного больше мат.ожидание этой величины(цены первой покупки).

# Дизайн АБ-теста:
 - Оценивать будем следующие метрики: конверсия (что нам уже дано) и средний чек (то, что я смоделирую)
 - Для конверсии я буду использовать Хи-квадрат в качестве стат.критерия(так как конверсия имеет биномиальное распределение), для среднего чего буду использовать Bootstrap
 - уровень значимости для этих метрик буду использвать 0.01
 - будем исходить из предположения, что контрольная и тестовая группы имеют равномерномерное распределение в данном рассматриваемом сегменте

# Посмотрим, что из этого вышло..

 

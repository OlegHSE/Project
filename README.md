# Проект
## План
- `Шаг 1.` Выбор темы
- `Шаг 2.` Сбор данных и Предварительная обработка
- `Шаг 3.` Визуализация и Гипотезы
- `Шаг 4.` Создание новых признаков
- `Шаг 5.` Машинное обучение
## Команда
- Черников Олег
- Землякова Анна
- Фирстова Мария

## Шаг 1. Выбор темы
Мы выбрали датасет "Employee Turnover", на основе которого мы бы хотели выявить основные факторы, кторые влияют на решение работника об уходе из компании. В настоящее время данная тема является актуальной для любого предприятия, так как работодателям всегда важно анализировать ситуацию на рынке труда и находить оптимальные условия труда для снижения уровня текучести кадров.  
## Шаг 2. Сбор данных и Предварительная обработка
Данный датасет мы взяли с сайта kaggle. База данных принадлежит крупной американской компании, отдел кадров которой собрал данные о почти 10 000 сотрудниках, которые покинули компанию в период с 2016 по 2020 год. Они использовали информацию из собеседований, обзоров эффективности и записей сотрудников.
__Описание переменных:__
- `department` - отдел, к которому принадлежит сотрудник.
- `promoted` - 1, если работник был повышен в должности в предыдущие 24 месяца, 0 в противном случае.
- `review` - совокупная оценка, которую сотрудник получил в результате последней оценки его производительности.
- `projects` - в скольких проектах участвует сотрудник.
- `salary` - по соображениям конфиденциальности заработная плата выходит на три уровня: низкая, средняя, высокая.
- `tenure` - сколько лет сотрудник работает в компании.
- `satisfaction` - мера удовлетворенности сотрудников по результатам опросов.
- `bonus` - 1, если сотрудник получил премию за предыдущие 24 месяца, 0 в противном случае.
- `avg_hrs_month` - среднее количество часов, которое сотрудник работал в месяц.
- `left` - "да", если сотрудник в конечном итоге ушел, "нет" в противном случае.

__Целевая переменная:__
`left` - будем предсказывать уход работника с места занятости. Бинарный признак, принимает значение 0, если работник остался, 1, если он ушел. 
## Шаг 3. Визуализация и  Гипотезы
> Визуализация полностью выполнена в тетрадке.

Мы бы хотели проверить следующие гипотезы:
- Сотрудники, которые ушли, составляют 30% от общего количества сотрудников. 
- Медианы по переменной `avg_hrs_month` у людей, которые ушли, и у тех, что остались,равны. 
- В департаментах одинаково повышали и тех,кто ушел, и тех, кто остался работать. 
- Решившие уйти в среднем прорабатывали в компании столько же лет, как и оставшиеся, против альтернативной гипотезы о том, что оставшиеся работают в компании дольше.
- Ушедшие в среднем получали столько же бонусов, сколько и те, что остались. 
- По всем департаментам люди, которые по итогу уволились, и те, кто остались, получили в среднем одинаковые оценки за `review`.
## Шаг 4. Создание нового признака
На этом этапе мы решили создать новый признак с помощью метода ближайших соседей, который будет выражать вероятность того, что сотрудник уволится. 
- `leaving_score` - вероятность ухода сотрудника. 
## Шаг 5. Машинное обучение
Мы бы хотели получить предсказание нашей целевой переменной с помощью следующих моделей: Случайный Лес (RandomForest), Логистическая регрессия(Logistic Regression).

Подводя итоги нашей работы, мы бы хотели посмотреть на важность признаков, влияющих на уход сотрудников, с помощью 2 способов - "снижение Джини", "снижение точности". 

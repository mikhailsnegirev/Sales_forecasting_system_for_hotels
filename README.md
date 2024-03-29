# Система прогнозирования продаж для отелей
## Описание проекта и цель<br>
Строится модель прогнозирования отказа от брони клиента. В качестве метрики используем величину выручки которая получится после внедрения модели машинного обучения. Необходимо спрогнозировать кто из клиентов откажется от брони.



## Инструменты
`предобработка данных`
`Python`
`Pandas`
`Matplotlib`
`numpy`
`исследовательский анализ данных`
`машинное обучение`
`бизнес-модели`


## Вывод
**Вычисление бизнес-метрики:**
- Оценили прибыль отеля без внедрения депозитов

**Создали функцию для расчета доходности бронирования:**

- Расчет сезонного коэффициента: В зависимости от месяца заезда, определяется коэффициент сезонности, который влияет на цену номера.
- Расчет стоимости номера: Используются данные о типе зарезервированного номера, общем количестве ночей и сезонном коэффициенте для определения стоимости проживания.
- Расчет затрат на обслуживание: Затраты на уборку вычисляются в зависимости от количества ночей проживания и типа номера.
- Расчет затрат при отмене бронирования: Если бронь была отменена (is_canceled == 1), то учитывается убыток от отмены бронирования, который включает стоимость одной уборки и одной ночи с учетом сезонного коэффициента.
- Применение функции к данным Функция calculate_income применяется к каждой записи (строке) в DataFrame hotel_train и hotel_test, чтобы рассчитать доходность бронирования и записать результат в новый столбец income.

Этот код позволил оценить доходность отдельных бронирований, учитывая различные факторы, такие как тип номера, длительность проживания, сезонные изменения цен и статус отмены брони.

**Разработка модели ML:**
- Обучили разные модели и оценили их качество. 
- Описали выводы. 
- Но в контексте представленных метрик и показателей, модель RandomForestClassifier выделяется на фоне других вариантов. Её способность обеспечить  высокую точность (Accuracy) и уровень F1-меры указывают на хороший баланс между точностью и полнотой предсказаний. Особенно важно отметить величины TN (True Negative) и TP (True Positive), которые представляют собой количество правильно определенных объектов отрицательного и положительного классов соответственно. Также Precision и Recall подчеркивают, что модель способна делать достаточно точные и полные прогнозы относительно различных классов. Но самым весомым аспектом является и прибыль, которая модель RandomForestClassifier обещает принести. Её способность прогнозировать прибыль достигает 36 779 280, что делает её очень привлекательным вариантом для бизнеса. С учётом всех этих факторов, можно с уверенностью утверждать, что RandomForestClassifier представляет собой оптимальное и сбалансированное решение для задачи прогнозирования в данном контексте.

**Выявление признаков «ненадёжного» клиента:**
- На основе исследовательского анализа данных описали клиента, склонного к отказу от брони: клиенты, останавливающиеся в отеле впервые, реже вносящие изменения в бронь, небронирующие места для машины, неделающие специальных запросов и часто бронирующие номера задолго до поездки более склонны к отменам и могут считаться менее "надежными".


Модели машинного обучения имеют огромное значение для бизнеса. Они позволяют компаниям анализировать большие объемы данных для выявления закономерностей и предсказания будущих тенденций. Это помогает оптимизировать процессы, улучшить прогнозы спроса, повысить эффективность производства и снизить издержки.

Модели машинного обучения также способны автоматизировать рутинные задачи, что позволяет сотрудникам сосредоточиться на более стратегически важных задачах. 

Использование моделей машинного обучения также позволяет нализировать риски и улучшать процессы принятия решений на основе данных. В целом, они играют ключевую роль в повышении конкурентоспособности компаний и помогают им адаптироваться к быстро меняющейся бизнес-среде.



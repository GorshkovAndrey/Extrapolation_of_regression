### Extrapolation_of_regression

### Использование информации о погрешности измерения переменных для достоверной экстраполяции регрессии
### Автор: Горшков Андрей Вячеславович
------------------------------------------

Рассмотрена задача экстраполяции регрессии, предикторы и целевая переменная которой заданы с некоторыми погрешностями измерений. При этом все предикторы являются, практически, мультиколлинеарными.

На сгенерированных учебных наборах данных обучены различные модели регрессоров из библиотеки scikit-learn и модель регуляризации Тихонова, коэффициент регуляризации которой определяется по условию оптимизации нестандартной метрики – обобщенной невязки, которая учитывает информацию о погрешности измерения предикторов и целевой переменной.

Несмотря на отличные метрики (R2 ≈ 1) всех моделей регрессоров из библиотеки scikit-learn, результаты их прогнозов не только имеют неприемлемую точность, но и сильно отличаются друг от друга, то есть являются неустойчивыми, в результате чего небольшие погрешности измерений данных приводят к недопустимым погрешностям прогноза целевых переменных. При этом модель регуляризации Тихонова, учитывающая погрешности измерения предикторов и целевой переменной, выдает устойчивое решение с приемлемой точностью. Так в данной задаче погрешность осредненного прогноза различных моделей регрессоров из библиотеки scikit-learn составила от -33% до 48%, тогда как погрешность прогноза модели регуляризации Тихонова составила 8%.

Выводы:
1. Игнорирование даже незначительной погрешности измерения предикторов и целевой переменной может привести к крайне большой погрешности прогноза экстраполяции.

2. Модели с мультиколлинеарными предикторами могут привести к неустойчивым прогнозам экстраполяции с недопустимой погрешностью.

3. Для моделей с мультиколлинеарными предикторами для получения устойчивого прогноза экстраполяции с допустимой погрешностью следует использовать регуляризацию с учетом информации о погрешности измерения предикторов и целевой переменной.

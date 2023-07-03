### Extrapolation_of_regression

### Горшков Андрей Вячеславович
### Повышение точности экстраполяции регрессии путем учета погрешности измерения переменных
------------------------------------------

Рассмотрена задача экстраполяции регрессии для наборов данных с практически абсолютной мультиколлинеарностью всех предикторов. Предполагается, что предикторы и целевая переменная заданы с некоторыми известными погрешностями измерений.

На сгенерированных наборах данных обучены различные модели регрессоров из библиотеки scikit-learn и модель регуляризации Тихонова, коэффициент регуляризации которой определяется по условию оптимизации нестандартной (для scikit-learn) метрики – обобщенной невязки, учитывающей информацию о погрешности измерения предикторов и целевой переменной.

Несмотря на отличные метрики (R2 ≈ 1) всех обученных моделей регрессоров из библиотеки scikit-learn, результаты их прогнозов не только имеют неприемлемую точность, но и являются неустойчивыми – небольшие погрешности измерений данных приводят к недопустимым погрешностям прогноза целевой переменной. При этом модель регуляризации Тихонова, учитывающая погрешности измерения предикторов и целевой переменной, выдает устойчивый прогноз с приемлемой точностью. Так в данной задаче погрешность осредненного прогноза различных моделей регрессоров из библиотеки scikit-learn составила от -33% до 48%, тогда как погрешность прогноза модели регуляризации Тихонова составила 8%.

Выводы:
1. Игнорирование даже незначительной погрешности измерения предикторов и целевой переменной может привести к крайне большой погрешности прогноза экстраполяции.

2. Модели, обученные на наборах данных с мультиколлинеарными предикторами по условию оптимизации стандартных метрик из библиотеки scikit-learn, могут привести к неустойчивым прогнозам экстраполяции с недопустимой погрешностью.

3. Для моделей, обучаемых на наборах данных с мультиколлинеарными предикторами, для получения устойчивого прогноза экстраполяции с допустимой погрешностью следует использовать регуляризацию с учетом погрешности измерения предикторов и целевой переменной.

# Заметки с PyCon.DE 2018

Расписание: https://de.pycon.org/schedule/

Видео всех докладов: https://administraitor.video/edition/PyCon.DE/2018

## Все посещенные доклады <a name="content"></a>
Первый день
1. [Quantum Computing](#quantum-computing)
1. [Germany's next topic model](#germany-s-next-topic-model)
1. [Cython to speed up your Python code](#cython)
1. [Active Learning](#active-learning)
1. [A Day Has Only 24±1 Hours](#timezones)
1. [Productionizing your ML code seamlessly (Yelp)](#prod_ml)
1. [How type annotations make your code better](#type_annotations)
1. [Lightning talks](#lightning1)

Второй день
1. [Keynote: Wes McKinney (создатель pandas)](#keynote_pandas)
1. [Deep Learning with PyTorch for more Fun and Profit (Part II)](#hendorf)
1. [Reproducibility, and Selection Bias in Machine Learning](#reproducibility)
1. [Data science complexity and solutions in real industrial projects](#industrial)
1. [PyTorch as a scientific computing library: past, present and future](#pytorch)
1. [Processing Geodata using Python](#geodata)
1. [Put your data on a map](#data_on_map)
1. [Observe all your applications](#observe)
1. [Where the heck is my memory](#memory)
1. [Lightning talks](#lightning2)

Третий день
1. [Keynote: Emmanuelle Gouillart](#keynote_skimage)
1. [Strongly typed datasets in a weakly typed world](#typed_datasets)
1. [Satellite data is for everyone](#sattelites)
1. [Python Decorators: Gift or Poison](#decorators)

[Спринты и воркшоп PyLadies](#sprints)

## Introduction and practical experience about Quantum Computing using the Python libraries from IBM and Google <a name="quantum-computing"></a>
Описание: https://de.pycon.org/schedule/talks/introduction-and-practical-experience-about-quantum-computing-using-the-python-libraries-from-ibm-and-google/

Видео: https://www.youtube.com/watch?v=dDPSmTGVvZE&feature=youtu.be

![](images/PyCon.DE_2018/photo_2018-11-07_15-38-14.jpg)
![](images/PyCon.DE_2018/photo_2018-11-07_15-38-15.jpg)
Мотивация: симуляция физических процессов должна быть согласована с их квантовой природой

![](images/PyCon.DE_2018/photo_2018-11-07_15-38-17.jpg)
Немного истории

![](images/PyCon.DE_2018/photo_2018-11-07_15-38-18.jpg)
![](images/PyCon.DE_2018/photo_2018-11-07_15-38-19.jpg)
Как можно использовать квантовые эффекты для с создания кубитов (для хранения информации в квантовом компьютере)

![](images/PyCon.DE_2018/photo_2018-11-07_15-38-20.jpg)
Технологические вызовы: охлаждение (для уменьшения шума), связи между кубитами

![](images/PyCon.DE_2018/photo_2018-11-07_15-38-21.jpg)
Сегодня: десятки кубитов

![](images/PyCon.DE_2018/photo_2018-11-07_15-38-22.jpg)
Сравнение с классическим подходом. Не для буквальных вычислений, но для аппроксимаций

![](images/PyCon.DE_2018/photo_2018-11-07_15-38-23.jpg)
Инфраструктура, симуляторы. Есть собранные контейнеры

![](images/PyCon.DE_2018/photo_2018-11-07_15-38-24.jpg)
Как использовать

![](images/PyCon.DE_2018/photo_2018-11-07_15-38-26.jpg)
В общем, был такой вводный доклад про квантовые вычисления, с небольшими примерами кода. Нужно глубокое понимание математики и физики для использования

[Наверх к оглавлению](#content)

## Germany's next topic model <a name="germany-s-next-topic-model"></a>
Описание: https://de.pycon.org/schedule/talks/germany-s-next-topic-model/

Видео: https://youtu.be/sI7VpFNiy_I

![](images/PyCon.DE_2018/photo_2018-11-08_18-48-44.jpg)
Доклад про выявление топиков в текстах путем представления слов как графа с некоторой метрикой близости по смыслу и выделения в этом графе кластеров-тем

![](images/PyCon.DE_2018/photo_2018-11-08_18-48-45.jpg)
![](images/PyCon.DE_2018/photo_2018-11-08_18-48-47.jpg)
![](images/PyCon.DE_2018/photo_2018-11-08_18-48-48.jpg)
![](images/PyCon.DE_2018/photo_2018-11-08_18-48-49.jpg)

Как используют в HolidayCheck (немецкий агрегатор отелей): 
* Разбиение отелей по похожести отзывов - видны кластеры пляжного отдыха, hiking, ..
* Автоматические ответы на вопросы типа "есть ли телевидение на немецком?" без необходимости в совпадении лексики

Строят матрицу близости слов, далее:
* Стандартный подход неявно предполагает, что темы распределены по документам, но в случае отзывов на отели дают один большой кластер "отзыв на отель"
* Используются infomap community detection алгоритмы (говорит, практически как кластеризация для графов, только для сетей)

![](images/PyCon.DE_2018/photo_2018-11-08_18-48-50.jpg)
Обзор их решения
Чтобы не ставить ограничение "одно слово в одной теме", используются fuzzy models

![](images/PyCon.DE_2018/photo_2018-11-08_18-48-51.jpg)
Тут должна быть классная визуализация сети слов с выделенными communities

[Наверх к оглавлению](#content)

## Cython to speed up your Python code <a name="cython"></a>

Описание: https://de.pycon.org/schedule/talks/cython-to-speed-up-your-python-code/

Видео: https://youtu.be/zx0wMxuh-wk (доклад переаписывали из-за проблем с оборудованием во время первой попытки)

![](images/PyCon.DE_2018/photo_2018-11-08_18-48-53.jpg)
![](images/PyCon.DE_2018/photo_2018-11-08_18-48-55.jpg)
Небольшое введение про проект trustyou.com (?) и разнообразие использующихся там питоньих тулз

![](images/PyCon.DE_2018/photo_2018-11-08_18-48-56.jpg)
Используют для текстов NLTK и хотят сделать его быстрее (спойлер: ускорили на 30%)

Сейчас рассказывает введение в cython с объяснениями, как устроено взаимодействие между питоном и си. Возможно, потом выложат тетрадку с разъяснениями, пока ни слайдов, ни других материалов в свободном доступе нет.

Ещё пример: ускорение difflib, диффилки из стандартной библиотеки питона, причем про последовательности ничего не знаем
* Просто перекомпиляция под cython 50->36 секунд на замеры бенчмарка
* Указание типов вспомогательных переменных: 36->31 секунд
* Можно смотреть разметку "эта строчка уже совсем сишная, а эта ещё питонья" и думать, как улучшать дальше

[Наверх к оглавлению](#content)


## Active Learning - Building Semi-supervised Classifiers when Labeled Data is not Available <a name="active-learning"></a>
Описание: https://de.pycon.org/schedule/talks/active-learning-building-semi-supervised-classifiers-when-labeled-data-is-not-available/

Видео: https://youtu.be/0efyjq5rWS4

![](images/PyCon.DE_2018/photo_2018-11-08_18-48-58.jpg)
Слайды к этому докладу и ещё паре от той же компании есть здесь: https://github.com/rosen-group/conferences/tree/master/PyConDE/2018
Компания предоставляет сервис диагностики всяких сложных систем (на стенде показывают свою железку для проверки труб)

Основной вопрос: как выбирать данные, требующие разметки человеком, так, чтобы получить наилучшую точность, потратив на разметку по возможности меньше усилий
* Брать для разметки случайные объекты - бейзлайн
* cluster homogenity: кластеризовать неразмеченные данные, брать объекты из кластеров равномерно/пропорционально/... (больше про exploration)
* uncertainty sampling: брать объекты, про которые классификатор наименее уверен в их классе (больше про explotation). Есть риск сконцентрироваться на выбросах
* query-by-committee: натренировать несколько классификаторов, брать объекты, где они больше всего несогласны
* expected model change: считаем по всем классам, какова вероятность, что разметка объекта этим классом изменит наш классификатор, берём объект с наибольшим ожиданием
* expected error reduction: аналогично предыдущему, но по уменьшению ошибки классификатора
Чем дальше, тем больше сложностей с вычислением
Какой выбрать - все) холодный старт - первые, дальше комбинировать, тестировать

Как тестировать - взять полностью размеченный датасет и симулировать онлайн-работу

Когда остановиться? Закончились деньги, модель сошлась, любой другой критерий
Они используют tsne для визуализации, смотрят глазами, что классы устаканились

В конце ссылки на python-пакеты по теме (один слайд про питон, круто)

Лектора спрашивают, когда, по его мнению, можно будет отказаться от разметки людьми. Ответ - мы обязаны использовать ручную разметку по закону :flushed: Но вообще перспективы хорошие - те же ганы

Говорит, поверх алгоритмов выбора можно навернуть ещё один алгоритм выбора, который бы по прежнему перформансу выбирал алгоритм для текущей итерации

![](images/PyCon.DE_2018/photo_2018-11-08_18-49-01.jpg)

Техника для проверки труб от компании, делавшей предыдущий доклад. Двигается со скоростью 2-5 метров в секунду, внутри начинка из десятков сенсоров

[Наверх к оглавлению](#content)



## A Day Has Only 24±1 Hours: import pytz <a name="timezones"></a>
Описание: https://de.pycon.org/schedule/talks/a-day-has-only-241-hours-import-pytz/

Видео: https://youtu.be/IRGKlwkio0Y

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-23.jpg)
Теперь доклад про таймзоны

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-24.jpg)
Боль-1 на картинке
Боль-2: повторные запросы текущего времени могут привести к неожиданным проблемам (смена суток, перевод часов)

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-25.jpg)
Текущие таймзоны в мире (больше 400!)

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-28.jpg)
Смена таймзон отдельных точек по географии с годами (по y - отклонения от Гринвича). Зигзаги - переход на зимнее/летнее время. Вертикальные линии - "прыгающие" между государствами острова

Очень прикольный доклад, он наверняка есть в записи, посмотрите. Поддержка tzdata ведется через почтовую рассылку, куда все могут прислать инфу типа "в местной газете написали, что страна N переходит на такое время" или "прилетел в страну M, а тут явно не та таймзона, как мы думали"

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-29.jpg)

[Наверх к оглавлению](#content)



## Productionizing your ML code seamlessly <a name="prod_ml"></a>
Описание: https://de.pycon.org/schedule/talks/productionizing-your-ml-code-seamlessly/

Видео: https://youtu.be/M0A8GaT5qns

Следующий доклад: productionizing your code seamlessely от ребят из yelp. Зал переполнен :)

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-31.jpg)

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-32.jpg)
Общий вид

Подробнее по пунктам:
* Data source. Данные могут обновляться
* Training data. Как часто тренировать модель? Нужна стратегия на случай падений. Масштабирование?
* Evaluation. Согласованность с продакшеном, классическая метрика + взгляд со стороны бизнеса, учитывать feedback loops. Хорошо проверять дополнительно на фиксированном датасете
* Predictions: падения, масштабирование, как и для обучения. Также вопрос использования предсказаний:
* Measuring success. Чекать бизнес-метрики, которые пытаемся двигать. АБТ. (Особенно в случае рекомендаций) надо проверять, что нет смещения в сторону положительных случаев - мб пользователь и без модели создал бы аккаунт / сделал что-то хорошее.

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-33.jpg)
Общие советы

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-34.jpg)
Вычисление фичей и обработка данных должны быть одинаковым при обучении и применении (🙄)

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-34%20(2).jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-16-35.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-16-36.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-16-37.jpg)

[Наверх к оглавлению](#content)



## How type annotations make your code better <a name="type_annotations"></a>
Описание: https://de.pycon.org/schedule/talks/how-type-annotations-make-your-code-better/

Видео: https://youtu.be/hHxZkdDA-l0


![](images/PyCon.DE_2018/photo_2018-11-14_12-16-38.jpg)
Agenda: maintanability, predictability, developer expirience, toolset

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-39.jpg)
Про maintainability

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-40.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-16-42.jpg)
Заодно рефакторинг

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-42%20(2).jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-16-43.jpg)
Вспомогательные штуки для используемых библиотек

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-44.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-16-45.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-16-46.jpg)
Кроме очевидных преимуществ также стимуляция к хорошим паттернам

Developer experience: базовая документация на виду, редактор всё подсказывает. Тесты всё ещё нужны, но меняется уровень рассмотрения проблем

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-46%20(2).jpg)
Тулы

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-47.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-16-48.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-16-49.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-16-50.jpg)

[Наверх к оглавлению](#content)



## Lightning talks <a name="lightning1"></a>
Описание: список тем ниже

Видео: можно найти по названию здесь https://administraitor.video/edition/PyCon.DE/2018

![](images/PyCon.DE_2018/photo_2018-11-14_12-16-51.jpg)

[Наверх к оглавлению](#content)



## Keynote: Wes McKinney (создатель pandas) <a name="keynote_pandas"></a>
Описание: https://de.pycon.org/blog/pyconde-and-pydata-karlsruhe-2018-keynote-wes-mckinney/

Видео: https://youtu.be/uETG3bn4kow

![](images/PyCon.DE_2018/photo_2018-11-14_12-51-44.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-51-45.jpg)
Долгое вступление про мотивацию и пользу анализа данных для мира закончилось экзистенциальными кризисами о_О

Я немного потерялась в докладе дальше, Вес рассказывал про историю того, как он начал делать pandas, какие сложности у них есть, и как он логически пришел к apache arrow

[Наверх к оглавлению](#content)



## Deep Learning with PyTorch for more Fun and Profit (Part II) <a name="hendorf"></a>
Описание: https://de.pycon.org/schedule/talks/deep-learning-with-pytorch-for-more-fun-and-profit-part-ii/

Видео: https://youtu.be/yB1rUfPILFY


![](images/PyCon.DE_2018/photo_2018-11-14_12-51-48.jpg)
Доклад одного из организаторов конфы про deep learning. Написано, что вторая часть, первая была не на этой конференции, а на других (есть видео)

![](images/PyCon.DE_2018/photo_2018-11-14_12-51-50.jpg)
Предыдущие доклады

Рассказывает краткое содержание предыдущих серий:
* Развлекался переносом стилей старых комиксов на новые, а также на всё подряд, конечно :)

Следующий шаг - аудио спектакли. Хотел генерировать целиком - сюжет, диалоги, человеческую речь, обложку, фоновые звуки

Текст: нашел сделанные фанатами скрипты, собрал имена, взял сетку Andrey Karpathy для Шекспира, получилось мало вразумительно
Взял чатбота по Стартреку, тоже не очень

Переключился на обложку, получилось очень классно

![](images/PyCon.DE_2018/photo_2018-11-14_12-51-51.jpg)
Среди этих картинок половина оригинальная, половина сгенерирована

![](images/PyCon.DE_2018/photo_2018-11-14_12-51-53.jpg)
Эти сгенерированы

Генерация звука: взял датасет с чтением английских текстов, взял сетку nvidia, тренировал несколько дней - получилось неплохо. Но с немецким все оказалось сложнее :joy:
Собирал датасет из новостных статей, для которых были аудиоверсии, прогонял их через google transcript, чтобы получить разметку фраз по времени. Обучил, получился жуткий голос, но в целом разобрать текст можно

![](images/PyCon.DE_2018/photo_2018-11-14_12-51-54.jpg)
Немного из серии "смешно, если бы не было так грустно"

![](images/PyCon.DE_2018/photo_2018-11-14_12-51-56.jpg)

![](images/PyCon.DE_2018/photo_2018-11-14_12-51-58.jpg)
Выводы из эксперимента (справа выдержка из какой-то немецкоязычной статьи)

Еще немного мыслей про AI vs Marketing B-bingo

[Наверх к оглавлению](#content)



## Reproducibility, and Selection Bias in Machine Learning <a name="reproducibility"></a>
Описание: https://de.pycon.org/schedule/talks/reproducibility-and-selection-bias-in-machine-learning/

Видео: https://youtu.be/MOBs6MNepDk


![](images/PyCon.DE_2018/photo_2018-11-14_12-52-01.jpg)
Следующий доклад: что делать, если кросс-валидации недостаточно

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-06.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-52-07.jpg)
Определение, первая часть доклада про reproducible. Классический подход - githib + jupyter.

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-09.jpg)
Список про воспроизводимость кода в целом. Дальше будем конкретно про ml

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-10.jpg)
Нужно фиксировать все рандомные параметры, притом далеко не всегда они видны в первом слое апи

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-12.jpg)
Подробнее про популярные либы. Theano берет из numpy

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-13.jpg)
С кудой всё плохо, дальше были слайды с открыми issues в тензорфлоу и пайторче

Переходим к части про selection bias.
Пара слайдов про hold-out, про bias-variance problem, learning curves, разные варианты разбиения для кросс-валидации. Опять напоминание фиксировать random seed

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-15.jpg)
Его предложение - несколько cv с разными seed, внизу со ссылкой на the elements рекомендуемые примеры для подбора параметров и для выбора модели

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-16.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-52-17.jpg)
Его проект для этой цели (wip)

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-18.jpg)
Пример применения для его биологического проекта

[Наверх к оглавлению](#content)



## Data science complexity and solutions in real industrial projects <a name="industrial"></a>
Описание: https://de.pycon.org/schedule/talks/data-science-complexity-and-solutions-in-real-industrial-projects/

Видео: https://youtu.be/bmtGr0LSb_Y

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-21.jpg)
Ещё один доклад от ребят, которые предоставляют сервис по проверке труб

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-22.jpg)
Немного про их данные

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-23.jpg)
В производстве тестируются на реально повреждённых трубах

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-26.jpg)
Доклад про то, как получать данные с этапа верификации результатов исследования заказчиком на этап обучения моделей. Проблемы перечислены на слайде. Решения не особо замысловатые, слайды есть тут https://github.com/rosen-group/conferences/blob/master/PyConDE/2018/DataScienceComplexityAndSolutionsInRealIndustrialProjects_by_AMiller_ROSEN_Group.pdf

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-27.jpg)
Как делается верификация - лазером без остановки работы трубопровода или рентгеном после выкапывания опасного участка

[Наверх к оглавлению](#content)



## PyTorch as a scientific computing library: past, present and future <a name="pytorch"></a>
Описание: https://de.pycon.org/schedule/talks/pytorch-as-a-scientific-computing-library-past-present-and-future/

Видео: https://youtu.be/0Y4kY6PnYfM


Доклад про advanced analytics today оказался слишком водянистым, перешла на доклад про pytorch. Adam Paszke рассказывает свежий релиз 1.0. Добавили script-mode

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-29.jpg)
Было

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-30.jpg)
Стало

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-31.jpg)
Текущие возможности

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-32.jpg)
Как перевести

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-34.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-52-35.jpg)
Пример использования

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-36.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-52-37.jpg)
Пример

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-38.jpg)
WIP

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-40.jpg)
Пример достигнутого

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-41.jpg)
Куда же без плюсов)

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-42.jpg)
Пример

[Наверх к оглавлению](#content)



## Processing Geodata using Python <a name="geodata"></a>
Описание: https://de.pycon.org/schedule/talks/processing-geodata-using-python/

Видео: https://youtu.be/49QwoR2aG74

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-43.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-52-44.jpg)
Показывать будет тетрадку, вверху ссылка на нее

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-45.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-52-46.jpg)
Обе векторные + pandas

Примеры про shapely, работа с многоугольниками: рисование, бинарные операции, в т.ч. contains, touches, crosses; сохранение в виде текста (wkt)

Fiona: больше возможностей для метаданных. Пример на открытых данных про аэропорты, про страны

Для перевода между системами координат pyproj

Geopandas
Другой пример про датасет про города с населением более 5к человек
Добавляем в dataframe колонку типа shapely.point, легко рисовать, проверять принадлежность полигонам

Folium: карты от open street map. Совместимо со всем предыдущим, можно рисовать красивые интерактивные (но не динамические) карты.

Ipyleaflet - ещё и динамические карты (внутри jupyter)

Вопрос про масштабирование - при использовании pandas всё в памяти, для многих полигонов лучше использовать напрямую фиону

[Наверх к оглавлению](#content)



## Put your data on a map <a name="data_on_map"></a>
Описание: https://de.pycon.org/schedule/talks/put-your-data-on-a-map/

Видео: https://youtu.be/CdgI-TUv5z0

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-48.jpg)
Ещё один доклад про карты

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-49.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-52-50.jpg)

Folium: карты, маркеры, geojson, разные tiles, стили отрисовки. Можно сделать .save("...html")

MapboxGL: больше про кастомную отрисовку. df_to_geojson: географическую инфу отдельно, мету отдельно.
Тысяча настроек, группировка по цветам, кластеризация, красота.

Kepler.gl - больше интерактивности, меньше программирования. Загружаешь данные, дальше gui с разными типами картинок поверх карты


![](images/PyCon.DE_2018/photo_2018-11-14_12-52-51.jpg)
Summary

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-52.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_12-52-53.jpg)

[Наверх к оглавлению](#content)



## Observe all your applications <a name="observe"></a>
Описание: https://de.pycon.org/schedule/talks/observe-all-your-applications/

Видео: https://youtu.be/F6-nvgnlr9Y

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-55.jpg)
Как настроить всё так, чтобы легко фиксить проблемы

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-56.jpg)
Как сделать сервис прозрачным

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-57.jpg)
Как писать сообщения в логах

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-58.jpg)
Форматирование сообщений: информация для дебага, подсветка вывода

![](images/PyCon.DE_2018/photo_2018-11-14_12-52-59.jpg)
Как собирать логи с распределенной системы: стандартный подход

![](images/PyCon.DE_2018/photo_2018-11-14_12-53-00.jpg)
Ошибки: sentry.

![](images/PyCon.DE_2018/photo_2018-11-14_12-53-01.jpg)
Для метрик специальный демон, который комбинирует связанные события в единые метрики

![](images/PyCon.DE_2018/photo_2018-11-14_12-53-03.jpg)
Визуализация - графана, притом каждый делает дашборды под свои процессы

![](images/PyCon.DE_2018/photo_2018-11-14_12-53-04.jpg)
Рекомендует провязывать все действия пользователя (например) общим id. Полезно в том числе для профайлинга

![](images/PyCon.DE_2018/photo_2018-11-14_12-53-05.jpg)

[Наверх к оглавлению](#content)



## Where the heck is my memory? <a name="memory"></a>
Описание: https://de.pycon.org/schedule/talks/where-the-heck-is-my-memory/

Видео: https://youtu.be/C-1XWTgFo5g

![](images/PyCon.DE_2018/photo_2018-11-14_12-53-06.jpg)
Доклад про memory management

![](images/PyCon.DE_2018/photo_2018-11-14_12-53-07.jpg)
Заметили после апдейта утечку памяти

![](images/PyCon.DE_2018/photo_2018-11-14_12-53-08.jpg)
Общий вид процесса. Фикс - добавили схематизацию, проблема ушла. Почему?

![](images/PyCon.DE_2018/photo_2018-11-14_12-53-10.jpg)
Локализовали проблему - пустые датафреймы

![](images/PyCon.DE_2018/photo_2018-11-14_12-53-11.jpg)
Как выглядел код - исходные данные удалялись явно

![](images/PyCon.DE_2018/photo_2018-11-14_12-53-12.jpg)
Случайно заметили, что в разных окружениях работает с памятью по-разному. Перешли на cpu profiler

![](images/PyCon.DE_2018/photo_2018-11-14_12-53-13.jpg)
Заметили, что сериализация пустого датафрейма занимает кучу времени, wtf?

![](images/PyCon.DE_2018/photo_2018-11-14_12-53-14.jpg)
Оказалось, там были категориальные фичи, для которых даже в пустом датафрейме хранились огромные списки строк. Изменили схему данных - проблема исчезла

![](images/PyCon.DE_2018/photo_2018-11-14_12-53-15.jpg)
Заключение

[Наверх к оглавлению](#content)



## Lightning talks <a name="lightning2"></a>
Описание: список тем ниже

Видео: можно найти по названию здесь https://administraitor.video/edition/PyCon.DE/2018


![](images/PyCon.DE_2018/IMG_20181025_184756.jpg)
Список докладов

![](images/PyCon.DE_2018/photo_2018-11-14_12-53-17.jpg)
Внезапный lightning talk про предсказание молний. По двум спутниковым снимкам предсказывает следующий, потом смотрит на разницу с реальностью и по этой разнице предсказывает молнии с accuracy 90%, что бы это ни значило

[Наверх к оглавлению](#content)


## Keynote: Emmanuelle Gouillart <a name="keynote_skimage"></a>
Описание: https://de.pycon.org/blog/pyconde-and-pydata-karlsruhe-2018-keynote-emmanuelle-ouillart/

Видео: https://youtu.be/P5kQXwmAYSY

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-03.jpg)
Keynote от Emmanuelle Gouillart, создательницы scikit-image

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-05.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_14-10-06.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_14-10-07.jpg)
Есть ли будущее у классической обработки изображений в эпоху DL?

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-08.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_14-10-09.jpg)
Примеры применения

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-10.jpg)
Отметила регионы с разными текстурами (цветными кругами), затем препроцессинг scikit-image, классификация scikit-learn, получилась точная разметка текстур в изображении какого-то физического процесса

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-11.jpg)
Статистика использования пакета

Работают с изображениями как numpy-массивами

Много внимания уделяют консистентности с sklearn, а также внутренней согласованности нейминга. Также стараются, чтобы для учёных, мало знакомых с программированием, порог входа был минимальным. Делают туториалы (см. scientific python lectures), документацию, подборки примеров

Много говорит про интерактивную документацию.
Joblib для кеширования промежуточных данных в скриптах, также для параллелизации (ещё пробовали dash)

[Наверх к оглавлению](#content)


## Strongly typed datasets in a weakly typed world <a name="typed_datasets"></a>
Описание: https://de.pycon.org/schedule/talks/strongly-typed-datasets-in-a-weakly-typed-world/

Видео: https://youtu.be/wtpQTWROPc0

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-12.jpg)
Доклад от той же фирмы, что вчера рассказывала про утечку памяти из-за пустых датафреймов

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-12%20(2).jpg)
У всего свои системы типов. В целом похожие, но есть своя специфика (те же categories в пандас), плюс конвертации (numpy int64->float64 может привести к очень неожиданным результатам)

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-13.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_14-10-14.jpg)

[Наверх к оглавлению](#content)



## Satellite data is for everyone: insights into modern remote sensing research with open data and Python <a name="sattelites"></a>
Описание: https://de.pycon.org/schedule/talks/satellite-data-is-for-everyone-insights-into-modern-remote-sensing-research-with-open-data-and-python/

Видео: https://youtu.be/tKRoMcBeWjQ


![](images/PyCon.DE_2018/photo_2018-11-14_14-10-15.jpg)
Доклад про спутниковые данные 

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-16.jpg)
Agenda

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-17.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_14-10-18.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_14-10-19.jpg)
Два варианта, как учиться - с нуля или только определенную часть почти готовой сетки

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-20.jpg)
Какие взяли модели (реализованные в керасе)

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-21.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_14-10-22.jpg)

Идут по тетрадке из репозитория про дообучение imagenet сетки, там все нормально прокомментировано, не буду пересказывать.
Также предлагают пробовать сегментацию, а потом уже классификацию

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-23.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_14-10-24.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_14-10-25.jpg)

[Наверх к оглавлению](#content)



## Python Decorators: Gift or Poison? <a name="decorators"></a>
Описание: https://de.pycon.org/schedule/talks/python-decorators-gift-or-poison/

Видео: https://youtu.be/VEexfP68LJs

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-26.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_14-10-27.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_14-10-28.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_14-10-29.jpg)

Дополнительная обработка результатов / логгирование / профайлер / ...
Пара примеров с кодом

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-30.jpg)

Дальше будет пример какого-то полезного для тестирования декоратора

Пара слов про late binding

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-31.jpg)

Замечательно, а зачем?

Если сохранять декорированную рекурсивную функцию в переменную, магии не получится

[Наверх к оглавлению](#content)



## Спринты и воркшоп PyLadies <a name="sprints"></a>

Хочется как-то подвести итоги выходных, два дня спринтов и воркшопа пролетели очень быстро: в первый день я развлекалась с micropython, мигала лампочками и замеряла температуру сенсорами, а во второй - готовила доклад на PiterPy, которая будет через неделю.

![](images/PyCon.DE_2018/photo_2018-11-14_14-10-36.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_14-10-37.jpg)
![](images/PyCon.DE_2018/photo_2018-11-14_14-10-38.jpg)

[Наверх к оглавлению](#content)


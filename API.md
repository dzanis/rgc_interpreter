# Манипуляции с объектами
| Имя функции | Входные параметры | Результат | Описание |
| ------ | ------ | ------ | ------ |
|objectGetId| - |int|Возвращает идентификатор обрабатываемого в данный момент объекта|
|objectDestroy| uint |-|Удаляет объект с карты. Принимает 1 параметр: идентификатор объекта|
|objectSetEnable| uint bool |-|Установить активность объекта. Неактивный объект не обрабатывается движком - отсутствует физика, анимация, рендеринг объект и обработка его скриптов. Принимает 2 параметра: идентификатор объекта, активность, где true - объект активен, false - неактивен|
|objectIsEnable|uint|bool|Проверить является ли объект активным, где true - активен, false - неактивен. Принимает 1 параметр: идентификатор объекта|
|objectIsInView| uint |bool|Проверяет находится ли объект в области видимости камеры|
|objectSetPosition|uint double double double| - |Установить объект в позицию (x, y, z). Принимает 4 параметра: идентификатор объекта, координаты для переноса - x, y, z|
|objectSetPositionX|uint double | - |Установить объект в позицию (x). Принимает 2 параметра: идентификатор объекта, координата для переноса x|
|objectSetPositionY|uint double | - |Установить объект в позицию (y). Принимает 2 параметра: идентификатор объекта, координата для переноса y|
|objectSetPositionZ|uint double | - |Установить объект в позицию (z). Принимает 2 параметра: идентификатор объекта, координата для переноса z|
|objectMove|uint double double double| - |Сдвинуть объект на указанное расстояние. Принимает 4 параметра: идентификатор объекта, величина переноса - x, y, z|
|objectGetPosition|uint| double[3] |Получить позицию объекта в формате массива чисел из трёх элементов. Принимает 1 параметр: идентификатор объекта. |
|objectGetPositionX|uint| double |Получить позицию X объекта. Принимает 1 параметр: идентификатор объекта|
|objectGetPositionY|uint| double |Получить позицию Y объекта. Принимает 1 параметр: идентификатор объекта|
|objectGetPositionZ|uint| double |Получить позицию Z объекта. Принимает 1 параметр: идентификатор объекта|
|objectSetRotation|uint double double double| - |Установить углы поворотов объекта по осям (x, y, z). Принимает 4 параметра: идентификатор объекта, углы - pitch, yaw, roll|
|objectSetRotationX|uint double| - |Установить угол поворота объекта по оси oX. Принимает 2 параметра: идентификатор объекта, угол - pitch|
|objectSetRotationY|uint double| - |Установить угол поворота объекта по оси oY. Принимает 2 параметра: идентификатор объекта, угол - yaw|
|objectSetRotationZ|uint double| - |Установить угол поворота объекта по оси oZ. Принимает 2 параметра: идентификатор объекта, угол - roll|
|objectRotate|uint double double double| - |Повернуть объект на указанные углы по осям. Принимает 4 параметра: идентификатор объекта, углы - pitch, yaw, roll|
|objectGetRotationX|uint| double[3] |Получить углы поворота объекта в формате массива чисел из трёх элементов. Принимает 1 параметр: идентификатор объекта|
|objectGetRotationX|uint| double |Получить тангаж (pitch) объекта. Принимает 1 параметр: идентификатор объекта|
|objectGetRotationY|uint| double |Получить рысканье (yaw) объекта. Принимает 1 параметр: идентификатор объекта|
|objectGetRotationZ|uint| double |Получить крен (roll) объекта. Принимает 1 параметр: идентификатор объекта|

# Пользовательские данные у объектов
| Имя функции | Входные параметры | Результат | Описание |
| ------ | ------ | ------ | ------ |
|objectAddVarNumber|uint string double|-|Привязать к объекту пользовательский параметр в виде числа. Принимает 3 параметра: идентификатор объекта, имя переменной, значение|
|objectAddVarBool|uint string bool|-|Привязать к объекту пользовательский параметр в виде булевого значения. Принимает 3 параметра: идентификатор объекта, имя переменной, значение|
|objectAddVarString|uint string string|-|Привязать к объекту пользовательский параметр в виде строки. Принимает 3 параметра: идентификатор объекта, имя переменной, значение|
|objectAddVarVector|uint string double double double|-|Привязать к объекту пользовательский параметр в виде вектора - массив чисел из трех элементов. Принимает 3 параметра: идентификатор объекта, имя переменной, значение|
|objectSetVar|uint string (*)|-|Изменить значение пользовательской переменной. Функция полиморфна. Для чисел, булевых и строк принимает 3 параметра: идентификатор объекта, имя переменной, значение. Для вектора принимает 5 параметров: идентификатор объекта, имя переменной, координаты из трех чисел - x, y, z. Если тип нового значения не соответствует указанному ранее типу, то значение изменено не будет |
|objectGetVar|uint string|(*)|Получить значение пользовательской переменной. Функция полиморфна. Принимает 2 параметра: идентификатор объекта, имя переменной|
|objectRemoveVar|uint string|-|Удалить пользовательскую переменную. Принимает 2 параметра: идентификатор объекта, имя переменной|
|objectClearVars|uint|-|Удалить все пользовательские переменные, привзяанные к объекту. Принимает 1 параметр: идентификатор объекта|
|objectIsVarNumber|uint string|bool|Проверка типа привязанной ранее пользовательской переменной. Возвращает true, если переменная является числом. Принимает 2 параметра: идентификатор объекта, имя переменной|
|objectIsVarBool|uint string|bool|Проверка типа привязанной ранее пользовательской переменной. Возвращает true, если переменная является булевым значением. Принимает 2 параметра: идентификатор объекта, имя переменной|
|objectIsVarString|uint string|bool|Проверка типа привязанной ранее пользовательской переменной. Возвращает true, если переменная является строкой. Принимает 2 параметра: идентификатор объекта, имя переменной|
|objectIsVarVector|uint string|bool|Проверка типа привязанной ранее пользовательской переменной. Возвращает true, если переменная является вектором. Принимает 2 параметра: идентификатор объекта, имя переменной|

# Камера
| Имя функции | Входные параметры | Результат | Описание |
| ------ | ------ | ------ | ------ |
|cameraSetPitch|double|-|Установить крен камеры (pitch). Принимает 1 параметр: угол в градусах|
|cameraSetYaw|double|-|Установить крен камеры (yaw). Принимает 1 параметр: угол в градусах|
|cameraGetPitch|-|double|Получить крен камеры (pitch). Возвращает угол в градусах|
|cameraGetYaw|-|double|Получить крен камеры (yaw). Возвращает угол в градусах|
|cameraGetTarget|-|double[3]|Получить вектор взгляда камеры в формате массива чисел из трёх элементов|
|cameraGetTargetX|-|double|Получить координату X вектора взгляда камеры|
|cameraGetTargetY|-|double|Получить координату Y вектора взгляда камеры|
|cameraGetTargetZ|-|double|Получить координату Z вектора взгляда камеры|
|cameraUpdate|-|-|Обновить состояние камеры и точку, куда она смотрит. Вызывается после изменения положения или углов поворота камеры|

# Карта
| Имя функции | Входные параметры | Результат | Описание |
| ------ | ------ | ------ | ------ |
|mapIsPlaceFree|uint uint|bool|Проверка является ли указанная ячейка на карте свободной от стен. Принимает 2 параметра: x и y на карте для проверки. Возвращает true, если ячейка свободна|

На данный момент карта представляет собой двумерный массив размеров [MAP_WIDTH x MAP_HEIGHT].
 
Текущие значения констант:

MAP_WIDTH  = 64

MAP_HEIGHT = 64


# Устройства ввода
Клавиатура.

Модуль Keyboard. Функции вызываются как Keyboard.*

Коды клавиш хранятся в keycodes.js.

| Имя функции | Входные параметры | Результат | Описание |
| ------ | ------ | ------ | ------ |
|isEventAvailable|-|bool|Возвращает true, если произошло событие клавиатуры|
|isKeyHit|KEY_CODE|bool|Возвращает true, если указанная кнопка нажата|
|isKeyPressed|KEY_CODE|bool|Возвращает true, если указанная кнопка была нажата|
|isKeyReleased|KEY_CODE|bool|Возвращает true, если указанная кнопка была отпущена|

Мышь.

Модуль Mouse. Функции вызываются как Mouse.*

Коды клавиш хранятся в keycodes.js.

| Имя функции | Входные параметры | Результат | Описание |
| ------ | ------ | ------ | ------ |
|setCursorVisible|bool|-|Установить видимость курсора мыши. Принимает 1 параметр: true - видимый, false - невидимый|
|isCursorVisible|-|bool|Проверить видимость курсора мыши. Возвращает: true - видимый, false - невидимый|
|isEventAvailable|-|bool|Возвращает true, если произошло событие мыши|
|setLogicalPosition|double double|-|Установить курсор мыши в позицию, переданную логическими координатами. Принимает значения в промежутке 0.0 .. 1.0, где (0.0, 0.0) - левый верхний угол, а (1.0, 1.0) - правый нижний|
|setPosition|int int|-|Установить курсор мыши в позицию, переданную абсолютными координатами. Принимает 2 параметра: x и y|
|getX|-|int|Получить текущую координату X курсора мышки|
|getY|-|int|Получить текущую координату Y курсора мышки|
|getDeltaX|-|double|Получить смещение курсора мышки по координате X относительно предыдущего положения в предыдущем кадре|
|getDeltaY|-|double|Получить смещение курсора мышки по координате X относительно предыдущего положения в предыдущем кадре|

# Математика
| Имя функции | Входные параметры | Результат | Описание |
| ------ | ------ | ------ | ------ |
|degToRad|double|double|Преобразование градусов в радианы|
|radToDeg|double|double|Преобразование радиан в градусы|
|distanceBetweenObjects| uint uint |double|Возвращает расстояние между двумя объектами, принимает в параметрах идентификаторы объектов для проверки|
|distanceBetweenPoints|(*)|double|Возвращает расстояние между двумя точками. Функция полиморфна. Принимает: для двумерных точек 4 параметра типа double - x1 y1 x2 y2; для трёхмерных точек 6 параметров типа double - x1 y1 z1 x2 y2 z2|

# Системные
| Имя функции | Входные параметры | Результат | Описание |
| ------ | ------ | ------ | ------ |
|print|(*)|-|Вывод в консоль сообщения. Принимает вариативное количество параметров, сцепляя их в одну строку|
|deltaTime|-|double|Возвращает количество секунд, прошедшее с предыдущего кадра|
|windowGetWidth|-|int|Получить ширину окна, в котором происходит вывод|
|windowGetHeight|-|int|Получить высоту экрана, в котором происходит вывод|

# MADE-CV-HW2
Домашняя работа №2 MADE CV

## 1 этап - детекция

В качестве первой модели для детекции я попробовал `FasterRCNN` для поиска bounding box с гос. номерами, 
но результат меня не удовлетворил.

Затем я попробовал использовать `KeypointRCNN`, но столкнулся с проблемами в процессе обучения (модель не училась),
долго пытался исправить, но так и не понял в чем проблема.

Следующей я попробовал `MaskRCNN` и на ней в итоге остановился.

В процессе предобработки изображений использовал повороты (\[-20; 20\] градусов), смещения (\[-20%; 20%\] от размера изображения) и 
масштабирование (\[0.7; 1.3\]).

# 2 этап - подготовка изображения для ocr

Использовал `four-point-transform` для того, чтобы растянуть номер в прямоугольное изображение по 4 точкам.

# 3 этап - ocr

Использовал модель с семинара с незначительными модификациями, такими как добавление 
дополнительных линейных и `GRU` слоев в `SequencePredictor`.

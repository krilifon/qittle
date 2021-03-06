## Qittle — indispensable solution for handling QIWI hooks
**Qittle** — это библиотека для легкого и функционального хендлинга вебхуков, посылаемых QIWI при каких-либо транзакциях внутри системы.

### Установка
1) **Из GitHub**:
    ```sh
   pip install -U https://github.com/muffleo/qittle/archive/master.zip
   ```
   
### Преимущества
- **полностью асинхронное серверное ядро**. Пишите эффективный конкуррентный код, способный обрабатывать десятки запросов в секунду.
- **типизированность**. Свободно ориентируйтесь в исходном коде, получайте подсказки в Вашей IDE и многое другое.


### Пример
В этом примере рассмотрим безусловную обработку всех поступающих уведомлений. Посмотрите, как это просто:
```python
from qittle import Listener, PaymentModel
from qittle.utils.logger import logger

listener = Listener("token", address="address")

@listener.event()
async def simple_handler(payment: PaymentModel):
    logger.success("Captured payment!")

listener.listen()
```
_Если вы не укажете адрес, на который QIWI будет отправлять обновления, Qittle автоматически создаст ngrok-туннель для Вашего удобства!_

Другие примеры можно найти в папке [examples](./examples).

### Сообщество
[Присоединяйтесь](https://vk.me/join/AJQ1d6rurhh0SUGH38LBeyeC) к нашему чату в VK, задавайте вопросы — и получайте ответы!

### Лицензия
© 2020 Exthrempty.
Этот проект имеет [MIT](./LICENSE) лицензию. 


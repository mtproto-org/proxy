[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fmtproto-org%2Fproxy.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fmtproto-org%2Fproxy?ref=badge_shield)
# MTProxy
Готовый вариант запуска собственного прокси-сервера на базе протокола MTProto.

### Что необходимо?
Для запуска собственного прокси-сервера, вам необходимо:

1. Абсолютно чистый сервер с ОС Ubuntu 16.04 или старше
2. Любой процессор/ОЗУ/диск (хотя бы: 1 ядро, 512 Мб ОЗУ, 5 ГБ диска)
3. Свободный порт и отсутствие любого файерволла (желательно)

### Использование

```javascript
const mtproxy = require('@mtproto-org/mtproxy');

mtproxy()
```

1. `sudo apt-get update`
2. `sudo apt-get upgrade`
3. `sudo apt-get install -y nodejs`
4. `sudo apt-get install -y npm`
5. `sudo apt-get install -y git`
6. `npm install pm2 -g`
7. `cd && mkdir mtproto && cd mtproto`
8. `npm install @mtproto-org/mtproxy`
9. `pm2 start *.js -i max`

#### Дополнительные настройки
Перейдите в папку, где лежит `*.js` и выполните одну из команд:

1. Запустить: `pm2 start *.js -i max`
2. Перезапустить: `pm2 restart *.js`
3. Выключить: `pm2 stop *.js`

### Что дальше?
По умолчанию:
1. Порт для подключения: `2233`
2. Секретный ключ: `11112222333344445555666677778888`
Для того чтобы изменить его, передайте объект в mtproxy();

- **Объект**
  - `port`: (Number)
  - `secret` : (String)

Далее
```javascript
const mtproxy = require('@mtproto-org/mtproxy');

mtproxy({
    port: 1122,
    secret: '11112222333344445555666677778888'
})
```


Вы можете поменять стандартный порт и секретный ключ, если хотите полной приватности. Рекомендуем сгенерировать секретный ключ из 32-х случайных чисел. Эти настройки установлены для тех, кому необходимо сразу запустить и пользоваться прокси-сервером.

### Как подключиться?
1. Перейдите в `Настройки`
2. Далее в `Продвинутые настройки`
3. Далее в `Тип соединения`
4. Выберите `Использовать собственный прокси`
5. `Добавить прокси`
6. Выберите `MTPROTO`
7. Хост - IP-адрес сервера или его `hostname`
8. Порт - ввежите порт прокси-сервера (по умолчанию: 2233)
9. Ключ - введите ключ прокси-сервера (по умолчанию: `11112222333344445555666677778888`)
10. Нажмите кнопку `Сохранить`
11. Как только сервер добавится в список ваших прокси, выберите его и дождитесь статуса `Подключён`
12. Готово!

### Fossa

[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fmtproto-org%2Fproxy.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fmtproto-org%2Fproxy?ref=badge_large)

### Копирайт
Разработано командой [MTProto.org](https://mtproto.org) и опубликовано согласно с условиями лицензии MIT License.

Copyright 2019, MTProto.org Team

*Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:*

*The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.*

*THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.*

# Voice Assistant Python App for Windows, Linux & MacOS [оригинальный репозиторий](https://github.com/EnjiRouz/Voice-Assistant-App)
### Возможности приложения
Данный проект голосового ассистента на Python 3 для Windows и Linux умеет:
* распознавать и синтезировать речь в offline-режиме (без доступа к Интернету);
* сообщать о прогнозе погоды в любой точке мира;
* производить поисковый запрос в поисковой системе Google
  (а также открывать список результатов и сами результаты данного запроса);
* производить поисковый запрос видео в системе YouTube и открывать список результатов данного запроса;
* выполнять поиск определения в Wikipedia c дальнейшим прочтением первых двух предложений;
* переводить с изучаемого языка на родной язык пользователя (с учетом особенностей воспроизведения речи);
* искать человека по имени и фамилии в соцсетях ВКонтакте и Facebook;
* "подбрасывать монетку";
* воспроизводить случайное приветствие;
* воспроизводить случайное прощание с последующим завершением работы программы;
* менять настройки языка распознавания и синтеза речи;
* TODO многое другое...

Для **быстрой установки** всех требуемых зависимостей можно воспользоваться командой:

`pip install requirements.txt`

### Настройка синтеза и анализа речи с возможностью offline-работы
Голосовой ассистент использует для синтеза речи встроенные в операционные системы возможности
(т.е. **голоса зависят от настроек операционной системы**). Для этого используется библиотека `pyttsx3`. [Подробнее здесь](https://github.com/nateshmbhat/pyttsx3)

    Для корректной работы системы распознавания речи в сочетании с библиотекой SpeechRecognition
    используется библиотека PyAudio для получения звука с микрофона.

В целом, решение работает на Windows, Linux и MacOS с незначительными различиями при установке библиотек PyAudio и Google.

Для установки PyAudio на Windows можно найти и скачать нужный в зависимости от архитектуры и версии Python whl-файл [здесь](https://www.lfd.uci.edu/~gohlke/pythonlibs/#pyaudio) в папку с проектом. После чего его можно установить при помощи подобной команды:

`pip install PyAudio-0.2.11-cp38-cp38m-win_amd64.whl`

В случае проблем с установкой PyAudio на MacOS может помочь [данное решение](https://stackoverflow.com/questions/33851379/pyaudio-installation-on-mac-python-3).

    Для использования SpeechRecognition в offline-режиме (без доступа к Интернету), 
    потребуется дополнительно установить Vosk (качество моделей близко к Google)
    
    В проекте преимущественно используется Google при наличии доступа в Интернет и
    предусмотрено переключение на Vosk в случае отсутствия доступа к сети.

Для избежания проблем с установкой Vosk на Windows, я предлагаю скачать whl-файл в зависимости от требуемой архитектуры и версии Python. Его можно найти [здесь](https://github.com/alphacep/vosk-api/releases/). Загрузив файл в папку с проектом, установку можно будет запустить с помощью подобной команды: 

`pip install vosk-0.3.7-cp38-cp38-win_amd64.whl`

Модели для распознавания речи с помощью Vosk можно найти [здесь](https://alphacephei.com/vosk/models). Я использовала в проекте [ru](https://alphacephei.com/vosk/models/vosk-model-small-ru-0.4.zip) и [en](http://alphacephei.com/vosk/models/vosk-model-small-en-us-0.4.zip) модели

### Настройка получения прогноза погоды от OpenWeatherMap
Для получения данных прогноза погоды мною был использован сервис `OpenWeatherMap`, который **требует API-ключ**.
Получить API-ключ и ознакомиться с документацией можно после регистрации (есть `Free`-тариф) [здесь](https://openweathermap.org/).
Примеры использования можно найти [здесь](https://pyowm.readthedocs.io/en/latest/v3/code-recipes.html)


### Прочие зависимости
Команды для установки прочих сторонних библиотек:
Команда установки  | Назначение библиотеки
----------------|----------------------
`pip install google`       | Поисковые запросы в Google
`pip install SpeechRecognition`       | Распознавание речи (Speech-To-Text)
`pip install vosk`       | Offline распознавание речи (Speech-To-Text)
`pip install pyttsx3`   | Offline синтез речи на Windows (Text-To-Speech)
`pip install wikipedia-api`| Wikipedia API
`pip install googletrans`| Google Translate
`pip install pyowm`| Получение данных погоды с помощью OpenWeatherMap
`pip install python-dotenv`| Работа с `.env`-файлами для хранения API-ключей
`pip install scikit-learn`| Машинного обучение для угадывания намерений

Дополнительную информацию по установке и использованию библиотек можно найти [здесь](https://pypi.org/)

    У меня на Windows не возникало проблем с установкой библиотек, перечисленных в таблице выше, 
    потому прилагаю только команды для установки.
    
    В случае возникновения проблем с установкой на Windows, вы можете воспользоваться тем же способом, 
    который я предлагала для установки PyAudio выше.

# О ПРОЕКТЕ OOPT_YandexCloud
15 августа 2022 Государственному  природному биосферному заповеднику "Керженский" (http://www.kerzhenskiy.ru/) Yandex Cloud (https://cloud.yandex.ru/) предоставил грант на использование ресурсов облака. К началу 2023 года мы проверили свои гипотезы о перспективности трансформации информационной инфраструктуры заповедника в облако. В январе 2023 года Яндекс предложил свою помощь по разработке ПО. Более подробно можно прочитать в пока неопубликованной статье about.pdf
Данный репозиторий - стартовая активность в этом сотрудничестве.  

# МАНИФЕСТ
При разработке просьба учитывать доменную область и называть программные сущности согласно справочнику Реймерс Н.Ф. Экология (теории, законы, правила принципы и гипотезы) 
Приложения должны оформляться в виде Docker образов. Доступ к необходимым сервисам предоставляется по запросу, так как некоторые сервисы могут быть не активированы. 
Релизный код выкладывается в GitHub https://github.com/juhnowski - отсюда будем забирать в облако, разработчик может вести свой проект в своем репозитории, если ему так удобно, но кто-то должен будет мержить все командные изменения
Не может быть такой ситуации, что проект уже занят, допускается параллельная разработка одного и того же таска, история сама решит что получилось хорошо 
Лицензия на код https://choosealicense.com/licenses/gpl-3.0/ , просьба добавлять ее в корень проекта
Разработчики не ограничиваются ни языком,ни технологиями. Ссылки в рописаниях задач на какие либо технологии не являются обязательными, а лишь поясняют суть того, что имелось в виду. 
Если водникают вопросы по науке, то на них ответит Зам.Директора по науке - Николай Георгиевич Баянов bayanovng@mail.ru
По техническим вопросам - обращаться ко мне, Илья Юхновский juhnowski@gmail.com
По вопросам связанным с оргвопросами и доступным по гранту сервисам Яндекс - Марина Кошелева, телеграм: @koshelevamur
 
# СПИСОК ЗАДАЧ
## 1. Автогенератор "ЛЕТОПИСЬ ПРИРОДЫ"
- агрегация с Object Storage, DataLens
- агрегирование данных наблюдений
- построение графиков
- формирование текста летописи по шаблону
- летопись должна обновляться по мере обновления данных наблюдений (ориентировочно раз в день)
- летопись должна сохраняться в папку https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=LETOPIS%2F 
- логи с ошибками должны сохраняться
- при возникновении ошибки должна быть нотификация по почте

## 2. Рефакторинг БД
Перенос в ClickHouse данных
https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%91%D0%B0%D0%B7%D1%8B+%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85%2F

## 3. Animals 23 февраля
База данных представляет собой программу на QT, необходим рефакторинг с целью создания облачного приложения
 https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%91%D0%B0%D0%B7%D1%8B+%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85%2FAnimals+23+%D1%84%D0%B5%D0%B2%D1%80%D0%B0%D0%BB%D1%8F%2F
 - фронтенд
 - бэкенд
 - перенос данных в CH

 ## 4. Животный мир НО 
 Рефакторинг с целью создания облачного приложения. Сейчас это десктопное приложение 
 https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%91%D0%B0%D1%8F%D0%BD%D0%BE%D0%B2+%D0%9D%D0%93%2F%D0%94%D0%B8%D1%81%D0%BA+1+%D0%96%D0%B8%D0%B2%D0%BE%D1%82%D0%BD%D1%8B%D0%B9+%D0%BC%D0%B8%D1%80+%D0%9D%D0%9E%2F
 - UI/UX
 - фронтенд
 - бэкенд
 - перенос данных в CH
 
## 5. Библиотека Фауна НО
Сейчас это структурированный по папкам справочник на двух дисках
- Диск 2
https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%91%D0%B0%D1%8F%D0%BD%D0%BE%D0%B2+%D0%9D%D0%93%2F%D0%94%D0%B8%D1%81%D0%BA+2+%D0%91%D0%B8%D0%B1%D0%BB%D0%B8%D0%BE%D1%82%D0%B5%D0%BA%D0%B0+%D0%A4%D0%B0%D1%83%D0%BD%D0%B0+%D0%9D%D0%9E%2F

- Диск 3
https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%91%D0%B0%D1%8F%D0%BD%D0%BE%D0%B2+%D0%9D%D0%93%2F%D0%94%D0%B8%D1%81%D0%BA+3_%D0%91%D0%B8%D0%B1%D0%BB%D0%B8%D0%BE%D1%82%D0%B5%D0%BA%D0%B0+%D0%A4%D0%B0%D1%83%D0%BD%D0%B0+%D0%9D%D0%9E%2F
 - UI/UX
 - фронтенд
 - бэкенд
 - перенос данных в CH

 ## 6. Библиотека Керженского заповедника
 https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%91%D0%B0%D1%8F%D0%BD%D0%BE%D0%B2+%D0%9D%D0%93%2F%D0%91%D0%B0%D1%8F%D0%BD%D0%BE%D0%B2+%D0%9D%D0%93_%D0%A1+Public%2F%D0%91%D0%94+%D0%91%D0%B8%D0%B1%D0%BB%D0%B8%D0%BE%D1%82%D0%B5%D0%BA%D0%B0+%D0%9A%D0%B5%D1%80%D0%B6%D0%B5%D0%BD%D1%81%D0%BA%D0%BE%D0%B3%D0%BE+%D0%B7%D0%B0%D0%BF-%D0%BA%D0%B0%2F

Десктопное приложение Biblozero - необходим рефакторинг и перенос в облако
 https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%91%D0%B8%D0%B1%D0%BB%D0%B8%D0%BE%D1%82%D0%B5%D0%BA%D0%B0%2FBiblozero%2F

 - UI/UX
 - фронтенд
 - бэкенд
 - перенос данных в CH
 - поиск по всему Object Storage и копирование всех текстовых материал в структурированное прстранство в Object Storage
 - реализовать контекстный поиск по материалам (Solar, Sphinx, ElasticSearch или что-то подобное)

## 7. Система учета посетителей
необходим рефакторинг десктопного приложения с переносом его в облако и веб интерфейсом
https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%91%D0%B0%D1%8F%D0%BD%D0%BE%D0%B2+%D0%9D%D0%93%2F%D0%91%D0%B0%D1%8F%D0%BD%D0%BE%D0%B2+%D0%9D%D0%93_%D0%A1+Public%2F%D0%91%D0%94+%D0%9F%D0%BE%D1%81%D0%B5%D1%82%D0%B8%D1%82%D0%B5%D0%BB%D0%B8%2Fkerz_release_001%2Fkerz_release_001%2F
 - UI/UX
 - фронтенд
 - бэкенд
 - хранение данных в PostgreSQL
 - витрина данных с выданными бланками в CH
 - мобильное приложение для хранения персональных эелектронных бланков (пропуск в заповедник)

 ## 8. Сервис бланков
У заповедника есть бланки, которые должны быть доступны по запросу и напечатаны или же заполнены в электронном виде и потом напечатаны. Для этого необходим отдельный сервис. Также есть бланки строгой отчетности, по которым должны вестись учет уникальных номеров.

 https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%91%D0%B0%D1%8F%D0%BD%D0%BE%D0%B2+%D0%9D%D0%93%2F%D0%91%D0%B0%D1%8F%D0%BD%D0%BE%D0%B2+%D0%9D%D0%93_%D0%A1+Public%2F%D0%91%D0%BB%D0%B0%D0%BD%D0%BA+%D0%BF%D0%B8%D1%81%D1%8C%D0%BC%D0%B0+%D0%B7%D0%B0%D0%BF%D0%BE%D0%B2%D0%B5%D0%B4%D0%BD%D0%B8%D0%BA%D0%B0%2F

## 9. Сервис видеонаблюдения
http://51.250.94.137:5080/#/pages/login
 
 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - тестировщик
 - разработчик ИИ, системма обнаружения нарушителей
 - разработчик ИИ, система распознавания и классификации животных 
 - система нотификации о событиях

## 10. Гидробиология
Диск Cladocera
https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%91%D0%B0%D1%8F%D0%BD%D0%BE%D0%B2+%D0%9D%D0%93%2F%D0%94%D0%B8%D1%81%D0%BA+Cladocera%2F

https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%91%D0%B0%D1%8F%D0%BD%D0%BE%D0%B2+%D0%9D%D0%93%2F%D0%94%D0%B8%D1%81%D0%BA+Hydrobiologia+Kutikova%2F

Разработать веб приложение по гидробиологии. Текстовые ресурсы из библиотеки или пока хранить в отдельном ресурсе, а потом перенести в библиотеку. Накопленные данные разместить на витрине данных.
 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - тестировщик



## 11. Светлояр
https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%91%D0%B0%D1%8F%D0%BD%D0%BE%D0%B2+%D0%9D%D0%93%2F%D0%94%D0%B8%D1%81%D0%BA+Svetolyar%2C+may+2003%2F

Десктопная версия программы BioFOX Zoo - рефакторинг с целью создания облачного веб приложения
 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - тестировщик

 Разработать веб приложение по Светлояру. Текстовые ресурсы из библиотеки или пока хранить в отдельном ресурсе, а потом перенести в библиотеку. Накопленные данные разместить на витрине данных.


## 12. ГосНИОРХ
Разработать на основе накопленного материала b2g информационную систему по взаимодействию с ГосНИОРХ
 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - тестировщик

## 12. Гидромет
Разработать на основе накопленного материала b2g информационную систему по взаимодействию с Гидромет
Интеграционные сервисы

 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - тестировщик

## 13. IOT - Логгеры
https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%9B%D0%BE%D0%B3%D0%B3%D0%B5%D1%80%D1%8B%2F

Разработать интеграцию с логгерами, сохранение и визуализация информации, подготовка температурны данных для летописи

 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - даитасаинтист
 - тестировщик


## 14. Гидрология
https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%93%D0%B8%D0%B4%D1%80%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%8F%2F

На основе имеющихся данных разработать веб приложение по сбору, сохранению и визуализации данных, подготовка материала для летописи

 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - даитасаинтист
 - тестировщик

 ## 15. КАДАСТР
 справочно информационная система, интеграций с картой
 https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%9A%D0%90%D0%94%D0%90%D0%A1%D0%A2%D0%A0+%D0%9A%D0%B5%D1%80%D0%B6%D0%B5%D0%BD%D1%81%D0%BA%D0%BE%D0%B3%D0%BE+%D0%B7%D0%B0%D0%BF%D0%BE%D0%B2%D0%B5%D0%B4%D0%BD%D0%B8%D0%BA%D0%B0%2F

 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - даитасаинтист
 - тестировщик

## 16. Карты
 https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%9A%D0%B0%D1%80%D1%82%D1%8B%2F
 интеграция накопленного материала с серисом яндекс карты

 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - даитасаинтист
 - тестировщик

## 17. ЗМУ
https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%97%D0%9C%D0%A3%2F
- временно пустая папка, данные ЗМУ разбросаны по папкам сотрудников
 интеграция накопленного материала с серисом яндекс карты
 сохранение результатов в витринах данных
 система сбора данных
 мобильное приложение автоматизирующая работу по маршруту
 ИИ по анализу следа
 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - даитасаинтист
 - тестировщик

 ## 18. Лесоустройство
 https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%9B%D0%B5%D1%81%D0%BE%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%B0%2F

конвертация данных из старых форматов, интеграция с яндекс картами, создание информационного веб сервиса
 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - даитасаинтист
 - тестировщик

  ## 18. Пожары
  По накопленным данным разработать сервис пожарной безопасности и статистики, интеграция с сервисом видеонаблюдения
  https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%9F%D0%BE%D0%B6%D0%B0%D1%80%D1%8B%2F
 
 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - даитасаинтист
 - тестировщик

 ## 19. Определители
 ВебСервис определителей

 ###  19.1 Определители гельминтов
 https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%9E%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B8%D1%82%D0%B5%D0%BB%D0%B8%2F%D0%9E%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B8%D1%82%D0%B5%D0%BB%D0%B8+%D0%B3%D0%B5%D0%BB%D1%8C%D0%BC%D0%B8%D0%BD%D1%82%D0%BE%D0%B2%2F

  - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - даитасаинтист
 - тестировщик

 ## 20 Сервис учета куриных
 https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%A3%D1%87%D1%91%D1%82%D1%8B+%D0%BA%D1%83%D1%80%D0%B8%D0%BD%D1%8B%D1%85%2F
 Собрать по папкам сотрудников

 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - даитасаинтист
 - тестировщик

 ## 21. Погода
 https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%9F%D0%BE%D0%B3%D0%BE%D0%B4%D0%B0%2F
 
 ### 21.1 Интеграционный сервис с IOT метеостанция Dawis
 https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D1%87%D0%B5%D1%80%D0%BD%D0%BE%D1%80%D0%B5%D1%87%D1%8C%D0%B5%2F

 ### 21.2 Интеграционный сервис с IOT логгер Ekerk - см. п. 13

 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - даитасаинтист
 - тестировщик

## 22. Сервис учета русловых процессов
https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%A0%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D1%8B%D0%B5+%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81%D1%8B%2F
папка не прогрузилась, по методике и данных много статей у Заповедника, необходимо будет собрать материал по папкам сотрудников. Интеграция с картами, видеосервисом

 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - даитасаинтист
 - тестировщик
 - разработчик ИИ, по анализу изменений русла на видео 

## 23. Сервис фенология
https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%A4%D0%B5%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%8F%2F
папка не прогрузилась, по методике и данных много статей у Заповедника, необходимо будет собрать материал по папкам сотрудников. Интеграция с картами, видеосервисом

 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - даитасаинтист
 - тестировщик
 - разработчик ИИ, по анализу изменений русла на видео 

 ## 24. Сервис по учету ягодников
 https://console.cloud.yandex.ru/folders/b1g2s2g1u72k9c25um07/storage/buckets/meteo?key=%D0%AF%D0%B3%D0%BE%D0%B4%D0%BD%D0%B8%D0%BA%D0%B8%2F
 
папка не прогрузилась, по методике и данных много статей у Заповедника, необходимо будет собрать материал по папкам сотрудников. Интеграция с картами, видеосервисом

 - аналитик
 - архитектор
 - UI/UX
 - фронтенд
 - бэкенд
 - разработчик БД
 - даитасаинтист
 - тестировщик
 - разработчик ИИ, по анализу изменений русла на видео 

# Задача «Dockerfile»
Соберите ваш первый Docker-образ на основе приложения авторизации, которое вы писали во втором домашнем задании. Возьмите только серверное приложение без html из прошлого задания. Для этого вы сначала напишете ваш Dockerfile, а затем для удобства, напишете манифест для docker-compose.

## Описание
Шаг 1. Сначала вам надо собрать jar-архив с вашим Spring Boot приложением. Для этого в терминале, в корне вашего проекта выполните команду:

Для gradle: ./gradlew clean build (если пишет Permission denied, тогда сначала выполните chmod +x ./gradlew).

Для maven: ./mvnw clean package (если пишет Permission denied, тогда сначала выполните chmod +x ./mvnw).

Шаг 2. Теперь можно начинать писать Dockerfile. Базовым образом возьмите openjdk:8-jdk-alpine и не забудьте открыть для Docker порт(EXPOSE), на котором работает ваше приложение.

Шаг 3. Добавьте собранный jar в ваш образ(ADD). Если вы собирали с помощью maven, тогда jar будет лежать в папке target, а если gradle — в build/libs.

Шаг 4. Для удобства сборки образа и запуска контейнера вашего приложения напишите docker-compose.yml. Контейнер назовите, как вам нравится, а в его конфигурациях пропишите следующее:

добавьте build: ./, который скажет docker-compose, что надо сначала собрать образ для этого контейнера;
добавьте соответствие порта на хост машине и порта в контейнере для вашего приложения (аналог аргумента -p у команды docker run).
Шаг 5. Два полученных файла добавьте в репозиторий вашего приложения и пришлите ссылку на него.

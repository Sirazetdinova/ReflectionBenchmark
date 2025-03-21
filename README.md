# Т-Банк, Академия бэкенда. Проект 5: Измерение производительности

## Описание

В проекте требуется написать набор бенчмарк-тестов, которые покажут скорость работы разных версий одного и того же метода.

Время работы коротких методов обычно изменяется в наносекундах и сильно зависит от текущего состояния операционной системы, поэтому такие замеры делаются при помощи специальных библиотек.


## Функциональные требования
- Написать бенчмарк-тест для каждого варианта метода (см инструкцию по реализации).
- Использовать JMH

## Нефункциональные требования
- Опубликуйте финальную таблицу результатов запуска тестов.

## Задание
Требуется реализовать и сравнить производительность 4 способов обращения к методу Student#name() (или любого другого класса/интерфейса):
1. Прямой доступ
2. java.lang.reflect.Method
3. java.lang.invoke.MethodHandles
4. java.lang.invoke.LambdaMetafactory

## Начало работы

Для того чтобы собрать проект, и проверить, что все работает корректно, можно
запустить из модального окна IDEA
[Run Anything](https://www.jetbrains.com/help/idea/running-anything.html)
команду:

```shell
mvn clean verify
```

Альтернативно можно в терминале из корня проекта выполнить следующие команды.

Для Unix (Linux, macOS, Cygwin, WSL):

```shell
./mvnw clean verify
```

Для Windows:

```shell
mvnw.cmd clean verify
```

Для окончания сборки потребуется подождать какое-то время, пока maven скачает
все необходимые зависимости, скомпилирует проект и прогонит базовый набор
тестов.

Если вы в процессе сборки получили ошибку:

```shell
Rule 0: org.apache.maven.enforcer.rules.version.RequireJavaVersion failed with message:
JDK version must be at least 22
```

Значит, версия вашего JDK ниже 22.

Если же получили ошибку:

```shell
Rule 1: org.apache.maven.enforcer.rules.version.RequireMavenVersion failed with message:
Maven version should, at least, be 3.8.8
```

Значит, у вас используется версия maven ниже 3.8.8. Такого не должно произойти,
если вы запускаете сборку из IDEA или через `mvnw`-скрипты.

Далее будут перечислены другие полезные команды maven.

Запуск только компиляции основных классов:

```shell
mvn compile
```

Запуск тестов:

```shell
mvn test
```

Запуск линтеров:

```shell
mvn checkstyle:check modernizer:modernizer spotbugs:check pmd:check pmd:cpd-check
```

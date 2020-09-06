# Тест-план автоматизации тестирования подачи заявки на открытие вклада "Накопилка"
## 1. Перечень автоматизируемых сценариев
Далее приведен список позитивных и негативных проверок. При составлении тест-кейсов необходимо помнить:
1. Все проверки должны быть задействованы.
2. Для каждой негативной проверки делаем самостоятельный тест-кейс.
3. При проверке позитивных сценариев для одного поля, другие поля должны быть заполнены позитивными (корректными) данными - не допускается в таких сценариях дозаполнять поля негативными данными.

### Позитивные проверки
1. Проверка корректного имени. 
Имя на русском (только буквы, без символов), первая буква заглавная, количество символов 5-6. Считаем, что минимальная длина имени 2 символа - Ян, а максимальная 11 - Понтелеймон. Берем для теста примерно среднее значение символов.
2. Проверка минимальной допустимой длины имени в 2 символа - Ян.
3. Проверка максимальной допустимой длины имени в 11 символов - Апполинарий, Понтелеймон.
4. 10 цифр в телефонном номере (без учета кода +7. Он указан на странице сразу и задизаблен от правок).
5. Чекбокс согласия обработки персональных данных отмечен
6. Нажата кнопка отправки заявки на рассмотрение.

### Негативные проверки
1. Имя полностью в нижнем регистре на русском.
2. Имя Полностью в верхнем регистре на русском.
3. Имя на английском, длина 5-6 символов
4. Имя на китайском, длина 5-6 символов
5. Имя на арабском, длина 5-6 символов
6. Имя с Фамилией
7. ФИО
8. Пробел до имени
9. Пробел после имени
10. Пробел в имени
11. Пустое поле с именем
12. Дефис в имени
13. Спецсимволы в имени
14. Числа в имени
15. Имя из одной русской буквы
16. Исполняемые скрипты в поле Имя
17. Исполняемые скрипты в поле Телефон
18. Указать 100 000 символов (русские буквы) в поле Имя
19. Пустое поле с телефоном
20. Указать 5 цифр в телефоне
21. Указать 12 цифр в телефоне
22. Указать 100 000 цифр в телефоне
23. Попробовать стереть код +7
24. Буквы в телефоне
25. Пробел в начале телефона
26. Пробел в середине телефона
27. Пробел в конце телефона
28. Тире в начале телефона
29. Тире в середине телефона
30. Тире в конце телефона


## 2. Перечень используемых инструментов с обоснованием выбора
1. GIT - для возможности вести работу над автотестами совместно с другими членами команды.
2. Если проект написан на Java (уточнить у PM), то выбираем для написания автотестов IntelliJ IDEA - бесплатная и удобная среда разработки. 
3. В зависимости от того, как написан проект, выбираем Maven или Gradle. Должен быть один тип, по возможности, чтобы членам команды было проще переключаться между задачами (между разработкой и тестированием).
4. Библиотека Faker для использования рандомных номеров и имен - позволит расширить тестовое покрытие.
5. Allure - отчет позволит анализировать результаты прохода тестов и будет сохраняться история проходов, чтобы можно было провести ретроспективу после нескольких инкрементов продукта.
6. Selenide - позволит автоматизировать действия пользователя в браузере
7. Браузер Chrome - самый популярный браузер.

## Перечень необходимых разрешений/данных/доступов от банка (предоставлять доступ к СУБД или давать собранную версию сервиса, вам, естественно, не будут)
Необходим тестовый стенд для возможности запуска на нем автотестов и нагрузочного тестирования.

## Перечень и описание возможных рисков при автоматизации
1. Вклад перестанет существовать, код тестов может стать ненужным.
2. За кодом перестанут следить (прекращение инвестирования).
3. Недостаток инвестирования может привести к тому, что не все сценарии будут автоматизированы
4. Необходим тестовый стенд. При попытке тестирования на пром среде авто-тестами можем засорить базу данных, положить сервер или получить бан своему IP от службы безопасности.
5. Изменения в селекторах на странице, могут поменяться названия полей и т.д. Тесты потребуется в лучшем случае слегка подправить, а в худшем - переписывать полностью.

## Перечень необходимых специалистов для автоматизации
1. Тестировщик-автоматизатор
2. Менеджер (владелец) продукта
3. Разработчики из команды
4. Тим-лид
5. Инженер DevOps (при наличии выделенной роли в команде)

## Интервальная оценка с учётом рисков (в часах)
1. Написание плана - 3 часа
2. Составление тест-кейсов - 2 часа
3. Настройка среды и окружения - 8 часов
4. Автоматизация тест-кейсов - 20 часов
5. Обсуждения с командой, риски - 7 часов
## Итого: 40 часов
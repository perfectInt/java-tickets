## Билет 8.

### 1. В чем различия Error от Exception?

У всех исключений есть общий класс-предок **Throwable**. От него происходят две большие группы  — исключения (Exception) и ошибки (Error).  

**Error** — это критическая ошибка во время исполнения программы, связанная с работой виртуальной машины Java. В большинстве случаев Error не нужно обрабатывать, поскольку она свидетельствует о каких-то серьезных недоработках в коде.   
Наиболее известные ошибки: `StackOverflowError` — возникает, например, когда метод бесконечно вызывает сам себя, и `OutOfMemoryError` — возникает, когда недостаточно памяти для создания новых объектов.  

**Exceptions** — это, собственно, исключения: исключительная, незапланированная ситуация, которая произошла при работе программы. Это не такие серьезные ошибки, как Error, но они требуют нашего внимания. Все исключения делятся на 2 вида — `проверяемые (checked)` и `непроверяемые (unchecked)`. 

### 2. Дайте определения JVM, JRE, JDK.

**JVM (Java Virtual Machine)** - это виртуальная машина Java, которая исполняет байт-код программы, предварительно созданный компилятором Java.

**JRE (Java Runtime Environment)** - это оболочка JVM + библиотеки языка Java, необходимые для запуска приложения.

**JDK (Java Development Kit)** - это набор инструментов для разработки программ на Java. Содержит в себе JRE среду, которая в свою очередь содержит JVM.

### 3. Расскажите про протокол OAuth2.

**OAuth 2.0** — протокол авторизации, позволяющий выдать одному сервису (приложению) права на доступ к ресурсам пользователя на другом сервисе. Протокол избавляет от необходимости доверять приложению логин и пароль, а также позволяет выдавать ограниченный набор прав, а не все сразу.

### 4. Какими способами микросервисы могут общаться между собой?

Как правило, микросервисы слабо связаны друг с другом. Если мы хотим синхронное общение между микросервисами то можно использовать HTTP запросы (WebClient, RestTemplate). Но можно это дело делать и с асинхронным подходом через брокеры сообщений (RabbitMQ, Apache Kafka).

### 5. Что такое REST?

**REST (Representational State Transfer)** - это архитектура построения API, основанная на HTTP запросах (GET, POST, PUT, DELETE, etc.). Технологию REST API применяют везде, где пользователю сайта или веб-приложения нужно предоставить данные с сервера.

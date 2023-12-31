## Билет 4.

### 1. Сравните асимптотические сложности LinkedList и ArrayList.

**LinkedList** - структура данных, которая в своей основе использует связный список, элементы в котором находятся не последовательно, а в разных кусках памяти, и каждый элемент ссылается на следующий (в случае двусвязного списка еще и на предыдущий).  

**ArrayList** - структура данных, которая под капотом использует массивы.

Сложности для `LinkedList`:
- взятие по индексу - O(n)
- удаление - O(1)
- вставка в заданную позицию - O(n)
- вставка в конец - O(1)
- вставка в начало - O(1)

Сложности для `ArrayList`:
- всятие по индексу - O(1)
- удаление - O(n)
- вставка - O(n)

В целом, LinkedList в абсолютных величинах проигрывает ArrayList и по потребляемой памяти, и по скорости выполнения операций. LinkedList предпочтительно применять, когда нужны частые операции вставки/удаления или в случаях, когда необходимо гарантированное время добавления элемента в список.

### 2. Для чего нужны аннотации @Controller, @Service, @Configuration, @Component и @Repository?

Spring предоставляет дополнительные стереотипные аннотации: `@Component`, `@Service` и `@Controller`. `@Component` – это общий стереотип для любого компонента, управляемого Spring. `@Repository`, `@Service` и `@Controller` – это специализированные формы `@Component` для более конкретных случаев использования (на уровнях хранения, сервисном и представления, соответственно). Поэтому вы можете аннотировать свои компонентные классы с помощью `@Component`, но, если вместо этого аннотировать их `@Repository`, `@Service` или `@Controller`, ваши классы будут больше подходить для обработки инструментами или связи с аспектами. Например, эти стереотипные аннотации являются идеальными целями для срезов. `@Repository`, `@Service` и `@Controller` также могут нести дополнительную семантику в будущих выпусках Spring Framework. Таким образом, если вы делаете выбор между `@Component` и `@Service` для вашего сервисного уровня, `@Service` будет явно лучшим выбором. Аналогично, как было отмечено ранее, `@Repository` уже поддерживается как маркер для автоматического преобразования исключений на вашем уровне хранения.

`@Configuration` – это аннотация на уровне класса, указывающая на то, что объект является источником определений бина. Классы, аннотированные `@Configuration`, объявляют бины через методы, аннотированные `@Bean`. Вызовы методов `@Bean` для классов `@Configuration` также могут быть использованы для определения межбиновых зависимостей.

### 3. Теорема CAP.

CAP теорема - теорема, утверждающая о том, что в распределенных системах нельзя одновременно добиться трех свойств:
- **Consistency** — согласованность. Каждое чтение даст вам самую последнюю запись.
- **Availability** — доступность. Каждый узел (не упавший) всегда успешно выполняет запросы (на чтение и запись).
- **Partition tolerance** — устойчивость к распределению. Даже если между узлами нет связи, они продолжают работать независимо друг от друга.

### 4. Что такое "транзакция"? Назовите основные свойства транзакции.

**Транзакция** - это воздействие на базу данных, переводящее её из одного целостного состояния в другое и выражаемое в изменении данных, хранящихся в базе данных.

Основные свойства транзакции - ACID:
- Атомарность (atomicity) гарантирует, что никакая транзакция не будет зафиксирована в системе частично. Будут либо выполнены все её подоперации, либо не выполнено ни одной.
- Согласованность (consistency). Транзакция, достигающая своего нормального завершения и, тем самым, фиксирующая свои результаты, сохраняет согласованность базы данных.
- Изолированность (isolation). Во время выполнения транзакции параллельные транзакции не должны оказывать влияние на её результат.
- Долговечность (durability). Независимо от проблем на нижних уровнях (к примеру, обесточивание системы или сбои в оборудовании) изменения, сделанные успешно завершённой транзакцией, должны остаться сохранёнными после возвращения системы в работу.

### 5. Что такое "пул строк"?

**Пул строк** – это набор строк, хранящийся в `Heap`.

- Пул строк возможен благодаря неизменяемости строк в Java и реализации идеи интернирования строк
- Пул строк помогает экономить память, но по этой же причине создание строки занимает больше времени
- Когда для создания строки используются ", то сначала ищется строка в пуле с таким же значением, если находится, то просто возвращается ссылка, иначе создается новая строка в пуле, а затем возвращается ссылка на неё;
- При использовании оператора new создаётся новый объект String. Затем при помощи метода `intern()` эту строку можно поместить в пул или же получить из пула ссылку на другой объект String с таким же значением;
- Пул строк является примером паттерна «Приспособленец» (Flyweight).


# Алгоритмы и Структуры данных
* Сортировки, их скорости в лучшем, среднем, худшем случае
* СД для хранения данных: упорядоченность, скорость операций

# Java Core
* Почему java кросплатформенная?
* jre, jvm, jdk
* слоган java: напиши единожды, используй везде
* Xms, Xmx, Xss (heap start, heap max, stack max)
* битовые сдвиги
* try-with-resourses, closable
* stack trace
* POJO

## Object
* Перечислите методы класса object (toString, equals, hashCode, wait, notify, notifyAll, clone, finilize, getClass)
* Создать imutable класс
* Сравнение по == и по equals
* переопределение и перегрузка
* Какими способами можно сконструировать объект в Java?
* Что такое сигнатура метода? что входит? (название и аргументы) что не входит? (возвращаемое значение, тело, исключения)
* В чём отличие класса, объекта и интерфейса?
* Можно ли создать переменную и аргумент с одинаковым именем? нет, т.к. аргумент то же объявление переменной. возможно только для класса, когда его поле имеет такое же имя. тогда используем this.

## Примитивы
* Где хранятся?
* Обёртки, зачем нужны? (подстановка в generics, коллекции)
* Boxing / unboxing
* Сколько каждый весит

## Ссылочные типы
* Кто относится к ним? Строка, массив, обёртка
* Где хранится ссылка, объект?
* Как происходит передача в аргумент метода?
* Сборщик мусора

## Строки
* В чём разница инициализации через строковый литерал и через new
* String pool
* Минусы конкатенации через +
* StringBuilder, StringBuffer, их различия
* Методы (charAt, indexOf, lastIndexOf, substring, replace, replaceAll, contains, startswith, endswith)
* В какой кодировке хранятся? Зависит от версии java ( 2 / 1 байт)
* intern
* Почему хранить пароль предпочтительнее в char[]/byte[], а не в String?

## Interface и abstract class
* Отличия интерфейса и абстрактного класса, особенности использования
* default методы интерфейса
* Реализация нескольких интерфейсов
* Throwable - это класс!
* Раннее и позднее связывание

## Модификаторы доступа
* Расположите в порядке строгости: private, default(package-private), protected, public
* На что могут быть навешены?
* Какие возможны для поля? (все)
* Какие возможны для метода? (все)
* Какие возможны для класса? (только default и public для внешних классов, + private для внутренних)

## Static и final
* Что даёт модификатор static для поля? метода? класса?
* Что даёт модификатор final для поля? метода? класса?
* Как сделать immutable класс?

## Конструкторы и методы
* Что такое конструктор? что такое this, super?
* Можно ли перегрузить конструктор? а переопределить?
* Всегда ли вызывается родительский конструктор? (да, неявно)
* Чем отличается конструктор от метода?
* Можно ли this присвоить null? (нет)

## Аннотации
* Как сделать свою аннотацию?
* Когда исчезает аннотация? Retention (runtime, class, source)
* На что может быть навешена? Target (Type, Method, Field)
* Основные аннотации (override, suppresswarnings, deprecated, author)
* Что такое маркерная аннотация?

## Enum
* Какие плюсы? память
* Как добавить поля, конструктор?
* Область видимости (всегда public)
* Enum как ключ map (EnumMap class)

## Collections
* Что такое collection? Интерфейс
* iterable и iterator
* Иерархия collection
![Ответ](https://2.bp.blogspot.com/-gu5S7gtlY9M/WzYWc2dcw8I/AAAAAAAAAqg/zN-I0hK0DYoVqzAYeRl1KexIL7NJRCIywCLcBGAs/s1600/class-and-interface-hierarchy.jpeg)
* Stack - это класс или интерфейс? класс
* Queue и deque
### HashMap
* В чём отличие HashMap от HashTable (возможность использовать один ключ null, блокировка не всей таблицы, а только бакета при обращении)
* Контракт equals и hashCode, как HashMap проверяет наличие объекта
* Привести пример плохой реализации hashCode()
* Отличие hashMap от treeMap
* Алгоритмические сложности HashMap (~O(1))
* Как устроен hashSet? Тупо внутри hashMap, но значение всегда null
* Что будет, если попытаться вставить в HashMap уже имеющийся в ней ключевой объект? замена
* Случай, когда можем положить объект в мапу, а потом не можем найти (изменился хеш ключа) (нельзя так делать!)
* !!! ConcurrentHashMap
* Как отсортировать по значению? Через stream sort в linkedHashMap
### TreeMap
* Сложность O(log(N))
* Внутренняя реализация (красно-чёрное дерево)
* Можно ли хранить null? нет
* Можно ли хранить разные классы? нет
* Условия использования (наличие Comparator / Comparable)
### List
* Отличие arrayList от linkedList, алгоритмические сложности
* Вставка в середину arrayList
* Расширение arrayList

## Многопоточка
* wait, notify, notifyAll
* synchronized
* !!! JMM
* Callable, Runnable и Thread
* Жизненный цикл потока
* Daemon потоки
* Thread pool (зачем? переиспользовать потоки, убивать дорого)
* Интерфейсы Executor и ExecutorService
* !!! Утечки памяти
* !!! volatile
* Атомарные типы данных, обёртки

## Stream API
* Что такое стримы? Как работают? К чему применяются? Откуда лямбды? Функциональщина
* Типы операций: конвейерные, терминальные
* Filter, Map, FlatMap, Peek, Sorted
* collect, forEach, count, reduce, findFirst, anyMatch
* Коллекторы
* Optional

## Generics
* Diamond operator
* Ковариантность: <? extends T>
* Wildcard <?> то же самое <? extends Object>
* Контрвариантность: <? super T>
* Инвариатность: < T >
* Есть ли generics в runtime? (нет, т.к. обратная совместимость)
* Кто разбирается с правильностью операций? Compiler

## Exceptions
* Иерархия исключений
![Ответ](https://fuzeservers.ru/wp-content/uploads/e/f/7/ef79d4a747c25ed5d44c345f6d5bcfde.png)
* Проверяемые, непроверяемые
* try/catch, multi-catch, несколько catch подряд
* throw и throws

## Тесты
* JUnit, принцип работы
* @Test, @Before, @After, @BeforeAll, @AfterAll
* assert, assertThat, assertEquals, fail

## Сериализация и десериализация

## IO
* Reader/Writer, надстройки

## Три(или четыре) кита ооп
* Инкапсуляция
* Наследование (сколько может быть родителей? а как реализовать множественное наследование? восходящее и нисходящее преобразования)
* Полиморфизм: один интерфейс - множество реализаций
* Абстракция
* Я являюсь и я имею

## SOLID
* Single Responsibility (не делай god object)
* Open-closed
* Liskov substitution
* Interface segregation
* dependency injection

## Другие принципы хорошего кода
* KISS (keep it simple, stupid)
* DRY (dont repeat yourself)
* YAGNI (You Aren’t Gonna Need It)

# Spring Framework
* Что такое IoC контейнер, DI?

## Bean
* Что такое бин? xml объявление, @Bean, @Component, @ComponentScan
* Инжект @Autowired, через конструктор
* Циклическая зависимость бинов BeanCurrentlyInCreationException, как избежать? архитектура / lazy / не через конструктор(сеттер)

## Конктекст
* Configuration

## Scope
* Что такое scope? область жизни бина
* Основные scopes: singleton (по умолчанию), prototype, request, session, application, websocket

## Паттерны проектирования
* Builder
* Factory method, factory, abstract factory
* Proxy
* MVC
* Service locator
* Singletone

## Transactional

## AOP
* Зачем?
* Aspect, join point, pointcut, advice
* !!! Либы, отвечающие за это

## SpringBoot
* Автоконфигурация
* Стартеры

## Выполнение запросов
* Dispatcher servlet, определение контроллера, контроллер, view resolver, view
* filters, filterChain

## Spring security
* User, UserDetails, UserDetailsService
* Где может храниться пользователь
* Роли
* PasswordEncoder
* authorizeRequests
* фильтры: login, csrf, cors, logout, anonymous
* globalMethodSecurity: pre/postAuthorize
* SecurityContextHolder

# Hibernate
* Что такое ORM? JPA?
* Основные аннотации
* Object pool
* Связи
* проблемы Lazy/Eager для list
* проблема N+1 запроса

# SQL
* Синтаксис, назначение
* ACID
* having и where
* что такое индекс?
* group by

# REST
* Соглашение о путях
* Статус коды (200, 201, 202, 302, 400, 401, 403, 404, 405, 415, 500)
* Методы
* Отличия post/put/patch
* Как отделяется тело запроса?
* Зачем нужен заголовок host?
* Можно ли отправить тело запроса GET?
* Как отправляется форма? url-form-encoded
* json
* jwt, никаких сессий

# Наёбки
* Когда не выполнится finally? (System.exit, Error, while(true), не return!)
* Поддерживает ли язык Java множественное наследование? Java поддерживает множественное наследование типов, ведь интерфейс в нём может расширять другие интерфейсы. Но множественное наследование реализаций язык Java не поддерживает.
* 1.0/0.0 = Double.INFINITY
* Можно ли использовать return в конструкторе? да, но без возвращаемого значения
* Можно ли из конструктора бросить исключение? да
* Можно ли в конструкторе вызвать другой конструктор? да, this(). А несколько? нет. А не первой строчкой? нет
* Где лежат поля-примитивы у классов? на heap
* Finilize / finally / final?
* В чём отличие инициализации констант в конструкторе и при объявлении? время срабатывания
* Можно ли сделать static метод final ? да
* Что получим в int a = Integer.MAX_VALUE + 10;
* Скомпилится ли byte b1 = 1 + 3;
* Тип данных больше long (BigInteger)
* Может ли метод быть статическим и абстрактным одновременно? нет
* Можно ли использовать из статического метода нестатический? нет
* Может ли интерфейс быть final? нет
* Как сделать класс, экземпляр которого нельзя создать? private конструктор
* Можно ли в java сделать pointers? ссылки, как в cpp? нет

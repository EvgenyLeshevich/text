Inversion of Control(IoC) (инверсия управления) - это такой архитектурный подход, когда сущность не сама создаёт свои зависимости, а когда этой сущности зависимости поставляются извне.

Dependency injection(DI) - один из версий inversion of control (IOC, видов управления). DI - на практике осуществляется путём передачи параметров конструктора или с помощью сеттеров. Одним из ключевых компонентов Spring является AOP. Модуль Core - обеспечивает ключевые части фреймворка, включая свойства IOC and DI. Context построен на основе BEANS и CORE. Ключевым элементом Context является интерфейс ApplicationContext. 

Для управления компонентами используется DI. Эти объекты называются Spring Beans. Spring контейнер получает инструкции какие объекты инстанцировать и как их конфигурировать через метаданные. Метаданные могут быть получены 3мя способами:

    1. Xml
    
    2. Аннотации java
    
    3. Java code
    
В Spring имеется 2 различных вида контейнеров:

    1. bean factory - для базового функционала (Spring Core) (Прочитать про 2 реализации)
    
    2. application context - весь функционал Spring (Прочитать про 2 реализации)
    
Bean - объект под управлением IOС контейнера. Создаётся при помощи метадаты. 

В Spring существуют такие свойства определяющие Bean (Прочитать про остальные аттрибуты):

    1. Class (обязательный) - указывает java class который будет использоваться для создания Bean-a
    
    2. Name - уникальный идентификатор Bean-a (должен быть name или id)
    
    3. Scope - область видимости создаваемых объектов
    
!!!Прочитать про обласи видимости.

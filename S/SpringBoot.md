Spring Boot - полезный проект целью которого является упрощение создания приложения на основе Spring. Он обладает большим функционалом:

    1. Управление зависимостями
    2. Автоматическая конфигурация 
    3. Встроенные контейнеры сервлетов
    
Что бы ускорить процесс управления зависимостями Spring Boot неявно упакавывает необходимые сторонние зависимости для каждого типа приложения на основе Spring и предоставляет их посредством стартер-пакетов. 

Стартер - пакеты представляют собой набор удобных дискриптеров - зависимостей которые можно включить в своё приложение, это позволит получить универсальное решение для всех связанных со spring-технологиями. 

Автоматическое конфигурирование - после выбора подходящего стартер-пакета Spring Boot автоматически настраивает приложение на основе добавленных вами jar-зависимостей. 

Встроенная поддержка сервера приложений - контейнера сервлетов. Каждое Spring Boot ц=веб-приложение включает встроенный веб-сервер. 

Если нам нужно использоватьотдельных http-сервер нам нужно исключить зависимость по умолчанию.

Требования:
    
    1. Maven 3+
    2. Java 8+
    
Для создания Spring Boot - приложения во всех известных IDE существуют шаблоны под названием Spring Initializer. Но так же была создана визуальная платформа для создания таких приложений. 

@SpringBootApplication - в неё передаётся 

Actuator:

Это подпроект Spring Boot который позволяет разработчику следить за состоянием своего приложения с минимальным вложением. В него входят множество эндпоинтов которые вы можете вызвать и посмотреть различную статистику по своему веб-приложению в реальном времени 
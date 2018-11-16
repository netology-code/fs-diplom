# Дипломное задание по профессии "Веб-разработчик"

# Создание «информационной системы для администрирования залов, сеансов и предварительного бронирования билетов».

### Студенту предоставляются следующие компоненты системы:
	•	PHP-MVC-фреймворк для создания АПИ приложения
	◦	ORM
	◦	Работа с коллекциями
	◦	Контроллеры
	◦	Роутинг
	◦	Авторизация/регистрация, управление ролями, гостевой доступ
	◦	Работа с QR-кодами с примерами:
	▪	https://github.com/khanamiryan/php-qrcode-detector-decoder
	▪	http://phpqrcode.sourceforge.net/
	•	JS-фреймворк для создания клиентской части
	◦	Модели
	◦	Коллекции моделей
	◦	Методы CRUD для моделей и коллекций
	◦	Шаблонизация twig https://github.com/twigjs/twig.js
	•	Дизайн
	•	Верстка

## Задачи
	•	Реализовать клиентскую часть: административный интерфейс, бронирование и контроль билетов на основе готовой верстки с использованием предоставленного, расширяемого фреймворка
	•	Реализовать серверную часть ИС на основе предоставленного скелета MVC

## Сущности
Кинозал
Помещение, в котором демонстрируются фильмы. Режим работы определяется расписанием на день. Зал - прямоугольный, состоит из N * M различных зрительских мест.
Зрительское место
Место в кинозале. Зрительские места могут быть VIP и обычные. 
Фильм
Информация о фильме заполняется администратором. Фильм связан с сеансом в кинозале.
Сеанс
Сеанс - это временной промежуток, в котором в кинозале будет показываться фильм. На сеанс могут быть забронированы билеты.
Билет
Право посещения сеанса в кинозале. В билете обязательно указаны место, ряд, сеанс, qr-код c уникальным кодом бронирования. Билет действителен строго на свой сеанс.

## Роли пользователей системы
	•	Администратор
	•	Контроллер
	•	Гость

### Возможности администратора
	•	Создание/редактирование залов
	•	Создание/редактирование фильмов
	•	Настройка цен
	•	Создание/редактирование расписания

### Возможности пользователя
	•	Просмотр расписания
	•	Просмотр фильмов
	•	Выбор места в кинозале
	•	Бронирование билета

## Компоненты системы
	•	Интерфейс администратора — Раздел фронтенд-приложения доступный для администратора, позволяет настроить кинозалы, цены на билеты, расписание показа фильмов, а также запустить старт бронирования.
	•	Интерфейс гостя — Раздел фронтенд-приложения доступный для всех посетителей сайта, реализует просмотр расписания, выбор сеанса, времени,  возможность забронировать билет и распечатать код бронирования.
	•	Интерфейс контроллера — Раздел фронтенд-приложения доступный для контроллера и администратора. Позволяет загрузить qr-код и получить по нему информацию.
	•	АПИ — Бекенд-приложение с достаточным набором роутов для работы фронтенд-приложения


## Этапы разработки
	1.	Верстка недостающих элементов системы: форма создания фильма, форма создания зала, пагинация и фильтрация фильмов, форма авторизации в ИС, страница загрузки QR кода.
	2.	Реализация  базового АПИ: на данном этапе создается бекенд-приложение с возможностями работы с пользователями, авторизацией -  все роуты проверяются по средствам rest-клиента(для примера https://install.advancedrestclient.com/)
	3.	Создание базового фронтенд-приложения: на этапе создается основа приложения, разделяется на разделы для гостя и авторизованных пользователей, а также подключение к АПИ.
	4.	Итерационное наращивание функционала (Continuous Integration): Расширение функциональности приложения небольшими частями, включающими разработку моделей и контроллеров на бек и соответствующие формы на фронт.
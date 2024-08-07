## Validation tests project: Yandex Samokat 
<img src="https://img.shields.io/badge/Python-gray?style=flat" alt="Python" /> <img src="https://img.shields.io/badge/Pytest-gray?style=flat" alt="Pytest" /> <img src="https://img.shields.io/badge/Selenium-gray?style=flat" alt="Selenium" /> <img src="https://img.shields.io/badge/Allure-gray?style=flat" alt="Allure" />

В этом проекте я взяла учебное приложение Yandex Samokat, в котором можно заполнить форму и оформить заказ. Написала тесты на валидацию полей и ещё на некоторые функциональности, которые мы не трогали во время обучения.

Приложение: https://qa-scooter.praktikum-services.ru/

Для тестирования валидации вывела тестовые данные с помощью классов эквивалентности и граничных значений.
Нашла 19 багов, завела баг-репорты в YouTrack. Таблицу можно посмотреть здесь:  
https://docs.google.com/spreadsheets/d/1qHHQ9G-ho5Iwf2B5WdYUp_jT3wOugODe0AMoLHHsXko/edit?usp=sharing

### Содержание:
**locators** - папка с локаторами

**pages** - папка с методами веб-страниц по модели РОМ:

- **base_page** - базовые/общие методы
- **common_header** - методы «шапки»
- **main_page** - методы главной страницы
- **order_page** - методы формы заказа

**tests** - папка с тестами:

- **tests_validation** - тесты на валидацию полей ввода
- **test_common_header** - тесты «шапки»
- **test_main_page** - тесты главной страницы
- **test_order_page** - тесты страницы заказа

**assistant_methods.py** - файл со вспомогательными методами (генераторы и тд)

**conftest.py** - файл с с фикстурами

**data.py** - файл с данными проекта (тестовый пользователь, урлы, образцы сообщений об ошибке)

**requirements.txt** - внешние зависимости

**validation_test_data.py** - тестовые данные для полей ввода

**allure_results** - отчёты

### Что интересного удалось сделать:

- Все тесты параметризованы и отрабатывают в 2 браузерах - сначала в chrome, потом в firefox

- Подсветка поля проверяется с помощью JavaScript, получаем фактическое значение CSS-свойства border.

- Для тестирования поля «Дата доставки» написан вспомогательный метод, который берёт
текущую дату и добавляет (или отнимает) нужное количество дней

- Для тестирования поиска заказа по номеру написана фикстура, которая создаёт заказ через API, возвращает его номер и потом отменяет его.
Для неё написаны генераторы случайных корректных данных: Имя, фамилия, почта и тд.










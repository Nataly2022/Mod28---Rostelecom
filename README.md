Files
-----

[conftest.py](conftest.py) contains all the required code to catch failed test cases and make screenshot
of the page in case any test case will fail.

[pages/base.py](pages/base.py) contains PageObject pattern implementation for Python.

[pages/auth_page.py](pages/auth_page.py) authorization page for working with autotests.

[pages/registration_page.py](pages/registration_page.py) registration page for working with autotests.

[pages/elements.py](pages/elements.py) contains helper class to define web elements on web pages.

[autotests_rostelecom.py](autotests_rostelecom.py) contains Web UI tests for Rostelecom (https://b2c.passport.rt.ru/)



How To Run Tests
----------------

1) Install all requirements:

    ```bash
    pip install -r requirements.txt
    ```

2) Download Selenium WebDriver from https://chromedriver.chromium.org/downloads (choose version which is compatible with your browser)

3) Run tests:

    ```bash
    pytest -v --driver Chrome --driver-path /chromedriver autotests_rostelecom.py
    ```

Note:
~/chrome in this example is the file of Selenium WebDriver downloaded and unarchived on step #2.


Autotests description
-----
**test_start_page_is_correct**

Тест-кейс EXP-001 Корректное отображение "Стандартной страницы авторизации"


**test_location_of_page_blocks**

Тест-кейс EXP-002  Проверка элементов в левом и правом блоке страницы
Тест не проходит (Bugs-BR-001).Причина - расположение элементов на странице не соответствует ТЗ


**test_phone_tab**

Тест-кейс EXP-003 Проверка названия вкладки "Номер"
Тест не проходит (Bugs-03).Причина - Вкладка 'Номер' не соответствует ТЗ (вкладка "Телефон" вместо "Номер")


**test_registration_page_and_continue_button**

Тест-кейс EXP-004 Проверка названия кнопки "Продолжить" в форме "Регистрация"
Тест не проходит (Bugs-04). Причина - Кнопка должна иметь текст 'Продолжить'


**test_registration_page_with_empty_name_field**

Тест-кейс EXP-005 Регистрация пользователя с пустым полем "Имя", появления текста с подсказкой об ошибке


**test_registration_with_an_incorrect_value_in_the_name_field**

Тест-кейс EXP-006 Регистрация пользователя со значением в поле "Имя" меньше 2 символов, появление текста с подсказкой об ошибке


**test_registration_with_an_incorrect_value_in_the_last_name_field**

Тест-кейс EXP-007 Регистрация пользователя со значением в поле "Фамилия" превышающим 30 символов), появление текста с подсказкой об ошибке


**test_registration_of_an_already_registered_user**

Тест-кейс EXP-008 Регистрация пользователя с уже зарегистрированным номером, появление оповещения


**test_notification_form**

 Тест-кейс EXP-009 Проверка значка "х" - закрыть всплывающее окно оповещения
Тест не проходит (Bugs-BR-004). Причина - "Должна быть кнопка закрыть 'х'"


**test_incorrect_password_during_registration**

Тест-кейс EXP-010  При регистрации пользователя введен пароль содержащий менее 8 символов, появление текста с подсказкой об ошибке


**test_instead_of_cyrillic_invalid_characters**

Тест-кейс EXP-011 При регистрация пользователя в поле "Фамилия" введено значение, содержащее недопустимые символы вместо кириллицы



**test_password_and_password_confirmation_do_not_match**

Тест-кейс EXP-012 Значения в поле ввода "Пароль" и поле ввода "Подтверждение пароля" в форме "Регистрация" не совпадают


**test_invalid_email_or_mobile_phone**

Тест-кейс EXP-013 Не валидный email в поле ввода "Email или мобильный телефон" в форме регистрация


**test_authorization_of_a_user_with_an_invalid_password**

Тест-кейс EXP-014 Вход по неправильному паролю в форме "Авторизация" уже зарегистрированного пользователя, надпись "Забыл пароль"
перекрашивается в оранжевый цвет


**test_authorisation_valid**

Тест-кейс EXP-015 Тестирование аутентификации зарегестрированного пользователя



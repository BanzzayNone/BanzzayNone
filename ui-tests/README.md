
*   Автотесты на **Playwright + Pytest**. 
*   Проверка UI, валидации форм и авторизации.

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?logo=python&logoColor=white)]()
[![Playwright](https://img.shields.io/badge/Playwright-Latest-2EAD33?logo=playwright&logoColor=white)]()
[![Pytest](https://img.shields.io/badge/Pytest-Latest-0A9EDC?logo=pytest&logoColor=white)]()

---

# Основные команды для взаимодействия
При написании команд не забывать - pytest не знает что такое регистр.

```bash
## Установка зависимостей (из корня репозитория)
pip install -r requirements.txt
playwright install

## Запустить все тесты в этой папке
pytest ui-tests/Tests/test_risk_based.py -v
или
pytest

## Запуск конкретного теста
pytest -k "test_name_example"

## Запустить с отчётом
pytest ui-tests/Tests/test_risk_based.py --alluredir=allure-results && allure serve

## Проверить фикстуры
pytest --fixtures
```
---

# Структура и описание тестов

| № | Тест | Что проверяет | 
| :--- | :--- | :--- |
| 1 | `test_page_elements_present` | Проверка наличия элементов формы и скрывается ли пароль при вводе|
| 2 | `test_login_valid_credentials` | Вход с валидными данными, проверка отправки запроса и ответа на него + проверка токена |
| 3 | `test_login_invalid_username` | Вход с несуществующим логином |
| 4 | `test_login_empty_fields` | Проверка, что будет с страницей при входе без заполнения полей |
| 5 | `test_login_without_click` | Проверка фокуса на поле ввода логина и реакции на клавишу Enter |

*   Важно: Часть локаторов и запуск браузера с страницей и контекстом лежат в conftests.py, в качестве фикстур.


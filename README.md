# For English-speaking and other people from another country who do not understand Ukrainian
The full description of the entire plugin in English is in a separate branch
- Link: https://github.com/Vitalij3/admin-commands-plugin/tree/English

# Інформація
Якось давно (ні) у мене не було ідей для створення нового плагіну, і я запитав у Сергія (CergC)
щоб він підсказав якусь ідею він мені відповів щоб я створив плагін на блокування та глушіння!
І знаєте що? Я не знав БД але я зібрався і написав це все (до кого я звертаюсь..)
## Особливості
- Плагін працює на базі даних **sqlite3**
- Навіть коли плагін вимкнений умовно час буде іти

## налаштування
В нещодавному оновленні був доданий файл конфігурації шлях: ```src/main/resources/config/general.properties``` в якому є тільки один параметер який вказує часовий пояс.
### для чого?
В багатьох випадках користувачі беруть іноземні хостинги тим самим це робить часовий пояс
не сумісним з вашим, причина цього це те що в класі ```Calendar``` дата визначалася автоматично.

## Команди
- По традиції щоб не було конфліктів між назвами команд я додав початкове слово ``adm``
- Також в командах де потрібно увести дати можна увести ``#`` таким чином плагін візьме теперешнє
значення якогось елементу. Наприклад є час 2022 5 22 21 40 звичайно що це швидко набридає тому
це швидко можна вирішити написавши # # # 21 40 виходить як 2022 5 22 21 40.

# команди консолі
- ``admtimeban <playername/UUID> <year> <month> <date> <hour> <minute>`` - заблуковує гравця по заданому часі
- ``admtimeunban <playername/UUID>`` - розблуковує гравця
- ``admmute <playername/UUID> <year> <month> <date> <hour> <minute>`` - заглушує гравця по заданому часі
- ``admunmute <playername/UUID>`` - розглушує гравця
- ``admcurrentdate`` - дає повні дати з моменту коли ви написали команду
- ``admplayerstats <playername/UUID>`` - дає статистику гравця (час бану та муту)

# команди клієнта
до всіх **клієнтськіх** команд мають доступ тільки адмін
- ``admtimeban <playername/UUID> <year> <month> <date> <hour> <minute>`` - заблуковує гравця по заданому часі
- ``admtimeunban <playername/UUID>`` - розблуковує гравця
- ``admmute <playername/UUID> <year> <month> <date> <hour> <minute>`` - заглушує гравця по заданому часі
- ``admunmute <playername/UUID>`` - розглушує гравця
- ``admcurrentdate`` - дає повні дати з моменту коли ви написали команду
- ``admplayeruuid <playername>`` - дає **UUID** гравця (саме той індетифікатор який записується в БД)
- ``admplayerstats <playername/UUID>`` - дає статистику гравця в таблиці (час бану та муту)

# Компіляція
Щоб почати користуватися моїм плагіном вам потрібно його скомпілювати

## вимоги
- встановлений **Maven** на вашому комп'ютері
- завантажений **zip** архів вихідного коду

## процес компіляції
- відкрийте командний рядок в розархівованій теці **zip** архіву (якщо не розархівувавли розархівуйте)
- запишіть ``mvn install``
- в кінці збірки **jar** файлу в командному рядку має написати *build succes* та створитися тека *target*
- в теці **target** знайдіть **.jar** файл який буде мати приблизну назву *admin-commands-plugin-1.0-jar-with-dependencies.jar* - це і є плагін який відповідно ви можете використати для вашого серверу

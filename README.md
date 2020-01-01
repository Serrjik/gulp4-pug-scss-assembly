# Gulp v.4 сборка на шаблонизаторе Pug и SCSS для вёрстки проекта из нескольких страниц

Сборка на Gulp 4 на примере вёрстки 1 страницы блога.
[Посмотреть страницу](https://serrjik.github.io/gulp4-pug-scss-assembly/)
![Скриншот страницы](https://raw.githubusercontent.com/Serrjik/gulp4-pug-scss-assembly/master/page.jpg)

## Для чего использовать сборку?

Использовать сборку предполагается для вёрстки многостраничных сайтов. Используется шаблонизатор Pug для HTML-кода и препроцессор SCSS для CSS-стилей.

## Как устроена сборка?
* Исходные файлы проекта лежат в папке src. Конечные файлы падают в папку build. При запуске сборки папка build очищается.
* В данном репозитории папка build переименована вручную в папку docs для того чтобы можно было увидеть результат работы сборки на github pages.
* Настроено слежение и копирование: изображений (папка src\img), скриптов (папка src\js), иконок сайта (папка src\, файлы с расширением ico).
* Настроено автоматическое добавление префиксов CSS-свойств и создание карт исходных стилей (в каком SCSS-файле и в какой строке изначально было написано CSS-свойство).
* Контент страницы хранится в JSON-файле (html-data.json). Сборка настроена на использование только 1 такого файла, т.е. в нем должно быть всё вынесенное содержимое.
* Шрифты подключены через сайт Google Fonts.

## Как использовать сборку:

1. На компьютере должен быть установлен Node Package Manager.

2. Клонировать на локальный ПК репозиторий командой:

`git clone https://github.com/Serrjik/gulp4-pug-scss-assembly.git`

3. Для папки gulp4-pug-scss-assembly вызвать командную строку (например Git Bash), и ввести команду `npm i` для инициализации проекта. Подождать пока будут установлены необходимые пакеты.

4. Запустить сборку командой:

`gulp`

5. Сборка запустится вместе с демонстрационными данными. Нужно удалить ненужные для вашего проекта файлы и заменить содержимое основных файлов (main.scss, index.pug, main.js) своим.

6. Заменить содержимое контента страницы в JSON-файле (html-data.json) своим. Его содержимое из PUG'а доступно в переменной jsonData.

### Структура папок

1. В папке `src\pug` - PUG-шаблоны HTML-страниц сайта

    1. В папке `src\pug\layouts` - мастер-шаблоны страниц сайта, файл `_mixins.pug` - в него подключены все миксины. Сам он подключен ко всем страницам (чтобы подключение миксинов происходило в единственном месте и не приходилось следить за их подключением на каждой странице отдельно).
    1. В папке `src\pug\mixins` - все миксины
    1. В папке `src\pug\pages` - страницы сайта
    1. В папке `src\pug\sections` - секции (крупные одинаковые блоки PUG кода, в которые не нужно передавать переменные). Соответствуют крупным блокам HTML-кода (шапка сайта, подвал сайта, пагинация, виджет).

2. В папке `src\scss` - SCSS стили

3. В папке `src\img` - картинки сайта

4. В папке `src\js` - скрипты сайта

5. В корне папки `src` находятся файлы иконок сайта `favicon` - расширение `.ico`

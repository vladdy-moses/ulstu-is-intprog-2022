# Лабораторная работа №B1 - Изучение шаблона проектирования MVC

## Цель работы

Понимание шаблона проектирования MVC и его применения при проектировании интернет-приложений.

## Ход выполнения работы

Необходимо вспомнить, что говорилось на лекции про данный шаблон проектирования.

Также крайне рекомендуется осознать материал отсюда:

- <https://metanit.com/sharp/aspnet6/>;
- <https://docs.microsoft.com/ru-ru/aspnet/core/mvc/overview?view=aspnetcore-7.0>.

Что следует понять из представленных выше и, возможно, каких других статей:

1. Какие есть компоненты в шаблоне MVC и как они зависят друг от друга.
2. Как реализуется шаблон в ASP.NET Core.
3. Как создавать контроллеры и представления для них.
4. Где находится общий шаблон всех представлений и как его подключить.
5. Как передаются параметры на действия контроллера.
6. Что такое `wwwroot` и как использовать файлы из этой директории в веб-приложении.

Что необходимо сделать для выполнения лабораторной работы:

1. Создать приложение ASP.NET Core (Model-View-Controller).
   Можно создать как через `dotnet new mvc -o test-mvc-proj`, так и через интерфейс Visual Studio.
2. Скопировать скрипты, изображения и таблицы стилей в `wwwroot`.
   Контент, который уже есть в этой папке, можно удалить.
3. Заменить мастер-шаблон сайта на ваш шаблон из лабораторных работ по блоку front-end.
   Как вы могли заметить, в замечаниях преподаватель всегда старался указать, что все страницы вашего веб-сайта должны выглядеть похожим образом.
   Такой подход помогает потом "натянуть" вёрстку на веб-приложение как раз благодаря единому мастер-шаблону.
   Если же у Вас несколько разных видов дизайна сайта (например, отдельно для главной страницы и для других), можно сделать несколько мастер-шаблонов.
4. Создать контроллеры и действия в них по смыслу тех страниц, что вы сверстали.
   Например, страницы входа и регистрации можно преобразовать в действия `Signin` и `Signup` в контроллере `Account` (класс будет называться `AccountController`).
   Страницы по заказу можно поместить в контроллер `Order`.
   Главная страница - это по умолчанию действие `Index` в контроллере `Home`.
   Страницы "О сайте", "Контакты" и аналогичные также рекомендуется размещать в контроллере `Home`.
5. Создать представления, связанные с действиями контроллеров.
   Получить доступ к отображению представлений определённых действий можно следующим образом: `{адрес-сайта}/{контроллер}/{действие}`.
   Действие `Index` и контроллер `Home` можно опускать из адреса.
   Например, адрес сайта - <http://localhost:5000/> или <https://localhost:5001/>.
   В этом случае главную страницу можно открыть по адресам <http://localhost:5000/>, <http://localhost:5000/Home/> или <http://localhost:5000/Home/Index>.
   Страница регистрации тогда будет доступна по адресу <http://localhost:5000/Account/Signup> и никак иначе.
6. Заполнить представления разметкой из статических файлов.
   Как можете догадаться, вставлять надо не полную разметку файла, а только отличающуюся у страниц часть для `RenderBody`.
7. Изменить ссылки (в меню, на страницах сайта) на новые.
   Можно использовать новую возможность ASP.NET Core - TagHelpers.
   [Пример использования TagHelper для ссылок тут](https://docs.microsoft.com/ru-ru/aspnet/core/mvc/views/tag-helpers/built-in/anchor-tag-helper?view=aspnetcore-7.0#asp-controller).
8. Ещё раз проверить, что сайт запускается.
9. Продемонстрировать работу приложения на лабораторном занятии и ответить на вопросы преподавателя.

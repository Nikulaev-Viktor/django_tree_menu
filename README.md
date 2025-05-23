# Django Древовидное Меню

Переиспользуемое Django-приложение для отображения древовидных (иерархических) меню с поддержкой:
- Редактирования через админку
- Именованных URL и произвольных путей
- Подсветки активного пункта по текущему URL
- Раскрытия только активной ветки
- Эффективного запроса к БД (всего один)

---

## 🔧 Возможности

- Иерархическая структура меню (родитель → потомок)
- Управление меню и пунктами через админку
- Метод `get_absolute_url()` с поддержкой `named_url` и `url`
- Определение активного пункта и автоматическое раскрытие ветки
- Template tag `{% draw_menu %}` для вставки в шаблон
- Только один запрос к БД на отрисовку меню

---

## Что реализовано по техническому заданию
✅ Древовидная структура в БД через parent

✅ Template tag для отрисовки меню

✅ Подсветка активного пункта по текущему пути

✅ Раскрытие только активной ветки

✅ Управление через админку

✅ Один SQL-запрос на всё меню

## 🚀 Установка и запуск

```bash
git clone https://github.com/yourusername/django-tree-menu.git
cd django-tree-menu
pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver

Пример настройки через админку
Создайте меню
Название: main_menu

Добавьте пункты меню

Название	Родитель	Named URL / URL
Главная	        –	         named_url = index
Услуги	        –	         url = /services/
Веб-
разработка         Услуги	  url = /services/web/
SEO-
оптимизация	   Услуги	url = /services/seo/

## Category: Категория 

> Пример объекта

```json
{
    "id": 17,
    "name": "Китайский чай",
    "color": "white",
    "hidden": 0,
    "delete": 0,
    "parent": 13,
    "picture": "",
    "sortOrder": 999,
    "subCategories": [1, 2],
    "extras": {}
}
```

### Свойства

Свойство | Описание
-------- | --------
id | Id категории
name | Название
color | Цвет
hidden | 1 — категория скрыта в заведении, 0 — категория не скрыта
delete | 1 — категория удалена, 0 — категория не удалена
parent | Id родительской категории, в которой находится текущая категория
picture | URL картинки категории
sortOrder | Порядок сортировки на терминале
subCategories | Массив подкатегорий которые находятся в текущей категории
extras | Список extras установлены для категории. Extras можно установить методом [application.setEntityExtras](https://dev.joinposter.com/docs/v3/web/application/setEntityExtras).

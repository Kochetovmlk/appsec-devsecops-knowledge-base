# Лаборатория: Незащищенные административные функции

В этой лаборатории используется незащищенная панель администратора.

Решите лабораторную работу, удалив пользователя carlos.

Ход работы:

Делаем проверку url-подмены домена 2-ого уровня:

Проверяем `admin`, `administrator` и `robots.txt`:

![PortSwigger](../Drawing/Drawing_7.png)


Видим Disallow: /administrator-panel, пробуем проверить:

![PortSwigger](../Drawing/Drawing_8.png)

Удаляем пользователя:

![PortSwigger](../Drawing/Drawing_9.png)

Успех!

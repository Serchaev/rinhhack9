# rinhhack9
# ЛЮДЬиЧЕЛОВЕКИ

**Файлы preds.csv лежат в папках model_preds и manual_preds.**

manual_preds - результаты ручной разметки на основе проведенного анализа датасета (1.0).

model_preds - результаты предиктов модели (0.9978).

Проект состоит из нескольких репозиториев.

0. https://github.com/Serchaev/rinhhack9-infra Инфраструктура. Postgres и redis.
1. https://github.com/Serchaev/rinhhack9-imitator Имитатор транзакций. Шлет в редис данные из датасета.
2. https://github.com/Serchaev/rinhhack9-model-manager Модел менеджер. Читает редис, прогоняет данные через модель и отправляет в редис на чтение бэкенду. Имеет ручку *"/model"* для предикта своей записи (кидаешь параметры на вход, на выходе получаешь предикт).
3. https://github.com/Serchaev/rinhhack9-backend Бэкенд. Читает редис, сохраняет данные и предикт в бд. Кидает в сокет для чтения фронту.
4. https://github.com/loqiemon/rinhack-24 Фронтенд. 

**Чтобы поднять проект, необходимо**

1)поднять docker compose из репозитория инфраструктуры.

2)поднять все остальные репозитории через docker compose.

Настройка конфигурации производится через динаконф. Файл конфига лежит в каждом репозитории config/settings.yml


# Домашнє завдання 4: Olist у PostgreSQL

## Дані

Джерело: [Olist Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce). Notebook завантажує CSV через `kagglehub` із публічного набору `olistbr/brazilian-ecommerce`; у середовищі запуску може знадобитися доступ до Kaggle. Варіант із курсовим архівом позначено в ноутбуці коментарем: для нього слід розпакувати CSV й один раз задати `dataset_dir` для свого середовища. Автоматичного перемикання на локальну папку код не робить.

| CSV | Raw-таблиця | Typed-таблиця | Рядків |
| --- | --- | --- | ---: |
| `olist_customers_dataset.csv` | `olist_customers_raw` | `olist_customers` | 99 441 |
| `olist_orders_dataset.csv` | `olist_orders_raw` | `olist_orders` | 99 441 |
| `olist_order_items_dataset.csv` | `olist_order_items_raw` | `olist_order_items` | 112 650 |
| `olist_products_dataset.csv` | `olist_products_raw` | `olist_products` | 32 951 |
| `olist_sellers_dataset.csv` | `olist_sellers_raw` | `olist_sellers` | 3 095 |
| `olist_order_reviews_dataset.csv` | `olist_order_reviews_raw` | `olist_order_reviews` | 99 224 |

Додаткові таблиці: `olist_customer_dim`, `customer_segments`, `seller_score`, `seller_alerts`. Розмір вибірки — 99 441 замовлення; кількості вище наведені для використаної копії CSV.

## Запуск

1. Відкрийте `goit_rdb_hw_04.ipynb` у Google Colab.
2. Забезпечте доступ до Kaggle для `kagglehub` або налаштуйте закоментований варіант із курсовим архівом та `dataset_dir`.
3. Оберіть **Runtime → Restart and run all**. Перша клітинка встановить залежності, запустить `pgserver` і покаже версію PostgreSQL.
4. Notebook створить raw- і typed-таблиці, виконає DML та аналітичні запити. Кількості raw-таблиць друкуються під час завантаження CSV; окремий smoke test показує кількості typed-таблиць для порівняння.

У ноутбуці збережено outputs клітинок. За використання KaggleHub шляхи до CSV підставляються автоматично; після налаштування доступу SQL не потребує ручних правок.

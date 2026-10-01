# Домашнє завдання 4: Olist у PostgreSQL

## Що в репозиторії

- `goit_rdb_hw_04.ipynb` — ноутбук з усіма завданнями і збереженими outputs клітинок.
- `README.md` — цей файл.

## Дані

Джерело: [Olist Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) на Kaggle (`olistbr/brazilian-ecommerce`).

CSV-файли в репозиторій не додані. Ноутбук сам завантажує їх через `kagglehub`, тому окремо нічого качати не треба. Якщо `kagglehub` не працює (наприклад, немає доступу до Kaggle), можна скачати архів вручну за посиланням вище, розпакувати CSV у `data/olist/` і в другій клітинці ноутбука розкоментувати рядок з `dataset_dir`, вказавши шлях до цієї папки.

Використано шість CSV із набору:

| CSV | Raw-таблиця | Typed-таблиця | Рядків |
| --- | --- | --- | ---: |
| `olist_customers_dataset.csv` | `olist_customers_raw` | `olist_customers` | 99 441 |
| `olist_orders_dataset.csv` | `olist_orders_raw` | `olist_orders` | 99 441 |
| `olist_order_items_dataset.csv` | `olist_order_items_raw` | `olist_order_items` | 112 650 |
| `olist_products_dataset.csv` | `olist_products_raw` | `olist_products` | 32 951 |
| `olist_sellers_dataset.csv` | `olist_sellers_raw` | `olist_sellers` | 3 095 |
| `olist_order_reviews_dataset.csv` | `olist_order_reviews_raw` | `olist_order_reviews` | 99 224 |

Вибірка не скорочувалась: використано повний набір, 99 441 замовлення за 2016–2018 роки. Крім таблиць вище, ноутбук створює `olist_customer_dim`, `customer_segments`, `seller_score` і `seller_alerts`.

## Запуск

1. Відкрийте `goit_rdb_hw_04.ipynb` у Google Colab.
2. Змініть версію середовища виконання: **Runtime → Change runtime type → Runtime version → 2026.04** (в українському інтерфейсі: **Середовище виконання → Змінити тип середовища виконання → Версія середовища виконання**) і натисніть **Save**. На цій версії ноутбук перевірено.
3. Переконайтеся, що `kagglehub` має доступ до Kaggle, або підключіть локальні CSV через `dataset_dir`, як описано вище.
4. Запустіть **Runtime → Restart and run all**. Перша клітинка встановить залежності, підніме `pgserver` і виведе версію PostgreSQL.
5. Далі ноутбук створить raw- і typed-таблиці та виконає всі запити. Після завантаження CSV друкується кількість рядків у raw-таблицях, а smoke test показує кількість у typed-таблицях, щоб їх можна було порівняти.

Ручних правок у SQL чи шляхах не потрібно: при `kagglehub` шлях до CSV підставляється автоматично.

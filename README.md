# Асинхронный парсер, который скачивает бюллетень по итогам торгов с сайта биржи


### ссылка на <a href=https://spimex.com/markets/oil_products/trades/results/>сайт</a>
### ccылка на <a href="https://github.com/ilia010310/parser_spimex">снхронную версию</a>

---

#### Достает из бюллетени необходимые столбцы (забрать только данные из таблицы «Единица измерения: Метрическая тонна», где по столбцу «Количество Договоров, шт.» значения больше 0)
- Код Инструмента (exchange_product_id)
- Наименование Инструмента (exchange_product_name)
- Базис поставки (delivery_basis_name)
- Объем Договоров в единицах измерения (volume)
- Объем Договоров, руб. (total)
- Количество Договоров, шт. (count)

#### Сохраняет полученные данные в таблицу «spimex_trading_results» со следующей структурой:

- id
- exchange_product_id 
- exchange_product_name
- oil_id - exchange_product_id[:4]
- delivery_basis_id - exchange_product_id[4:7]
- delivery_basis_name
- delivery_type_id - exchange_product_id[-1]
- volume
- total
- count
- date
- created_on
- updated_on

---

#### * Необходимо создать базу данных, которая будет хранить информацию по итогам торгов начиная с 2024 года.

- Время выполнения асинхронным способом получилось 7 минуты 34 секунды.
- Разница в скорости выполнения со синхронным - примерно 19 минут, в пользу асинхронного.






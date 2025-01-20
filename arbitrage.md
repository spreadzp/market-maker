# Арбитражная система

## Структура данных

### Orders (Ордера)

Структура для хранения ордеров на CEX и DEX биржах.

#### Пример:

```json
// Ордер на CEX
{
    "pair_id": 1,
    "exchange_id": 1,
    "type": "buy",
    "price": 50000,
    "amount": 1,
    "status": "open",
    "created_at": "2023-10-01 12:00:00"
}

// Ордер на DEX
{
    "pair_id": 1,
    "exchange_id": 2,
    "type": "sell",
    "price": 50500,
    "amount": 1,
    "status": "open",
    "created_at": "2023-10-01 12:00:00"
}
```

### OrderBook (Книга ордеров)

Структура для хранения состояния книги ордеров на биржах.

#### Пример:

```json
// Ордербук на CEX
{
    "pair_id": 1,
    "exchange_id": 1,
    "bid_price": 49900,
    "ask_price": 50000,
    "bid_amount": 10,
    "ask_amount": 5,
    "timestamp": "2023-10-01 12:00:00"
}

// Ордербук на DEX
{
    "pair_id": 1,
    "exchange_id": 2,
    "bid_price": 50400,
    "ask_price": 50500,
    "bid_amount": 8,
    "ask_amount": 6,
    "timestamp": "2023-10-01 12:00:00"
}
```

### Prices (Цены)

Структура для хранения исторических данных о ценах на разных биржах.
Поле `exchange_id` используется для привязки цены к конкретной бирже.

#### Пример:

```json
// Цена на CEX
{
    "pair_id": 1,
    "exchange_id": 1,
    "price": 50000,
    "timestamp": "2023-10-01 12:00:00"
}

// Цена на DEX
{
    "pair_id": 1,
    "exchange_id": 2,
    "price": 50500,
    "timestamp": "2023-10-01 12:00:00"
}
```

### ArbitrageOpportunities (Арбитражные возможности)

Структура для отслеживания арбитражных возможностей между биржами.

#### Пример:

```json
{
    "pair_id": 1,
    "cex_exchange_id": 1,
    "dex_exchange_id": 2,
    "cex_price": 50000,
    "dex_price": 50500,
    "profit": 500,
    "timestamp": "2023-10-01 12:00:00"
}
```
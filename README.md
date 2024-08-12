# Практические задания по вебинару о TypeScript

## Задание 1. Переписать js код под ts

В блоке ниже находится абстрактный код, позволяющий работать с набором товаров в магазине. 
В рамках данного задания необходимо типизировать все функции, переменные и описать необходимые типы объектов.

Код не должен содержать ошибок от TypeScript.

```js
/** Создаёт магазин с набором товаров,по умолчанию возвращает пустой массив */
function createShopCollection(items = []) {
  return items;
}

/** Создаёт товар магазина */
function createShopItem(item) {
  const data = {
    id: Math.floor(Math.random() * 100_000),
    title: item.title,
    description: item.description,
    price: item.price,
    amount: item.amount,
    isAvailable: item.isAvailable,
  };
  return data;
}

/** Поиск товара в магазине по id */
function findShopItemById(shop, id) {
  return shop.find((item) => item.id === id);
}

/** Возвращает массив со всеми доступными товарами в магазине */
function getShopAvailableItems(shop) {
  return shop.filter((item) => item.isAvailable);
}

/** Устанавливает количество определённого товара в магазине */
function setShopItemAmount(shop, id, amount) {
  const item = findShopItemById(shop, id);
  item.amount = amount;
}
```

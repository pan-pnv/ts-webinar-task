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
## Задание 2. Реализовать класс для шифрования строк на TypeScript.

В рамках задания нужно реализовать класс для шифрования и расшифровки строк согласно шифру Цезаря.

Ссылка на ознакомление с шифром Цезаря: \
https://ru.wikipedia.org/wiki/%D0%A8%D0%B8%D1%84%D1%80_%D0%A6%D0%B5%D0%B7%D0%B0%D1%80%D1%8F

Требования к задаче:
- Для шифрования/расшифровки должен быть создать классс `EncryptionService`;
- При инициализации класса `EncryptionService` должна быть возможность указать сдвиг, по умолчанию он равен 3;
- Должна быть поодержка шифрования строк с кириллическими и латинскиими символами, специальные символы (пробелы, точки и пр.) остаются без изменений;
- При шифровании и расшифровки должен сохраняться регистр символов;

Пример работы класса `EncryptionService`:
```ts
const service = new EncryptionService(3);

const encodedString = service.encode("Hello world!");
console.log(encodedString);  // Выведет "Mjqqt btwqi!"

const decodedString = service.decode(encodedString);
console.log(decodedString);  // Выведет "Hello world!"
```

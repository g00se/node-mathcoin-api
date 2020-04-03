# mathcoin-api
MathCoin API Node js package


Создать апи ключ - https://m.vk.com/app6995668#create_merchant

Установить
```javascript
npm i mathcoin-api
```


Использование
```javascript
const MathCoinAPI = require ('mathcoin-api');
const api = new MathCoinAPI('апи ключ','vk id бота');
```

Функции

# Получить ссылку на перевод
@summa - сумма
```javascript
let transfer_link = api.get_link(summa);
```


# Получить список переводов
@last_tx_id - номер последнего перевода после которого показать переводы

```javascript
api.txList(last_tx_id,(err,resp)=>{
if(err) return;
if(resp.length>0){
  console.log('Получено '+resp.length+' транзакций');
}
});
```

# Узнать баланс

@id - чей баланс узнать
@cb - ответ от сервера
```javascript
  api.score(1234 ,(score)=>{
    console.log('Получен баланс: '+score);
  });
```
# Отправить коины

```javascript
api.send(1234, 10000, (res)=>{
  console.log('Результат отправки: '+res['success']);
});
```

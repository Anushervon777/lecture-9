# Асинхронӣ ва Синхронӣ дар JavaScript

## Муқаддима

# Дар JavaScript, иҷрои код метавонад синхронӣ ё асинхронӣ бошад. Фаҳмидани ин консепсияҳо барои навиштани кодҳои самаранок ва иҷроишӣ муҳим аст.

## JavaScript-и Синхронӣ

**Дар барномасозии синхронӣ, амалҳо як ба як иҷро мешаванд. Ҳар як амалиёт бояд пеш аз оғози амалиёти навбатӣ ба итмом расад. Ин метавонад ба рафтори "блоккунӣ" оварда расонад, ки вазифаҳои тӯлонӣ иҷрои вазифаҳои баъдиро бозмедоранд.**

### Мисол
```javascript
console.log('Аввал');
console.log('Дуввум');
console.log('Севвум');
```
```
function fetchData(callback) {
    setTimeout(() => {
        callback('Маълумот гирифта шуд!');
    }, 2000);
}

fetchData(data => {
    console.log(data);
});
```
---
```
function fetchData() {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve('Маълумот гирифта шуд!');
        }, 2000);
    });
}

fetchData().then(data => {
    console.log(data);
});
```
```
function fetchData() {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve('Маълумот гирифта шуд!');
        }, 2000);
    });
}

async function main() {
    const data = await fetchData();
    console.log(data);
}

main();
```

HTTP ва HTTPS протоколҳои асосии веб мебошанд. API ба барномаҳо имкон медиҳад бо ҳамдигар муошират кунанд, ва REST API яке аз меъёрҳои маъмул барои ин кор мебошад. Бо истифода аз JavaScript, мо метавонем ба осонӣ бо API-ҳо кор кунем ва маълумотро интиқол диҳем.
```
// HTTP GET барои гирифтани маълумот
fetch('https://api.example.com/items')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));

// HTTP POST барои фиристодани маълумот
fetch('https://api.example.com/items', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({ name: 'Item' })
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```
# HTTP, HTTPS, API ва REST API дар JavaScript

## Муқаддима

# Интернет асосан ба воситаи протоколҳои HTTP ва HTTPS кор мекунад. Бо истифода аз API-ҳо (Application Programming Interface) барномаҳо метавонанд бо ҳамдигар муошират кунанд. REST API яке аз меъёрҳои маъмул барои сохтан ва истифода бурдани API-ҳо мебошад.

## HTTP ва HTTPS

**HTTP (HyperText Transfer Protocol) протокол барои интиқоли маълумот дар веб мебошад. HTTP пайвастагии осебпазир аст ва маълумотро бе рамзгузорӣ интиқол медиҳад.**

**HTTPS (HyperText Transfer Protocol Secure) як версияи амншудаи HTTP мебошад. HTTPS маълумотро рамзгузорӣ мекунад, ки ин бехатарии онро таъмин мекунад.** 

### Мисол бо HTTP дар JavaScript
```javascript
fetch('http://example.com/data')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));
```

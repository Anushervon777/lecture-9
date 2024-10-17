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

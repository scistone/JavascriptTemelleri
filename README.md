# Javascript Temelleri - Veri Tipleri, Objeler ve Operatörler
Türkçe javascript temelleri dökümantasyonu


## Javascript Nedir ? 
JavaScript oldukça hızlı ve kolay bir şekilde öğrenilebilir ve web sitelerinin işlevini arttırmaktan oyunlar çalıştırmaya kadar çoğu amaç için kullanılabilir. Dahası, Github gibi siteler sayesinde ücretsiz olarak bir çok JavaScript taslağı ve uygulaması bulabiliriz

## Javascript'i HTML içine import etmek

İçine import edeceğimiz html dosyasıyla aynı klasör içerisinde app.js adında bir dosya oluşturuyoruz.
Daha sonra HTML dosyamızın içerisine:

```javascript
<script src="app.js"> </script>
```
src anahtar kelimesi ile app.js'in yolunu göstererek import edebiliriz.

## Javascript Temel Fonksiyonlar

Sayfada uyarı bastırmak için:
```javascript
alert("Merhaba Dünya");
```

Konsolda yazı bastırmak için:
```javascript
console.log("Merhaba Dünya");
```
Değişken tanımlamak:
```javascript
var a = 20;
```
Veri tipini öğrenmek için:
```javascript
var a=20;
console.log(typeof a);
```
Konsolda uyarı bastırmak için:
```javascript
console.warn("Bu bir uyarıdır.");
```
Konsolda hata bastırmak için:
```javascript
console.error("Bu bir hatadır.");
```
Yorum satırı yazmak için:
```javascript
console.log("Merhaba Dünya")
// console.log("Merhaba Dünya")   Bu bir yorum satırıdır.
veya
/*
console.log("Merhaba Dünya")      Bu da bir yorum satırıdır.
*/
```

## Javascript Değişkenleri
Javascript değişkenlerini tanımlarken bazı dikkat edilmesi gereken durumlar vardır:
#### 1. Değişken isimleri sayı ile başlayamaz
```javascript
1sayi=1;  //yanlış kullanım

sayi1=1;  //doğru kullanım

```
#### 2. Değişken isimleri $ ya da _ ile başlayabilir.
```javascript
$sayi1=1;  //doğru kullanım

_sayi1=1;  //doğru kullanım
```
#### 3. JavaScript dilinde değişken tanımlanırken ```var```,```let``` veya ```const``` ifadesi kullanılır.
```javascript
var a = 1;   //doğru kullanım

var b = 2;   //doğru kullanım
```
Ayrıca var ifadesi ile tek satırda birden fazla değişken tanımlanabilir.
```javascript
var a = 5, var b = 12, var c = 20;
```
## Javascript Veri Tipleri
Javascript'te iki tür veri tipleri bulunmaktadır: 

1. Primitive Veri Tipleri
2. Reference Veri Tİpleri


### 1. Primitive(İlkel) Veri Tipleri

```javascript
var a = 30;                 Number Veri Tipi(Sayısal)
var b = 3.14;               Number Veri Tipi(Sayısal)
-------------------------------------------------
var name = "Ahmet";         String Veri Tipi(Metin)
-------------------------------------------------
var x= true;                Boolean Veri Tipi(Mantıksal)
-------------------------------------------------
var y=null;                 null(hiçbir değer taşımayan) veri tipi
-------------------------------------------------
var a;                      undefined veri tipi
```

### 2. Reference(Referans) Veri Tipleri
Referans veri tiplerinin hepsi obje tipindedir.
```javascript
var numbers=[1,2,3,4,5];     Array Verisi(Dizi)
-------------------------------------------------
var person={
    name:"Ahmet Değer",      
    age :22
};                           Veri İkilileri (Nesneler)                           
-------------------------------------------------
var date = new Date();       class veri tipi
-------------------------------------------------
var merhaba = function(){
    console.log("Merhaba");
};                           function veri tipi
```

#### Değişkenlerin veri tipini değiştirmek
JavaScript veri türleri yeni değerler atanarak kolayca değiştirilebilir. Aşağıda a değişkeni içerisinde bulunan değer yeni bir değer almıştır.
```javascript
var a;          // a null    bir değer aldı.

var a= "deger"; // a string  bir değer aldı.

var a= 1998;    // a sayısal bir değer aldı.

var a=null;     // a null    bir değer aldı.
```

#### Veri Türünü Tespit Etmek (typeof)
Typeof operatörü kullanılarak bir değişkenin türü sorgulanabilir.
```javascript
typeof “deger”;                                //string

typeof “123”;                                  //number

typeof true;                                   //boolean

typeof [1855,4785,5412,5698];                  //object

typeof {isim: "scistone", içerik:"eğitim"};    //object
```

#### Array veri tipi olan değişkeni başka bir değişkene eşitlemek
Öncelikle a array'ini tanımlıyoruz.
```javascript
var a = [1,2,3];
```
daha sonra b diye bir veri tipi oluşturup a değişkenine eşitliyoruz.
```javascript
var b = a;
```
a array'i içerisine yeni bir eleman ekliyoruz.
```javascript
a.push(4);
```
normalde beklediğimiz sadece bu değeri a array'inin içerisine eklemesi ama javascriptte 
çalışma mantığı biraz daha pointer mantığına benzer şekilde işlediği için, a array'ine eklenen 4 değeri aynı zamanda b array'i içine de eklenir.

---
### let anahtar kelimesi
let anahtar kelimesi var gibi iki defa tanımlanan bir anahtar kelime değildir. Bu yüzden let anahtar kelimesi ile tanımladığımız değişkenleri tekrardan declare edemeyiz.

```javascript
let name= "Ahmet Değer";
let name= "Deger";   // yazarsak eğer SyntaxError verecektir.
```

### const anahtar kelimesi
const anahtar kelimesi ile oluşturulan değişkenler ekrardan tanımlanamaz. Fakat primitive değil de bu değişkenimizin veri tipinin array olduğunu varsayarsak. Bu array'e dışarıdan push methodu ile yeni bir değişken ekleyebiliriz. Çünkü push methodu değişkenin gösterdiği yer değişmez. Yeniden bir değer ataması yapılmıyor
```javascript
const a = [1,2,3,4]

a.push(5)       //doğru kullanım

a = [1,2,3,4,5] //yanlış kullanım hata mesajı dönecektir.
```

aynı zamanda const anahtar kelimesi ile undefined değerli bir değişken oluşturulamaz.

```javascript
const a;    //yanlış kullanım
```

## Veri Tiplerini Birbirine Dönüştürme

```javascript
let value;

// Veritiplerini String'e Çevirme

value = String(123);
value = String(3.14);
value = String(true);
value = String(function(){console.log()});
value = String([1,2,3,4]);

value = (10).toString();
value = (3.14).toString();

// Veritiplerini Sayılara Çevirme

value = Number("123");
value = Number(null);               // 0 değeri döndürür
value = Number(undefined);          // NaN
value = Number("Hello World");      // NaN

value = Number("3.13");
value = parseFloat("3.14");

value = parseInt("3");

const a = "Hello" + 34;             // Hello34
```

## Operatörler ve Math Objesinin Metodları

```javascript

value = Math.PI;                // pi sayısını verir
value = Math.E;                 // e sayısını verir
value = Math.round(3.6)         // yakın olan tarafa yuvarlar

value = Math.ceil(3.2)          // yukarı yuvarlama
value = Math.floor              // aşağı yuvarlama
value = Math.sqrt(16)           // karekökü
value = Math.abs(-16)           // Mutlak değer
value = Math.pow(8,3)           // 8 üzeri 3
value = Math.max(10,-1,100,32); // verilen *args daki en büyük değeri bulur.
value = Math.min(10,-1,100,32); // verilen *args daki en küçük değeri bulur.
value = Math.random();          // 0 ile 1 arası 0 dahil ama 1 dahil değil
value = Math.random() *20 ;     // 0 ile 20 arasında
value = Math.random() * 20+1;   // 1 ile 21 arasında  
```
## String Metodları
```javascript
const firstName = "Louis";
const lastName  = "Armstrong";
const langs = "Java,Python,C++"
let value = firstName.lenght;                           // stringin uzunluğu verir

value = firstName.concat(" ",lastName," ","adamdır.");  // concat methodu ile bir stringi birden fazla string ifadesi ile toplayabiliriz.
value = firstName.toLowerCase();
value = firstName.toUpperCase();

value = firstName.indexOf("L");                         // L yi arar; bulur ise index konumunu verir.
value = firstName[3] === firstName.charAt(3);           // 2 kullanım da 4. değeri value'ya atar

value = firsName.split("o"); // stringteki o yu çıkarır çıkardığı yerden bölüp yeni bir array olarak tanımlar.  ["L","uis"]

value = firsName.replace("s","z");  // value, Louiz olarak tanımlanır.
value = langs.includes("Java");     // stringin içinde verilen argümanı arar eğer verilen argüman stringin içinde var ise true boolean değer döner yoksa false.

```
## Template Literal - String
```javascript
const name = "Berk";
const department = "Bilişim";
const salary = 30000;

const a = `İsim:${name}\nDepartman:${department}\nMaaş:${salary}`;

function a(){
    return "Merhaba";
}

const html = `
    <ul>
    <li>${name}</li>
    <li>${department}</li>
    <li>${salary}</li>
    <li>${10/4}</li>
    <li>${a()}</li>
    </ul>
`;

document.body.innetHTML = html ;  //js kodu html sayfamıza çağırıldı
```

## Arraylerin Özellikleri 

```javascript
let value;

const numbers = [43,56,33,23,44,5];

const langs = ["Python","C","Java","Javascript"];

const a = ["Merhaba",22,null,undefined,3.14]; // array içine farklı veri tiplerindeki değerleri verebiliriz.

value = numbers.length;
value = numbers[0];

value = numbers[numbers.length -1];           // numbers arrayini son elemanı

numbers[2] = 1000;                  // herhangi bir indeksteki değeri değiştirme

numbers.indexOf(1000);              // 1000 2. indekste olduğu için 2 dönecektir.

numbers.push(2000);     // array'in sonuna eleman ekleme
numbers.unshift(3000);  // array'in başına eleman ekleme

numbers.pop();          // array'in son elemanını array'den çıkartacaktır.

numbers.shift()         // array'in başındaki elemanı array'den çıkartacaktır.

numbers.splice(0,3);    // array'in 0. elemanından 3. elemanına kadar olan elemanları array'den çıkartır.

numbers.reverse();      // array'i tersine çevirir

numbers.sort();         // ilk rakamlarına göre array'i sıralar.

value = numbers.sort(function(x,y){
    return x-y;   // küçükten büyüğe sıralamak
});

value = numbers.sort(function(x,y){
    return y-x;   // büyükten küçüğe sıralamak
});
```

## Object Literal

```javascript
let value;

const programmer = {
    name : "Ahmet Değer",
    age : 22,
    email : "adeger@scistone.com",
    langs : ["Python","C","Sql"],
    
    adress : {
        city : "Istanbul",
        country : "Turkey"
    },

    work : function(){
        console.log("Programcı it gibi çalışıyor...");
    }
}
value = programmer;
value = programmer.email;

value = programmer.langs;

value = programmer.adress.city;

programmer.work();

const programmers [
    {name:"Berk", title:"Fullstack"},
    {name:"Ahmet",title:"Fullstack"}
]
programmers[0].name
programmers[0].title
```
## Zaman Objesi ve Metodları

```javascript
let value;

const now = new Date();

const date1 = new Date("1-22-1998 01:00"); // 22 Ocak 1997 saat 01 tarihi
const date2 = new Date("January 22 1998"); 
const date3 = new Date("1/22/1998");

value = date1.getMonth();           // 0 dan başlayıp sayar, tarihteki ayı alır
value = date1.getDate();            // eylül ayının hangi günü
value = date1.getDay();             // 0=pazar , günü alır

value = date1.getHours();           // saat bilgisini verir
value = date1.getMinutes();         // dakika
valeu = date1.getSeconds();         // saniye
valeu = date1.getMilliseconds();    // milisaniye


date1.setMonth(3);
date1.setDate(14);
date1.setFullYear(year,month,date)   // üç parametre alabilir, tek argüman verilirse sadece seneyi değiştirir.
```


# Javascript Temelleri - Koşullar, Döngüler, Fonksiyonlar

## Karşılaştırma Operatörleri
```javascript
console.log(2==2);              // true
console.log("js"=="java");      // false

console.log(2 == "2");          // true
console.log(2 === "2");         // === ifadesi araya typeof'u da katarak sorgulama yapar bu sebeple bu işlem false çıkar.

console.log(2<4);               // true
console.log(2 != 2);            // false
console.log(4 >= 2 );           // true
console.log(4 <= 2 );           // false

```

## Mantıksal Bağlaçlar

```javascript

console.log(!(2!=2));

console.log( (2==2) && ("Ahmet"=="Ahmet") );   // ve    operatörü   &&
console.log( (4==2) || ("Ahmet"=="Ahmet") );   // veya  opertörü    ||

```

## Koşul Operatörleri

```javascript
const error = true;

if (error==true){
    console.log("Hata oluştu.");
}
else {
    console.log("Hata oluşmadı.");
}
```

başka bir örnek : 
```javascript

const user = "mmc";

if (user === "mmc"){
    console.log("Kullanıcı bulundu");
}
else{
    console.log("Kullanıcı bulunamadı.");
}

```

bir başka örnek daha :

```javascript
const process = 1;

if (process === 1){
    console.log("işlem 1");
}
else if (process === 2){
    console.log("işlem 2");
}
else{
    console.log("geçersiz işlem");
}
```

## Ternary Operator

```javascript
const number = 100;
console.log(number===100 ? "Sayı 100" : "Sayı 100 Değil");
```

Koşul sağlandıktan sonra işlemler tek satırlık ise süslü paranteze gerek olmadan yanına yazabilirsiniz:
```javascript
if (number===100) console.log("Sayı 100");
else console.log("Sayı 100 değil");
```

## Switch Case
```javascript
const process = 2 ;

switch(process){
    case 1:
        console.log("İşlem 1");
        break;
// breakdöngüyü kırmak için yazılır eğer break yazılmazsa, döngü kırılmaz ve aşağıdaki işleme geçer
    case 2:
        console.log("İşlem 2");
        break;
    case 3:
        console.log("İşlem 3");
        break;
    case 4:
        console.log("İşlem 4");
        break;
    default:
        console.log("Geçersiz işlem");
}
```
## Fonksiyonlar

```javascript
// Fonksiyon Tanımlama

function merhaba(name="Bilgi Yok",age="Bilgi Yok"){
    //if (typeof name === "undefined") name = "Bilgi Yok";
    //if (typeof age  === "undefined") name = "Bilgi Yok";
    console.log(`İsim: ${name} Yaş ${age}`);
}

// Fonksiyon Çağrısı
merhaba("Berk",22);

```
---
```javascript
function square(x){
    return x*x;
}
function cube(x){
    return x*x*x;
}
let a = square(12);
a = cube(a);
```
---
```javascript
const merhaba = function(name){
    console.log("Merhaba "+name)
}
merhaba("Berk")
```

### Immediately Invoked Function Expression (IIFE)
```javascript
(function(name){
    console.log("Merhaba: "+name);
})("Ahmet");
```
---
### Anonim Fonksiyonlar     
```javascript
const database = {
    host:"localhost",
    add: function(){
        console.log("Eklendi.");        
    },
    get: function(id){
        console.log("Elde edildi.");
    },
    update: function(id){
        console.log(`Id: ${id} Güncellendi.`);
    },
    delete: function(id){
        console.log(`Id: ${id} Silindi.`);
    }
}
console.log(database.host);
database.add(10);
database.delete(10);
```
## Döngüler (While,Do While, For Döngüleri)
### Basit while / do while Döngüsü
```javascript
let i=0;

while(i<10){
    console.log(i);
    i++;
}
// Aynısının do while ile yazılışı
do {
   console.log(i);
    i++; 
}while(i<10);
```
---
### for Döngüsü
```javascript
const langs = ["Python","Javascript","Java"];
for (let index=0;index<langs.length;index++){
    console.log(langs[index]);
}
```
---
### forEach
```javascript
const langs = ["Python","Javascript","Java"];
langs.forEach(function(lang){ // for i in lang olduğu gibi düşünürsek 
    console.log(lang);        
    // i = lang, fonksiyon içerisindeki parametrenin i olduğunu düşünebiliriz.
});
```
---
```javascript
const langs = ["Python","Javascript","Java"];
langs.forEach(function(lang,index){ // for i in lang olduğu gibi düşünürsek 
    console.log(lang);        
    // i = lang, fonksiyon içerisindeki parametrenin i olduğunu düşünebiliriz.
    // index = i'nin indexi
});
```
### map fonksiyonu ile objelerde gezinmek
```javascript
const user = [
    {name:"Berk",age:22},
    {name:"Aleyna",age:23},
];
const names = users.map(function(user){
    return user.name
});
const ages = users.map(function(user){
    return user.age
});
```
### Sözlükler üzerinde gezinmek
```javascript
const user = {
    name:"Ahmet",
    age:22,
};
for (let key in user){
    value = user[key];
    console.log(key,value);
};
```

## Window objesi - this keyword nedir ?


---
## JS Scope Kavramı
```javascript

```

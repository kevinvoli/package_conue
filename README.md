
# package_conue


* 1 D3
* 2 MOMENT
* 3 LOCALFORAGE
* 4 COLOR
* 5 BLUEBIRD 

## D3
### utiliter

D3 (ou D3.js) est une bibliothèque JavaScript permettant de visualiser des données à l'aide de normes Web. 

### instalation

npm install d3
et initialiser le en sur votre fichier serveur.js avec 

    const D3 = require('d3')

ensuite pour l'utiliser sur votre page html ajouter le lien du fichier javascripte
<script src="https://d3js.org/d3.v5.js"></script>
ou la version minifier
<script src="https://d3js.org/d3-selection.v1.js"></script>

### utilisation

    var d3 = Object.assign({}, require("d3-format"), require("d3-geo"), require("d3-geo-projection"));

## MOMENT

###  utiliter

moment il serre a l'utilisation et  la gestion des dattes

### instalation

npm install moment
* initialisation

    var moment = require('moment');
    moment().format();

ensuite pour l'utiliser sur votre page html ajouter le lien du fichier javascripte
<script src="moment.js"></script>

### utilisation

    <script>
    moment().format("LLLL"); // 'Friday, June 24, 2016 1:42 AM'
    </script>

## localforage

### installation 
 npm install localforage
 ensuite pour l'utiliser sur votre page html ajouter le lien du fichier javascripte
 <script src="localforage/dist/localforage.js"></script>
 
### utiliter

localForage est une bibliothèque de stockage rapide et simple pour JavaScript.
il permet de gerre les fichier uploider
### utilisation
*cote html
 <script>localforage.getItem('something', myCallback);</script>
 
 *cote nodesjs
 
 *configuration

    localforage.config({
        driver      : localforage.WEBSQL, //Forcer WebSQL; même utilisation de setDriver ()
        name        : 'myApp',
        version     : 1.0,
        size        : 4980736, // Taille de la base de données, en octets. WebSQL-seulement pour l'instant.
        storeName   : 'keyvaluepairs', //Devrait être alphanumérique, avec des traits de soulignement.
        description : 'some description'
    }); 



*avec les promise

    localforage.setItem('key', 'value').then(function () {
      return localforage.getItem('key');
    }).then(function (value) {
      // we got our value
    }).catch(function (err) {
      // we got an error
    });

## COLOR

### UTILITER

Bibliothèque JavaScript pour la conversion et la manipulation de couleurs immuables avec prise en charge des chaînes de couleurs CSS.

### INSTALLATION

npm install color
initialiser le avec  

    var Color = require('color');

### UTILISATION

* avec les promise
``
var color = Color('rgb(255, 255, 255)')
var color = Color({r: 255, g: 255, b: 255})
var color = Color.rgb(255, 255, 255)
var color = Color.rgb([255, 255, 255])
``

* manipulation
``
    color.negate()         // rgb(0, 100, 255) -> rgb(255, 155, 0)

    color.lighten(0.5)     // hsl(100, 50%, 50%) -> hsl(100, 50%, 75%)
    color.darken(0.5)      // hsl(100, 50%, 50%) -> hsl(100, 50%, 25%)

    color.saturate(0.5)    // hsl(100, 50%, 50%) -> hsl(100, 75%, 50%)
    color.desaturate(0.5)  // hsl(100, 50%, 50%) -> hsl(100, 25%, 50%)
    color.grayscale()      // #5CBF54 -> #969696

    color.whiten(0.5)      // hwb(100, 50%, 50%) -> hwb(100, 75%, 50%)
    color.blacken(0.5)     // hwb(100, 50%, 50%) -> hwb(100, 50%, 75%)

    color.fade(0.5)     // rgba(10, 10, 10, 0.8) -> rgba(10, 10, 10, 0.4)
    color.opaquer(0.5)     // rgba(10, 10, 10, 0.8) -> rgba(10, 10, 10, 1.0)

    color.rotate(180)      // hsl(60, 20%, 20%) -> hsl(240, 20%, 20%)
    color.rotate(-90)      // hsl(60, 20%, 20%) -> hsl(330, 20%, 20%)

    color.mix(Color("yellow"))        // cyan -> rgb(128, 255, 128)
    color.mix(Color("yellow"), 0.3)   // cyan -> rgb(77, 255, 179)
``
// chaining
    color.green(100).grayscale().lighten(0.6)

## BLUEBIRD

### utilite
Bluebird est une bibliothèque de promesses mermetant d'utiliser les promise presque partous

### intalation
npm install bluebird

initialiser le avec 
    ``const Promise=requuire( "bluebird");``

### utilisation

pour pouvoir utiliser les promise sur un autre package  *exemple

    var redis = require("redis"),
        client = redis.createClient();
    const bluebird = require("bluebird");

    bluebird.promisifyAll(redis.RedisClient.prototype);
    bluebird.promisifyAll(redis.Multi.prototype);

    const redisKey = "redis-set-key";
    const redisValue = "hello-world";

    client.set(redisKey, redisValue);

    function getData(key) {
        return client.get(key, function(err, result) {
            console.log("1. Get key from redis - ", result.toString());
            return result.toString();
        });
    }

    const getRedisdata = getData(redisKey);
    console.log("2. getRedisdata", getRedisdata);

* Promise

`` .then((response) => {

)
.catch((error) => {
  // break promise here
})
.then((response) => {
 // skip
 // Je ne veux pas de vérifications supplémentaires ici!
)
.catch((error) => {
  // skip
  // Je ne veux pas de vérifications supplémentaires ici!
})``

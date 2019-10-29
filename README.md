# package_conue


* 1 D3
* 2 MOMENT
* 3 PDF.JS
* 4
* 5

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

### utilisation

moment il est utiliser pour la gestion des datte

### instalation

npm install moment
*initialisation 
var moment = require('moment');
moment().format();
ensuite pour l'utiliser sur votre page html ajouter le lien du fichier javascripte
<script src="moment.js"></script>

###utilisation

<script>
    moment().format("LLLL"); // 'Friday, June 24, 2016 1:42 AM'
</script>

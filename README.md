# README.md

### Descrizione

"boolbnb" e' un sito web progettato da zero grazie al lavoro di [Tetyana Sergata](https://github.com/TetyanaSergata), [Stefano Riccio](https://github.com/stefanoriccio1), [Manuel Di Pilla](https://github.com/Manuel-Di-Pilla), [Elia Pari](https://github.com/ailequal) e [Federico Caiello](https://github.com/FedericoCaiello). La piattaforma si ispira al famoso portale online Airbnb, il quale mette in contatto persone in cerca di un alloggio o di una camera per brevi periodi.

Essa prevede la registrazione di utenti, l’inserimento di appartamenti con geo-localizzazione ([TomTom API](https://developer.tomtom.com/)), il supporto ad una piattaforma di pagamenti esterna ([Braintree SDK](https://developers.braintreepayments.com/)) e la visualizzazione grafica delle statistiche d’uso ([Chart.js](https://www.chartjs.org/)) usando [Laravel](https://laravel.com/) come framework PHP.

### Guida

"boolbnb" e' basato sulla versione "[5.8.X](https://laravel.com/docs/5.8/releases#laravel-5.8)" di Laravel.

#### Requisiti per l'installazione

* PHP >= 7.1.3
* Composer (per utilizzare i packages in PHP)
* Node.js (per utilizzare i packages di npm in JavaScript)
* MySQL

#### Installazione

* Clonare la repository da GitHub con il seguente comando da terminale.

```sh
$ git clone https://github.com/ailequal/boolbnb.git
```

* Navigare all'interno della cartella.

```sh
$ cd boolbnb
```

* Copiare il file ".env.example" in uno nuovo chiamato ".env".

```sh
$ cp .env.example .env
```

* Compilare i seguenti campi del file ".env" in modo da farli combaciare con il proprio ambiente di lavoro locale. Le chiavi per abilitare Braintree sono reperibili registrandosi [qui](https://developers.braintreepayments.com/).

```sh
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD= 

BRAINTREE_ENV=sandbox
BRAINTREE_MERCHANT_ID=
BRAINTREE_PUBLIC_KEY=
BRAINTREE_PRIVATE_KEY=
```

* Copiare il contenuto dell'archivio zip "images.zip" (compresa la cartella che contiene i file) all'interno del seguente percorso:


```sh
boolbnb/storage/app/public/
```

* Ora digitare tutti i seguenti comandi da terminale, uno dopo l'altro.

```sh
$ composer install

$ php artisan key:generate

$ composer dump-autoload

$ php artisan storage:link

$ php artisan migrate

$ php artisan db:seed

$ npm install

$ npm run dev

$ php artisan serve
```

* "boolbnb" sara' ora accessibile in locale dal seguente indirizzo: "[127.0.0.1:8000](http://127.0.0.1:8000)".

#### Errori

* Se si ricevono degli errori legati a Braintree, provare a digitare il seguente comando:

```sh
$ php artisan config:clear
```

### Struttura database con i seeder iniettati

#### Utenti

* Pippo con 4 appartamenti a Roma
* Paperino con 6 appartamenti a Napoli
* Paperina con 5 appartamenti a Rimini
* Topolino con 4 appartamenti a Milano
* Minnie con 1 appartamento a Cesena

Ogni utente ha la sua email composta da "**utente@gmail.com**". Quindi nel caso di Pippo avremo "pippo@gmail.com". La password dei seguenti 5 account e' "**password**".

#### Appartamenti

* Tutti gli appartamenti hanno gia' delle informazioni "realistiche".
* Tutti gli appartamenti hanno ognuno la propia foto personalizzata.
* I servizi extra sono generati casualmente dai seeder per ogni appartamento.
* I primi quattro utenti hanno tutti un singolo appartamento con la promozione gia' attivata. Quindi tutti tranne Minnie.
* Tutti gli appartamenti hanno gia' statistiche di visite e messaggi pronte da essere visualizzate, tutte diverse tra loro.


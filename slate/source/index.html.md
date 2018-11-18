---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell #!TODO - verify shell and CMD
  - docker
  - csharp
  - javascript
  - bash
  - sh

toc_footers:
  - <a href='https://github.com/lord/slate'>Dokumentacja stworzona przy pomocy Slate</a>

includes:
  - errors

search: true
---

# Wstęp
Outloud jest serwisem umożliwiającym naukę poprawnej wymowy wyrażen w języku angielskim.

Serwis jest realizacją pracy dyplomowej o temacie !TODO - jaki ja mam temat?!

Serwis składa się z części serwerowej oraz klienckiej. Część serwerowa składa się z mikrousług (ang. microservices) opartych o technologię .NET Core oraz język C#. 
Część kliencka serwisu to aplikacja mobilna, dostępna na platformę Android. Aplikacja ta została stworzona przy pomocy frameworka React-Native w języku JavaScript i możliwa jest do pobrania w postaci pliku *.apk z repozytorium. !TODO - link!

# Architektura 
Tworząc część serwerową (ang. backend) zdecydowałem się zastosować architekturę mikroserwisową. 
Architektura mikroserwisowa pozwala na lepszą kontrolę rozwoju oprogramowania:
 - lepszy dobór języków programowania do określonych podzadań systemu.

## Kontrola wersji
Kod źródłowy całego projektu znajduję się w repozytorium [GitHub](https://github.com/out-loud)


## Komunikacja
Elementy backendu komunikują się pomiędzy sobą za pomocą :
 - kolejek zdarzeń opartych o protokół AMQP i narzędzie RabbitMQ dla asynchronicznych zapytań typu POST
 - protokołu HTTP i RESTful API dla zapytań typu GET

## Chmura
Wszystkie składowe serwisu tworzone są w sposób umożliwiający wdrożenie w dowolnej chmurze, oferując m.in. konteneryzację przy użyciu narzędzia Docker.

## Monitorowanie

# Instrukcje
## Uruchamianie lokalnie
Zanim developer rozpocznie pracę nad jednym z mikroserwisów, wymagane jest stworzenie odpowiedniej infrastruktury do uruchomienia całego projektu.

Aby uruchomić projekt należy pobrać podprojekt Outloud a następnie uruchomić skrypt git-pull.sh

> Uruchamianie mikroserwisu napisanego w .NET Core:
```sh
dotnet watch run
```

> Uruchamianie przy użyciu Dockera należy uruchomić w projekcie Outloud komendę:
```sh
docker-compose up
```

### Wymagania
  - **npm** w wersji minimum 6.4
  - **.NET Core SDK** w wersji minimum 2.1.403
  - **Docker** w wersji minimum 18.06
  - **Git Bash** 
  - Emulator systemu Android lub fizyczne urządzenie na tej platformie w wersji minimum 6.

### Polecane narzędzia
  - VSCode - darmowy edytor tekstowy
  - SourceTree - darmowe narzędzie do obsługi repozytoriów
  - ADB - darmowy emulator Android, dostępny z Android Studio oraz VS w pakiecie Xamarin

## Uruchamianie w klastrze Kubernetes

## Uruchamianie w chmurze


# Licencja
Oprogramowanie dostępne jest na licencji MIT.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete


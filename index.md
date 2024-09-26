---
title: Home
layout: home
---



# Llenguatges de Marques - JSON

## JSON

### JavaScript Object Notation

### JavaScript Object Notation

- JSON (JavaScript Object Notation). És un “format de notació de dades” lleuger utilitzat tant per a guardar informació com per a l’intercanvi de dades entre aplicacions.
- No es defineix com llenguatge de marques ja que no usa etiquetes com HTML o XML.
- Els arxius JSON són arxius de text i usen l'extensió `.json`.
- La seua principal característica és que és un llenguatge autodescriptiu i fàcil de llegir i d’escriure tant per les màquines com per els humans.
- És una alternativa més simple i lleugera a XML que compta amb funcions similars.
- JSON és un estàndard ampliament acceptat en la comunicació entre clients i servidors.
- La majoria dels llenguatges de programació tenen suport integrat per a la manipulació de JSON.
- És una eina versàtil per a l'emmagatzematge de dades i la configuració d'aplicacions.

## 1.- Sintaxi JSON

JSON utilitza una estructura basada en parelles clau-valor (keys - values):

- Les claus (keys) són cadenes de caràcters (strings) envoltats entre cometes “ ”.
- Els valors (values) són un tipus de dades JSON vàlids.
- Les dades es separen per comes.

```json
{ "key":"value", "key1":"value", "key2":"value" }
```

En JSON els valors admeten els següents tipus de dades:

- **Cadenes de Text (Strings):** es representen amb cometes dobles, com "aquesta és una cadena". Poden contenir qualsevol caràcter Unicode.
- **Números:** JSON admet nombres enters i decimals, sense notació especial. Ex: `42` o `3.14`.
- **Booleans i Null:** JSON admet valors booleans, representats com `true` i `false`. Per a representar un valor nul utilitzem `null`.

```json
{
  "nom": "Aitor Tilla",
  "edat": 26,
  "estudiant": true,
  "ciutat": "La Vall d'Uixó",
  "puntuació": 5.5,
  "comentari": "Aquest és un exemple de JSON amb diverses dades.",
  "nulExemple": null
}
```

## 2.- Objectes JSON

Un objecte JSON és una col·lecció de parelles clau-valor, on les claus són cadenes de text i els valors poden ser de qualsevol tipus de dades suportat per JSON.

```json
{ "nom": "Aitor Tilla", "edat": 26, "moto": null }
```

Objecte JSON que representa un llibre:

```json
{
  "títol": "El Gran Gatsby",
  "autor": "F. Scott Fitzgerald",
  "anyPublicació": 1925,
  "editorial": "Scribner",
  "disponible": true,
  "crítiques": [4.5, 5.0, 4.2]
}
```

Com es mostra a l’exemple, les claus ("títol", "autor", "anyPublicació", etc.) són cadenes de text. Els valors poden ser cadenes de text, nombres, booleans o fins i tot un array (com "crítiques") que conté valors numèrics.

- Delimitats per `{}`.
- S'organitzen en parells clau/valor.
- Tipus de dades:
  - Claus: string.
  - Valors: string, number, object, array, boolean o null.
- Claus i valors: Separats per dos punts.
- Parells claus/valor: Separats per comes.

## 3.- Arrays JSON

Un Array JSON és una llista ordenada de valors:

```json
[ "Ford", "BMW", "Fiat" ]
```

Exemple d'Array que conté una llista de tasques:

```json
{
  "tasques": ["Comprar llet", "Anar al gimnàs", "Estudiar per l'examen"]
}
```

En aquest exemple, l'array està contingut dins de l'objecte com el valor associat a la clau "tasques". L'array conté tres cadenes de text que representen tasques diferents.

## 4.- Combinacions d’Objectes i Arrays

Les combinacions de dades en JSON són molt variades i flexibles, ja que podem anidar objectes dins d'objectes, arrays dins d'arrays i combinar-los segons les nostres necessitats. Algunes combinacions són:

- **Objectes simples:**
  ```json
  { "nom": "Jaume", "edat": 18, "ciutat": "La Vall d'Uixó" }
  ```

- **Arrays simples:**
  ```json
  ["blau", "verd", "groc"]
  ```

- **Objectes dins d'objectes:**
  ```json
  {
    "persona": { "nom": "Veronica", "edat": 28 },
    "adreça": { "carrer": "Carrer Gran, 123", "ciutat": "Fodeguilla" }
  }
  ```

- **Arrays dins d'arrays:**
  ```json
  [ [1, 2, 3], ["a", "b", "c"] ]
  ```

- **Objectes amb arrays:**
  ```json
  {
    "noms": ["Gerard", "Jordi"],
    "punts": [8.5, 7.0]
  }
  ```

- **Arrays d'objectes:**
  ```json
  [
    { "nom": "Vicent", "edat": 25 },
    { "nom": "Carles", "edat": 29 }
  ]
  ```

- **Arrays amb tipus de dades mixtes:**
  ```json
  [42, "groc", true, { "objecte": "aninat" }]
  ```

- **Objectes amb tipus de dades mixtes:**
  ```json
  {
    "nom": "MariCarmen",
    "edat": 30,
    "actiu": true,
    "aficions": ["lectura", "caminar"]
  }
  ```

- **Objectes buits i arrays buits:**
  ```json
  {
    "informacio": {},
    "interessos": [],
    "historial_compres": []
  }
  ```

- **Valors nuls i valors booleans:**
  ```json
  {
    "valor1": null,
    "valor2": true,
    "valor3": false
  }
  ```

- **Arrays amb elements anidats:**
  ```json
  [ [1, 2, 3], ["a", "b", "c", [true, false]] ]
  ```

## 5.- Consideracions i Errors comuns en JSON

- **Case-Sensitive:** Distingeix entre majúscules i minúscules.
  ```json
  { "nom": "Fina", "Nom": "Pepe" }
  ```

- **Format per un únic element (Array o Objecte):**
  - Incorrecte:
    ```json
    [1, 2, 3], ["a", "b", "c"]
    ```

  - Correcte:
    ```json
    [ [1, 2, 3], ["a", "b", "c"] ]
    ```

  - Incorrecte:
    ```json
    { "nom": "Sergi", "edat": 21, }
    ```

  - Correcte:
    ```json
    { "nom": "Sergi", "edat": 21 }
    ```

- **No permet claus duplicades en un objecte:**
  ```json
  {
    "color": "vermell",
    "color": "blau"
  }
  ```

- **No permet comentaris.**

## 6.- Utilització caràcters especials i de control

En JSON es poden usar caràcters especials, de control i caràcters Unicode escapats adequadament. Exemple:

```json
{
  "missatge": "Aquest és un exemple amb caràcters especials: \"cometes dobles\". També conté línies noves:\nLínia 1\nLínia 2",
  "barra_invertida": "Això és una barra invertida escapada: \\",
  "tabulacio": "Això és una tabulació: \tTabulació 1\tTabulació 2",
  "simbol": "Símbol de copyright © (c) representat com Unicode: \\u00A9",
  "caracter_control": "Això és un caràcter de control representat com Unicode: \\u20AC"
}
```

Nota: Poden trobar molts **validadors de JSON online**, com [jsonlint.com](https://jsonlint.com).


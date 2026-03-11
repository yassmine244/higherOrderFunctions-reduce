```javascript
var people = [ 
  {name: {first: 'Grace', middle: 'B.', last: 'Hopper'}, age: 85}, 
  {name: {first: 'Adele', last: 'Goldstine'}, age: 43}, 
  {name: {first: 'Ada', last: 'Lovelace'}, age: 36}, 
  {name: {first: 'Hedy', middle: 'E.', last: 'Lamarr'}, age: 85}, 
  {name: {first: 'Ruchi', last: 'Sanghvi'}, age: 34} 
]; 
```

## 1 — Âge moyen

Écris une fonction `averageAge` qui retourne l’âge moyen des personnes.

Étapes :
1. Calculer la somme des âges
2. Diviser par le nombre de personnes (`people.length`)

```javascript
function averageAge(people) {
 var somme = people.reduce(function(acc, person) {
    return acc + person.age;
  }, 0);

  return somme / people.length;
}
```

---

## 2 — Factorielle avec range et reduce

On te donne la fonction `range` :

```javascript
function range(start, end) { 
  var acc = []; 
  for (var i = start; i < end; i++) { 
    acc.push(i); 
  } 
  return acc; 
}
```

En utilisant `range` et `reduce`, complète la fonction `factorial` qui calcule la factorielle de `n`.

```javascript
function factorial(n) {
return range(1, n + 1).reduce(function(acc, num) {
    return acc * num;
  }, 1);
}
}
```

Exemples :

```javascript
factorial(5); // => 120
factorial(3); // => 6
```

---

## 3 — Compter les occurrences

Écris une fonction `countOccurrences` qui prend :
- une chaîne
- un caractère

et retourne le nombre de fois que ce caractère apparaît.

```javascript
function countOccurrences(chaine, caractere) {
return chaine.split('').reduce(function(count, char) {
    if (char === caractere) {
      return count + 1;
    }
    return count;
  }, 0);
}
```

Exemples :

```javascript
countOccurrences('hello', 'l'); // => 2
countOccurrences('the', 'z'); // => 0
countOccurrences('hello, world!', 'l'); // => 3
```

---

## 4 — Fonctions "every"

Écris des fonctions qui vérifient si :

### a) Tous les nombres sont impairs

```javascript
function tousImpairs(nombres) {
return nombres.every(function(n) {
    return n % 2 !== 0;
  });
}
```

---

### b) Tous les nombres sont positifs

```javascript
function tousPositifs(nombres) {
 return nombres.every(function(n) {
    return n > 0;
  });
}
```

---

### c) Toutes les chaînes ont une longueur supérieure à 3

```javascript
function longueurSuperieureA3(chaines) {
 return chaines.every(function(c) {
    return c.length > 3;
  });
}
```

---

### d) Toutes les chaînes contiennent la lettre "e"

```javascript
function contiennentE(chaines) {
return chaines.every(function(c) {
    return c.includes('e');
  });
}
```

---

## 5 — Fonction every

Écris une fonction `every` qui prend :
- un tableau
- une fonction prédicat (qui retourne true ou false)

`every` doit retourner `true` si le prédicat est vrai pour **tous** les éléments.

```javascript
function every(tab, predicate) {
for (var i = 0; i < tab.length; i++) {
    if (!predicate(tab[i])) {
      return false;
    }
  }
  return true;
}
```

Tu dois pouvoir écrire :

```javascript
function everyNumberEven(numbers) { 
  return every(numbers, function(number) { 
    return number % 2 === 0; 
  }); 
}
```

---


### 6 — Tous les âges sont supérieurs à 30

```javascript
function agesSuperieursA30(people) {
return people.every(function(person) {
    return person.age > 30;
  });
}
```

---

### 7 — Toutes les personnes ont un prénom

```javascript
function tousOntPrenom(people) {
}
```

---

### 8 — Tous les prénoms contiennent au moins 3 lettres

```javascript
function prenomsLongs(people) { return people.every(function(person) {
    return person.name.first.length >= 3;
  });
  }
  
```

---

### 9 — Somme des âges > 200

Écris une fonction qui retourne true si la somme des âges est supérieure à 200.

```javascript
function sommeAgesSup200(people) {
var somme = people.reduce(function(acc, person) {
    return acc + person.age;
  }, 0);

  return somme > 200;
}
```

---

### 10 — Tous les noms de famille commencent par une majuscule

```javascript
function nomsMajuscule(people) {
return people.every(function(person) {
    var last = person.name.last;
    return last[0] === last[0].toUpperCase();
  });
}
```

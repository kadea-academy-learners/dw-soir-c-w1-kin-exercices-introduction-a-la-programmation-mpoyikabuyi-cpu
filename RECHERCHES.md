# RECHERCHES — Semaine 13

> Pour chaque exercice : reformule avec tes mots (pas de copier-coller), ajoute un test que tu as exécuté toi-même,
> et cite une source précise (une page, pas juste « Google »). MDN en français est la référence.
> Si tu as utilisé une IA, indique ton prompt et vérifie sa réponse sur MDN.
> Ne modifie pas les titres `## F1 — …` : ils servent à l'évaluation automatique.

## F1 — Ma carte d'apprenant

**Question :** Pourquoi typeof null renvoie-t-il 'object' alors que null n'est pas un objet ?

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

...

**Mon test dans la console :**

```js
const ancienneFormation = null;
console.log(typeof ancienneFormation);
// Résultat obtenu : object
```

**Source :** https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Operators/typeof

**IA utilisée ? (prompt + vérification sur MDN) :** non

## F2 — Le convertisseur de saisie

**Question :** Qu'est-ce que NaN, et pourquoi NaN === NaN renvoie false ? Quelle fonction utiliser pour le détecter ?

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

**Qu'est-ce que NaN, et pourquoi NaN === NaN renvoie false ?**
  `NaN` (Not-a-Number) est une valeur spéciale en JavaScript qui représente un résultat numérique invalide ou non représentable (par exemple, suite à une opération mathématique impossible). `NaN === NaN` renvoie `false` par définition dans la norme IEEE 754 (la norme sur les nombres à virgule flottante utilisée par JavaScript), qui stipule qu'un nombre non valide n'est égal à aucune autre valeur numérique, y compris lui-même.
  Il faut utiliser la fonction `Number.isNaN()` (ou globalement `isNaN()`, bien que `Number.isNaN()` soit plus stricte et recommandée)

**Mon test dans la console :**

```js
 console.log(NaN === NaN);                           // résultat obtenu : false 
 console.log(Number.IsNaN(Number('abc')))           // résultat obtenu : true
```

**Source :** https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/NaN

**IA utilisée ? (prompt + vérification sur MDN) :** oui, je l'ai demandé NaN === renvoi false

## F3 — Pair ou impair : le tirage des tickets

**Question :** Que renvoie -7 % 2 ? Déduis-en pourquoi il vaut mieux tester % 2 !== 0 plutôt que % 2 === 1 pour détecter un nombre impair.

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

...En javascript, l'opérateur modulo (%) conserve le signe du dividende (le nombre de gauche). Par conséquent,-7% renvoie -1 (et non 1)
%2 !== 0 plutot que %2 ===1? puisque le reste peut etre négatif si l'on manipule des nombres négatif (comme -1), un test strict === 1 échouera pour les nombres impairs négatifs. En testant !== 0, on s'assure de capturer correctement tous les nombres impairs, qu'ils soient positifs ou négatifs.

**Mon test dans la console :**

```js
console.log(-7 % 2); // Résultat obtenu : -1
```

**Source :** https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Remainder

**IA utilisée ? (prompt + vérification sur MDN) :** Oui, je l'ai demandé pour -7 % 2 vont mais 1 garde le signe de 7.

## F4 — Le contrôleur du bus

**Question :** Peut-on enchaîner plusieurs ternaires ? Pourquoi est-ce souvent déconseillé ?

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

oui, il est techniquement possible d'enchainer plusieurs opérations ternaires mais ce deconseillé par ceque
la lisibilité reduite et maintenance difficile.

**Mon test dans la console :**

```js
const age = 16;
const status = age >= 16 ? 'mineur' : 'majeur'
console.log(status);     // Afficher 'mineur'
```

**Source :** https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_operator

**IA utilisée ? (prompt + vérification sur MDN) :** Oui, je l'ai demandé pourquoi ce deconseillé de mettre plusieur ternaires

## F5 — Ma première fonction fléchée

**Question :** Quand peut-on enlever les parenthèses autour des paramètres, et quand peut-on enlever return et les accolades ?

**Ma réponse (avec mes mots, 3 à 5 lignes) :**
quand il ya exactement un paranthètre simple exemple n => n*n elle sont obligatoires pour zéro 
...

**Mon test dans la console :**

```js
// colle ici le test que tu as exécuté et le résultat obtenu
const carre = (nombre) => { nombre * nombre};
console.log (carre(7));      // resultat undefined
```

**Source :** https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function

**IA utilisée ? (prompt + vérification sur MDN) :** non

## F6 — Le compte à rebours

**Question :** À quoi sert le mot-clé continue ? Quelle différence avec break ?

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

...

**Mon test dans la console :**

```js
// Test avec continue : 3, puis 1 (le 2 est saute)
// Test avec braek : 3, seulement (la boucle s'arrete au 2)
```

**Source :** https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Statements/continue

**IA utilisée ? (prompt + vérification sur MDN) :** Oui, je l'ai démande quel est l'importance de continue et quelle est la difference entre continue et break. 

## M1 — FizzBuzz kinois

**Question :** Pourquoi FizzBuzz est-il célèbre dans les entretiens d'embauche de développeurs ?

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

FizzBuzz est célèbre parce que c'est un test très simple qui de permet de vérifier vite si un candidat sait vraiment programmer.
il faut utiliser une boucle, le modulo et des conditions.beaucoup de candidat se trompent sur l'ordre des conditions : le cas " multiple de 3 et de 5 doit etre testé en premier.

**Mon test dans la console :**

```js
// colle ici le test que tu as exécuté et le résultat obtenu
const estMultipleDe = (nombre, diviseur) => nombre % diviseur === 0;
const fizzBuzzKinios = (nombre) => {
  if (estMultipleDe(nombre, 3) && estMultipleDe(nombre, 5)) return "Malewawe";
  if (estMultipleDe(nombre, 3)) return "Malewa";
  if (estMultipleDe(nombre, 5)) return "Wewa";
  return `${nombre}`;
};
const resultats = [],
for (let i; i <= 30 ; i++) {
  resultats.push(fizzBuzzKinios(i));
}
console.log(resultats.join(" , "));       // 1, 2, Malewa, 4, Wewa, Malewa, 7, 8, Malewa, 11, Malewa, 13, 14, MalewaWewa, 16, 17, Malewa, 19, Wewa, 22, 23, Malewa, Wewa, 26, Malewa,28, 29, MalewaWewa

**Source :** https://coddy.tech/learn/javascript/fundamentals/the_fizzbuzz_function

**IA utilisée ? (prompt + vérification sur MDN) :** oui 

## M2 — Le distributeur automatique (DAB)

**Question :** Comment afficher 75000 sous la forme 75 000 avec toLocaleString() ?

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

Pour afficher 75000 sous la forme 75 000, on utilise la méthode toLocaleString()
sur le nombre, en lui donnant la langue francaise : (toLocalString ("fr-FR)) elle ajoute automatiquement un espace entre les millier, selon les règles de la langues choisie. sans paramètre, elle utilise la langue de l'ordinateur, donc le résultat peut changer d'une machineà l'autres

**Mon test dans la console :**

```js
// colle ici le test que tu as exécuté et le résultat obtenu      Résultat obtenu
console.log((75000).toLocaleString("fr-FR));                       // 75000
console.log((500000).toLocaleString("fr-FR));                      // 500 000

**Source :**https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toLocaleString

**IA utilisée ? (prompt + vérification sur MDN) :** non

## M3 — Le détecteur de champs vides (Truthy / Falsy)

**Question :** Quelle est la liste complète des valeurs falsy en JavaScript ? (Indice : il y en a plus que dans cet exercice.)

**Ma réponse (avec mes mots, 3 à 5 lignes) :**
En  javascript, une valeur false est une valeur qui devient `false` quand on la met dans une condition. il y en a 8: `false`, `0`, `On` (le BigInt zéro),`" "`,(chaine vide), `null`, undefined et `NaN`, il existe aussi `document.all`

**Mon test dans la console :**

```js
// colle ici le test que tu as exécuté et le résultat obtenu
console.log(["", "0", -0, On, "", null, undefined, NaN].map(Boolean));
// [false, false, false, false, false, false, false,false ,fasle ]

console.log (["", "0", [], {}, ].map(Boolean));

**Source :**https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/falsy

**IA utilisée ? (prompt + vérification sur MDN) :** non

## M4 — Le score par défaut : || contre ??

**Question :** Que fait l'opérateur ?? (coalescence des nuls) et en quoi est-il différent de || ?

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

...

**Mon test dans la console :**

```js
// colle ici le test que tu as exécuté et le résultat obtenu
```

**Source :** 

**IA utilisée ? (prompt + vérification sur MDN) :** non

## M5 — La vitre teintée (portée de bloc)

**Question :** Pourquoi var est-il banni du code moderne ? Cherche ce que sont la portée de fonction et le « hoisting ».

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

...

**Mon test dans la console :**

```js
// colle ici le test que tu as exécuté et le résultat obtenu
```

**Source :** 

**IA utilisée ? (prompt + vérification sur MDN) :** non

## M6 — Le détective du return

**Question :** Le troisième bug vient de l'« insertion automatique de point-virgule » (ASI). Explique ce mécanisme en 3 lignes.

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

...

**Mon test dans la console :**

```js
// colle ici le test que tu as exécuté et le résultat obtenu
```

**Source :** 

**IA utilisée ? (prompt + vérification sur MDN) :** non

## M7 — La tirelire numérique

**Question :** Cite tous les opérateurs d'affectation composée (+=, -=…) et donne un exemple pour chacun.

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

...

**Mon test dans la console :**

```js
// colle ici le test que tu as exécuté et le résultat obtenu
```

**Source :** 

**IA utilisée ? (prompt + vérification sur MDN) :** non

## M8 — La batterie qui se décharge

**Question :** Quelle est la différence entre while et do...while ? Que donnerait l'étape 4 avec un do...while ?

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

...

**Mon test dans la console :**

```js
// colle ici le test que tu as exécuté et le résultat obtenu
```

**Source :** 

**IA utilisée ? (prompt + vérification sur MDN) :** non

## A1 — Kadea Express v2 : le calculateur de livraison

**Question :** Pourquoi 0.1 + 0.2 ne donne-t-il pas 0.3 en JavaScript ? Et pourquoi toFixed() est un piège si on veut continuer à calculer ?

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

...

**Mon test dans la console :**

```js
// colle ici le test que tu as exécuté et le résultat obtenu
```

**Source :** 

**IA utilisée ? (prompt + vérification sur MDN) :** non

## A2 — Le moteur de paie v2

**Question :** La méthode .reduce() n'a pas été vue en atelier. Explique ce qu'elle fait et réécris l'étape 2 avec elle.

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

...

**Mon test dans la console :**

```js
// colle ici le test que tu as exécuté et le résultat obtenu
```

**Source :** 

**IA utilisée ? (prompt + vérification sur MDN) :** non

## A3 — L'inventaire en console

**Question :** Comment afficher seulement les colonnes nom et stock avec console.table() ? Et que renvoient .find() et .filter() quand rien ne correspond ?

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

...

**Mon test dans la console :**

```js
// colle ici le test que tu as exécuté et le résultat obtenu
```

**Source :** 

**IA utilisée ? (prompt + vérification sur MDN) :** non

## A4 — Le classement de la promo

**Question :** Comment classer le bulletin de la meilleure à la moins bonne moyenne avec .sort() ? Pourquoi .sort() modifie-t-il le tableau d'origine, et comment l'éviter ?

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

...

**Mon test dans la console :**

```js
// colle ici le test que tu as exécuté et le résultat obtenu
```

**Source :** 

**IA utilisée ? (prompt + vérification sur MDN) :** non

## A5 — Le nombre mystère

**Question :** Explique la « recherche dichotomique » et pourquoi 7 essais suffisent toujours pour trouver un nombre entre 1 et 100.

**Ma réponse (avec mes mots, 3 à 5 lignes) :**

...

**Mon test dans la console :**

```js
// colle ici le test que tu as exécuté et le résultat obtenu
```

**Source :** 

**IA utilisée ? (prompt + vérification sur MDN) :** non

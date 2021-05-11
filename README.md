# Test technique pour un stage braincube recherche

Le but de ce test est d'avantage de nous donner un aperçu de votre expérience avec python et quelques outils classique d'analyse de données. Même si vous ne répondez pas à toutes les questions, ce test nous servira de support pour l'entretien. Essayez de ne pas prendre plus d'une heure pour faire ce test.

## 1. Récupération des données

Clonez ce répertoire sur votre machine (le répertoire contient un fichier `depenses.csv` et un `README.md`).

## 2. Création d'un dépôt git
**[Si vous savez utiliser git]** Créez un nouveau sur projet git sur votre plateforme de choix (github/gitlab/bitbucket) et poussez y les deux fichiers.

N'hésitez pas à consulter la documentation des services en question, elle est généralement très bonne :

https://guides.github.com/activities/hello-world/

## 3. Anonymisation des données
Un site de vente en-ligne a enregistré les montants dépensés par chaque client dans le CSV qui contient cinq colonnes :

- `nom`: nom du client

- `ville`: ville de résidence

- `age`: âge du client

- `salaire`: salaire annuel du client

- `depenses`: montant des dépenses effectuées.

Pour des raisons d'anonymisation, les noms et les villes de résidence ne doivent pas apparaitre en clair dans le CSV mais uniquement un identifiant unique `id1`, `id2`, etc. ou `ville1`, `ville2`, etc. Toutes les occurrences d'une même ville doivent être remplacées par la même valeur anonymisée. D'autre part les colonnes numériques (age, salaire, dépenses) doit être centrées (moyenne = 0) et réduites (écart-type = 1). Vous devez écrire un script **python** (`anonymisation.py`) qui lit le fichier `depenses.csv` et écrit un nouveau fichier CSV (appelé `depenses_anonymes.csv`) avec les données anonymisées (noms et villes) et centrées réduites (numériques).

L'utilisation de la librairie **pandas** est recommandée.

## 4. Régression linéaire

À partir des **données transformées**, il vous est demandé de produire un prédicteur qui estime les dépenses d'un client à partir de ses revenus. Pour cela vous devez écrire un fichier `lineaire.py` qui utilise une simple [régression linéaire](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html) pour prédire les `depenses` à partir du `salaire`. Le résultat (qui contient les colonnes `salaire`, `depenses` et une nouvelle colonne appelée `prediction_depenses`) doit être exporté dans un fichier csv `predictions_1.csv`.

Remarquez que les régressions linéaires peuvent utiliser plusieurs variables. Faites une deuxième prédiction mais cette fois-ci en utilisant à la fois le `salaire` et l'`age` des clients. Le code peut être mis dans `lineaire.py` également mais le résultat (qui contient toutes les colonnes du fichier originel et une nouvelle colonne `prediction2_depense`) doit être exporté dans `predictions_2`.csv.

## 5. Questions

À partir des données originelles, répondez à ces deux questions :
- Quelle est la probabilité qu'un individu ayant dépensé moins de 50 € habite Clermont-Ferrand ?
- Dans quelle commune les habitants ont-il le plus taux de dépense par rapport à leur salaire le plus élevé ?

## 6. Poussez les résultats

- Si jamais l'étape 2 me vous a pas posée de soucis, vous pouvez ajouter les fichiers pythons et csv créés au dépôt git et pousser les modification sur le serveur de votre plateforme. 

  *Attention : vérifiez que votre push a fonctionné correctement et que les fichiers sont bien dur github (ou gitlab ou bitbucket).*

- Si l'étape 2 vous a donné du fil à retordre, il est possible de nous envoyez vos scripts et csv sous forme d'un fichier zip.

Dans les deux cas, le lien vers le dépôt git ou le fichier zip doivent être envoyés en réponse au mail d'invitation pour l'entretien et avant l'entretien en question.

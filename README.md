# Être ou ne pas être

##  Présentation :
Dans ce projet on nous propose de construire un modèle d’apprentissage supervisé qu’on utilisera
pour faire des prédictions sur le décès ou pas des patients d’un hôpital.

Le set de données porte sur 80000 patients représentés par des variables telles que le sexe, l’age ,
l’origine ethnique etc.

Le travail s’est fait en en 3 parties :

  Dans un premier temps il s’agit de charger les données et de les parcourir pour les connaître et avoir une idée de comment les exploiter. On va également s’occuper de traiter ces données pour que celles-ci soient exploitable par le modèle (traitement des valeurs absentes et aberrantes, etc).
  
  On va par la suite diviser le set de données en 2 groupes : Le groupe de données d’entraînement et le groupe de données validation.

  Enfin on a construit le modèle prévisionnel et on l'a testé pour voir si il est efficace. On cherche à avoir à terme un algorithme dont l’objectif est de deviner l’état de santé d’un patient automatiquement.
  
## Chargement/Traitement des données:

  La première étape est bien entendu de charger et traiter les données qu’on va par la suite exploiter.
On cherche à ne garder dans notre set que les données exploitables et dans la mesure où toutes les
données ont un impact sur la précision du modèle il faut être sûr de retirer (ou modifier) toutes les
données inexploitables.

Ces données vont par exemple être les données de patients incomplets (NaN) ou aberrantes. Dans
ce projet on choisit de remplacer les valeurs non définies par « la valeur la plus probable de la
variable »  qui est simplement l’occurrence de la variable la plus présente dans l’ensemble.

On cherche ensuite à remplacer les données exprimées sous formes de chaînes de caractères par des
données exprimées sous forme d’entiers car les entiers sont beaucoup plus facilement exploitables
par des modèles.

Pour le faire on dispose de deux méthodes qui nous sont proposées : LabelEncoder et One hot Vector.

Pour réduir les dimension des données on utilise l’ACP (analyse en composantes principales).

Pour le faire l’ACP cherche les combinaisons linéaires de variables qui expliquent la variance
maximale des données.

Par ce moyen on détermine les composantes les plus importantes des données car ayant le plus gros
impact sur la variance.

On va utiliser la méthode Logistic Regression pour créer le modèle et on va l’entraîner grâce à notre
ensemble d’entraînement.

## Analyse exploratiore :

Dans cette partie nous présentons les résultats de l'analyse exploratoire des données. Nous avons commencé par examiner les types de variables dans notre
ensemble de données. Nous avons constaté que la plupart des variables étaient
numériques, suivies des variables binaires et seulement huit variables étaient
catégorielles.

Ensuite ,nous avons examiné la variable cible ‘y’ qui dit si le patient a survécu ou non
et nous avons constaté que la majorité de nos patients survivent .

Enfin ,nous avons dessiné quelques graphes pour bien visualiser la répartition des
données et les relations potentielles entre eux (par exemple la corrélation ).


## Evaluation :

Le but de cette dernière partie est d'évaluer les performances des modèles de classification,
tout d’abord la méthode hold out est utilisée pour mesurer le score de validation mais il est
recommandé d’utiliser la validation croisée pour des résultats plus fiables et pour cela on utilise
GridSearchCV pour trouver les meilleurs hyperparamètres .

Ensuite ,pour deux modèles de classification les balanced_accuracy sont calculées
pour plusieurs valeurs d’un hyperparamètre .

Enfin, les résultats sont affichés sous forme de diagrammes à bâtons avec des barres d’erreur
pour les deux modèles .

Dans l’ensemble cette dernière étape permet d’observer la stabilité des prédictions pour chaque
modèle en fonction des différentes valeurs des hyperparamètres choisis .


## Résultats :

- **Si l'équilibre entre les classes est crucial** et que la capacité à bien performer sur les deux classes (décès et non-décès) est la priorité, **le modèle KNN** pourrait être préféré en raison de son score de précision équilibrée supérieur.
- **Cependant, si la capacité à distinguer précisément entre les patients qui décéderont et ceux qui ne le feront pas est plus importante**, ce qui est souvent le cas dans les contextes médicaux où minimiser les faux positifs et faux négatifs est crucial, **le modèle de régression logistique** est nettement le meilleur choix, en raison de son score AUC très supérieur.
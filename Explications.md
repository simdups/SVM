L'objectif principal de ce projet était de développer un modèle de classification pour prédire l'état de santé des arbres en utilisant des mesures spectrales, notamment les bandes rouge, verte et infra-rouge. Le projet a impliqué plusieurs étapes, incluant la construction et l'évaluation de modèles, ainsi que l'exploration de méthodes d'interprétabilité des modèles via des outils comme PFI, PDP et ICE.

1. Analyse descriptive des données :

Importation et traitement des données : La première étape a consisté à importer et à préparer les données. Cela a inclus la gestion des valeurs manquantes (NA), avec l'application de techniques de remplacement adaptées afin d'éviter toute perte d'informations critiques. J'ai également mené une analyse détaillée de la répartition des classes, constatant un déséquilibre marqué entre les classes "arbre sain" et "arbre malade".

Standardisation et gestion des valeurs aberrantes : Pour garantir que les différentes échelles des variables spectrales n'influencent pas les résultats des modèles, j'ai standardisé les données. Une attention particulière a été portée à la détection et à l'élimination des valeurs aberrantes, en particulier pour les variables spectrales, afin de ne pas fausser les analyses.

Analyse de corrélation : Une analyse de corrélation a été réalisée pour identifier les relations entre les différentes variables. Cette étape a permis de repérer les variables les plus influentes pour la prédiction de l'état des arbres. Les résultats ont montré que certaines bandes spectrales, telles que la bande rouge et infra-rouge, étaient particulièrement pertinentes pour la classification.

Répartition des classes : J'ai étudié la répartition des classes et observé un déséquilibre notable, avec une majorité d'arbres sains et une proportion beaucoup plus faible d'arbres malades. Ce déséquilibre a conduit à l'application de la technique SMOTE pour rééchantillonner les données et améliorer les performances des modèles de classification.

2. Modèles utilisés :

Gradient Boosting (GB) et SVM : J'ai testé deux modèles classiques de classification, le Gradient Boosting et le SVM, pour prédire l'état de santé des arbres. Le modèle GB a mieux prédit les arbres sains, tandis que le SVM a légèrement mieux détecté les arbres malades. En fin de compte, les performances des deux modèles étaient assez similaires, en particulier après l'application de la méthode d'oversampling SMOTE pour corriger le déséquilibre des classes.

3. Tuning du modèle :

J'ai tenté d'améliorer les performances des modèles en réalisant une étape de tuning des hyperparamètres pour le modèle SVM. Cependant, malgré plusieurs tentatives pour optimiser ce modèle, l'étape de tuning n'a pas permis d'améliorer les résultats comme prévu.

4. Interprétation des résultats :

L'analyse des variables spectrales a montré que la bande rouge (Mean_R) joue un rôle crucial dans la classification des arbres malades. En effet, plus la moyenne de la bande rouge augmente, plus la probabilité que l'arbre soit malade est élevée, car les arbres malades tendent à réfléchir plus de lumière dans cette bande, ce qui reflète des altérations structurelles. En revanche, pour la bande verte (Mean_G), c'est l'inverse : plus la moyenne diminue, plus la probabilité d'un arbre malade augmente. Cela peut être expliqué par le fait que les plantes saines réfléchissent davantage la lumière verte, tandis que les arbres malades en perdent cette capacité en raison de la dégradation des tissus. Enfin, la bande infra-rouge (Mean_NIR) n'a montré aucun impact significatif dans ce modèle, probablement parce que l'information qu'elle fournit est déjà bien captée par les autres bandes. L'analyse des PDP individuels a confirmé que les bandes rouge et verte sont les plus discriminantes pour prédire l'état de santé des arbres.

5. Limitations et difficultés :

La gestion du déséquilibre des classes a été l'une des principales difficultés rencontrées. Malgré l'application de SMOTE, le modèle a continué à rencontrer des challenges pour classifier correctement la classe minoritaire (arbres malades).

L'étape de tuning du modèle SVM, ainsi que l'utilisation des méthodes d'interprétabilité SHAP, n'ont pas produit les résultats escomptés. Le tuning n'a pas permis d'améliorer significativement les performances, et l'application de SHAP a été limitée par la complexité du calcul des valeurs SHAP avec un modèle SVM.

6. Perspectives :

Malgré les difficultés rencontrées, ce projet a permis de démontrer l'importance des variables spectrales pour la classification des arbres malades. À l'avenir, il serait intéressant d'explorer d'autres techniques de tuning ou d'envisager l'utilisation de modèles basés sur des arbres, qui sont mieux adaptés à l'application de méthodes d'interprétabilité telles que SHAP.

De plus, une exploration approfondie des techniques d'oversampling ou des méthodes d'optimisation pourrait potentiellement améliorer les performances des modèles pour mieux gérer le déséquilibre des classes et affiner les prédictions des arbres malades.
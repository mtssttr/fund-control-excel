# Vérification de l'édition publique

Le classeur utilise des cours et des opérations entièrement fictifs. Le jeu de référence a été calculé avant l'introduction des six anomalies.

Le moteur de calcul a passé **18 tests**, couvrant notamment :

- détection des six anomalies au 24 septembre ;
- rapprochement des positions, espèces et actif net après les cinq corrections justifiées ;
- règlement tardif de TR-017, puis rapprochement complet au 25 septembre ;
- refus d'une VL valide lorsqu'un cours manque ou qu'un identifiant de cours est dupliqué ;
- conservation des notes d'investigation après rechargement des mêmes lignes ;
- extension à un onzième jour sans réécrire les formules.

La VL de référence du 25 septembre est **100,264110 EUR par part**, pour un actif net de **1 002 641,10 EUR**. Le classeur enregistré présente cette valeur et indique « Contrôles rapprochés ».

L'archive `.xlsx` a été validée comme fichier ZIP et ses huit feuilles ont été lues sans erreur. Le classeur contient neuf requêtes Power Query, un tableau croisé dynamique et un graphique natif. L'exécution de **Données > Actualiser tout** et l'actualisation du tableau croisé dans une session Excel locale restent à confirmer. Les tests de rechargement mentionnés ci-dessus portent sur le modèle de calcul, pas sur l'exécution native des requêtes.

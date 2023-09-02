Tableau de Bord pour le Suivi des Prêts Immobiliers au Crédit Breton

Ce tableau de bord a été conçu pour fournir une vue complète et détaillée de l'activité des prêts immobiliers au sein des agences du Crédit Breton.

Présentation du Dashboard

Le tableau de bord se compose de plusieurs pages, chacune fournissant des informations spécifiques pour mieux comprendre et analyser les demandes de prêts et les performances des agences du Crédit Breton.

1.	Page "Demandes de Prêt"

Cette page présente des statistiques détaillées concernant les demandes de prêts immobiliers :

•	Historique des Demandes : Visualisez l'historique temporel des demandes de prêts.
•	Évolution du Taux des Prêts Acceptés : Suivez la fluctuation du taux de prêts acceptés au fil du temps.
•	Évolution du Montant Moyen des Opérations : Explorez les variations du montant moyen des prêts accordés.
•	Dossiers en Cours de Traitement : Identifiez les demandes de prêts en attente de traitement.
 



 2. Page "Performance des Agences"

Cette page permet de comparer la performance des différentes agences du Crédit Breton :

•	Localisation des Agences : Visualisez la répartition géographique des agences.
•	Nombre de Demandes Reçues par Agence : Identifiez les agences avec le plus grand nombre de demandes.
•	Classement des Agences par Nombre de Demandes : Obtenez un classement des agences en fonction du nombre de demandes reçues.
•	Taux d'Acceptation des Prêts par Agence : Analysez le taux d'acceptation des prêts pour chaque agence.
 
 3. Page "Indicateurs Clients"

Cette page met en avant les informations relatives aux clients :
•	Date de Naissance et Demandes de Prêts : Visualisez la corrélation entre la date de naissance des clients et le nombre de demandes de prêts.
 
 4. Page "Liste Clients"

Cette page offre une vue détaillée de la situation des clients et de leurs demandes de prêts.
 

Données Utilisées

Les données utilisées pour ce tableau de bord proviennent d'un fichier Excel contenant des informations sur les clients, les demandes de prêts, les agences et d'autres indicateurs 
pertinents. Les données ont été soigneusement nettoyées pour garantir leur précision et leur fiabilité.

Algorithme de Critères d'Acceptation des Demandes de Prêt

Une des caractéristiques clés de ce tableau de bord est l'implémentation d'un algorithme de critères d'acceptation des demandes de prêt. Cet algorithme automatise le processus d'évaluation des demandes et détermine si elles sont acceptées ou refusées en fonction de critères spécifiques, tels que l'âge du client, la régularité des revenus et la capacité de remboursement.

Utilisation de la Formule DAX

La formule DAX (Data Analysis Expressions) est utilisée pour mettre en œuvre ces critères d'acceptation dans Power BI. La formule DAX permet de manipuler et d'analyser les données en fonction de diverses conditions, ce qui permet de déterminer automatiquement si une demande de prêt est acceptée ou refusée en fonction des critères énoncés ci-dessus.

voici la formule utilisée : 
Score_emprunteur = IF(LOOKUPVALUE('Situation famille'[Age_ client],'Situation famille'[ID_Client],'Demandes de pret'[Numéro client])>=82,"REFUS",IF(LOOKUPVALUE('Situation pro'[Régularité des revenus],'Situation pro'[Numéro client],'Demandes de pret'[Numéro client])== "3 : Très irréguliers","REFUS",IF(([Montant_prété]/'Demandes de pret'[Durée])>LOOKUPVALUE('Situation pro'[Revenu mensuel moyen],'Situation pro'[Numéro client],'Demandes de pret'[Numéro client])/(3+LOOKUPVALUE('Situation famille'[Nombre d'enfants à charge],'Situation famille'[ID_Client],'Demandes de pret'[Numéro client])),"REFUS","ACCEPTE")))


Comment Accéder au Tableau de Bord


Suivez ces étapes pour accéder au tableau de bord :

1.	Installer Power BI Desktop : Si vous n'avez pas déjà Power BI Desktop installé, téléchargez et installez-le depuis le site officiel de Power BI.

2.	Ouvrir le Fichier : Téléchargez le fichier du tableau de bord (format .pbix) depuis ce référentiel GitHub.

3.	Importer les Données : Dans Power BI Desktop, importez le fichier Excel contenant les données nettoyées.

4.	Explorer les Pages : Une fois le fichier ouvert dans Power BI Desktop, naviguez entre les différentes pages pour explorer les statistiques et les indicateurs.


Remarque Importante

Assurez-vous de respecter toute politique de confidentialité ou de sécurité liée aux données utilisées dans ce tableau de bord.


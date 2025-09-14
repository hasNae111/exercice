Contexte : Gestion d’un Restaurant
Vous êtes chargé de développer une petite application de gestion pour un restaurant. L'objectif est de modéliser et interagir avec la base de données du restaurant, permettant de gérer les plats, les catégories, les commandes, et les clients.

Le restaurant veut suivre :
Les plats disponibles (nom, prix, description, catégorie).
Les commandes passées par les clients (date, contenu, total).
Les clients (nom, email).
Les catégories de plats (ex : Entrée, Plat principal, Dessert, Boisson).

Structure des Tables
categories(id (PK), nom (ex: Entrée, Dessert))
plats(id (PK), nom, prix, description, categorie_id (FK vers categories))
clients, id (PK), nom, email
commandes(id (PK), client_id (FK vers clients), date_commande, total)
commande_plats (commande_id (FK vers commandes), plat_id (FK vers plats), quantite)
Requêtes à réaliser: 

Créer les tables dans PostgreSQL en utilisant SQLAlchemy.
Insérer les données suivantes (voir plus bas).
Lister tous les plats triés par prix décroissant.
Lister tous les plats dont le prix est compris entre 30 et 80.
Afficher les clients dont le nom commence par "S".
Afficher les plats avec leur nom de catégorie.
Lister les commandes avec le nom du client et la date.
Pour chaque commande, afficher les plats commandés avec leur quantité.
Afficher le nombre de plats pour chaque catégorie.
Afficher le prix moyen des plats par catégorie.
Afficher le nombre de commandes par client.
Afficher les clients ayant passé plus d’une commande.
Lister les plats commandés plus de deux fois avec leur total de quantités.
Lister les commandes du mois de juillet 2025.
Afficher la commande la plus récente (avec le nom du client).
Afficher les clients ayant passé une commande d’un montant supérieur à 100.
Afficher les plats plus chers que la moyenne des plats (via sous-requête).
Mettre à jour le prix du plat "Pizza Margherita" à 75.
Ajouter un nouveau plat dans la catégorie "Boisson" depuis Python.
Supprimer le client "Youssef El Khalfi" et toutes ses commandes associées.

Afficher pour chaque client :
Son nom,
Le nombre total de plats commandés,
Le montant total dépensé.
Lister les 3 plats les plus commandés (par quantité totale).
Afficher les clients et leurs dernières commandes
Créer une vue virtuelle (select) qui affiche :
le nom du client,
les plats commandés,
les quantités,
et la date de la commande.

Données à insérer:
categories:


id	nom
1	Entrée
2	Plat principal
3	Dessert
4	Boisson

plats:
id	nom	prix	description	categorie_id
1	Salade César	45	Salade avec poulet	1
2	Soupe de légumes	30	Soupe chaude de saison	1
3	Steak frites	90	Viande grillée et frites	2
4	Pizza Margherita	70	Pizza tomate & mozzarella	2
5	Tiramisu	35	Dessert italien	3
6	Glace 2 boules	25	Glace au choix	3
7	Coca-Cola	15	Boisson gazeuse	4
8	Eau minérale	10	Eau plate ou gazeuse	4

clients:
id	nom	email
1	Amine Lahmidi	amine@example.com
2	Sara Benali	sara.b@example.com
3	Youssef El Khalfi	youssef.k@example.com

commandes:

id	client_id	date_commande	total
1	1	2025-07-07 12:30:00	120
2	2	2025-07-07 13:00:00	85
3	1	2025-07-08 19:45:00	150

commande_plats:



commande_id	plat_id	quantite
1	1	1
1	3	1
1	7	2
2	2	1
2	4	1
2	8	1
3	3	1
3	5	1
3	7	1


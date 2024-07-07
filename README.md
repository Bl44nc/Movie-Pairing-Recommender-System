# Movie-Pairing-Recommender-System

Bonjour, je n'ai pas reussi la phase de recommendation du projet je n'arrivais pas à traiter mes données pour les faire marcher avec le model NN que j'essayais d'utiliser.



1. **Data Collection and Preprocessing**

J'ai utilisé les dataset de MovieLens et title_basics et title_ratings de imdb.

En premier lieu j'ai traité le dataset movies pour que les titres correspondent à ceux de title_basics.

J'ai merge title_basics et tile_ratings en faisant un peu de preprocessing que j'explique dans mon notebook.

Enfin je merge movies et le nouveau dataset issu de imdb en fonctions des titres et des années.

2. **Feature Engineering**

J'ai ajouté les colonnes de chaque genres pour chaque user, la valeur de ces colonnes correspond à la moyenne des notes que l'utilisateur a donné pour ce genre de film.

3. **Model Development**

Tout d'abord j'ai essayé de faire les recommendations avec un SVD sauf que je me suis rendu compte qu'en utilisant ce model mes vecteurs de features des users et movies ne seraient pas utilisé. Car svd n'utilise que la matrix user x movie obtenu en faisant le pivot de ratings.


J'ai donc ensuite essayé un réseau de neurones car cela se prétait mieux au traitement de donné que j'avais entrepris.
* les genres sont en hot-encoded-one dans le vecteur de movie_feature
* les moyennes de note par genre sont en hot-encoded-one dans le vecteur de user_feature 

le réseau de neurones prend en entré mes vecteurs de features des utilisateurs et films et me renvois un rating pour chaque film par utilisateurs.


 Cependant je n'ai pas réussi à adapter mes données au même format que le cours et je n'ai donc pas réussi cette étape.

4. **Recommendation Algorithm**

Je comptais prédir les films avec le plus de ratings pour les deux users dans le couple. Ensuite regarder le film le plus haut dans la liste des ratings pour les deux users. Et cela m'aurait donnée un film dont les deux users en couple le plus aimé.

5. **Evaluation**


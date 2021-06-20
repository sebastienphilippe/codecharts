# Comment générer les heatmap ?

# 3 partie : 
    - Générer les données pour le test
    - Faire le test du formulaire sur la page web et téléchargé le résultat
    - Utiliser le résulat pour la génération des heatmap


# 1 Génération des données pour le test

Supprimer tout le contenu du répertoire "assets/task/data" c'est dans ce folder que seront générés touts les données utiles pour le tests.

Avant de lancer le serveur et commencé le test, et il faut avoir un folder avec les images que l'on veux tester. Ce folder a été crée il se nomme "photo_pub", vous pouvez y placez toutes les photos de pub à tester. Ensuit il faut dire a l'application t'utiliser ce folder pour ce faire vous devez regarder le notebook "main.ipynb" qui contient tout le code python afin de générer les données pour le test.

Vous trouverez dans les premières cellules le code qui permet de définir les images a utiliser 

sourcedir = '../photo_pub/' # ici vous pouvez voir le chemin pour récupérer les imgaes de pub
tutorial_source_dir = 'tutorial_images' # ici ce trouve le chemin des images pour les images tutoriels si vous souhaitez les changer 

vous trouverez plus bas la cellule pour indiquer les paramètres important pour la génération 


voice les paramètres que nous avons mis en place libre a vous de les modifiez

PARAMETERS for generating subject files

num_subject_files = 3     # number of subject files to generate (i.e., # of mturk assignments that will be put up)    

num_images_per_sf = 3    # number of target images per subject file 

num_imgs_per_tutorial = 2 # number of tutorial images per subject file

num_sentinels_per_sf = 1  # number of sentinel images to distribute throughout the experiment (excluding the tutorial)

add_sentinels_to_tutorial = True # whether to have sentinel images as part of the tutorial

num_sentinels_per_tutorial = 1   # number of sentinel images to distribute throughout the tutorial

Pour générer toutes les données pour le test il vous suffit d'executer toute les cellulles, normalement vous devriez voir que votre folder "assets/task/data" n'est plus vide.

# 2 Lancer le tests sur la page web 

Avant de lancer le serveur pour le test avec le formulaire il vous est possible de modifié certains paramètres comme la durée d'affichages des images de deux façons:
 - via le fichier "custom.js" que vous trouverez dans "assets/js"
 - directement avec l'url

nous l'avons fait avec la deuxième options que nous allons expliquer plus tard

Il faut lancer le serveur avec une ligne de commande via un terminal, nous utilisons visual studio code depuis le début dans l'onglet "Terminal" qui se trouve en Haut de l'application de vscode. Faites "New Terminal" et un terminal s'ouvriras, il faudras vous mettre à la racine du projet pour savoir si vous êtes à la racine vérifiez que vous avez bien un texte "(merging)"
qui se trouver à coté de l'emplacement du projet.

exemple : d******************** MINGW64 ~/pub_project/codecharts (merging)


vous trouverez un symbole $ juste en dessous taper cette ligne de commande afin de lancer le serveur : py -m http.server

normalement le serveur devrais être lancé clicker sur ce lien : http://localhost:8000/

pour pouvoir mettre une durée entre chaque image via l'url vous devez rajouter ce texte dans l'url : ?msecImg=1000
et modifier le nombre selon vos besoin et la durée est exprimé en millisecondes.
voci un exemple d'un test avec 5 secondes entre les images : localhost:8000/?msecImg=5000

Enfin vous pourrez commencé le tests et à la fin téléchrager le résultat.

# 3 Utilisez le résultat pour la génération des heatmap

Récupérez le fichier puis mettez le dans le folder "data-analysis".
Pour la partie de génération des heatmap il faut se référer au notebook "plot_data.ipynb"

Dans une des premières cellues vous trouverez cette partie de code 

useDEMOfile = True # set to False if you will be providing your own data_path below
data_path = ''     # if you want to provide your own codecharts results file, add it here

if useDEMOfile: 
    data_path = "my_result_6.json"

pour pourvoir utilisez notre résulat pour générer les heatmap il faut que la variable "useDEMOfile" soit a True, pour utilisez une nouvelles données vous devez donner le nom de votre fichier de résulat dans la variable "data_path"

exemple :  à la fin du test vous avez télécharger le fichier et l'avez appelé "my_result_7.json"

il vous suffit de faire : data_path = "my_result_7.json"

Enfin executer toute les cellues puis vous verrez aparaitre sur vos différentes images de pub les heatmap qui ont étés générés

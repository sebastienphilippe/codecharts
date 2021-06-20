# Comment générer les heatmap ?

# 3 partie : 
    - Générer les données pour le test
    - Faire le test du formulaire sur la page web
    - Télécharger le fichier pour la génération des heatmap


# 1 partie Génération des données pour le test

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


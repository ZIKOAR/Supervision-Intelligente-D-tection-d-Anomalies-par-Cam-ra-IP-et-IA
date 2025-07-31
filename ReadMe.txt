📁 Structure du projet
1. Dossier dist dans (Application)
Contient le fichier exécutable main_with_automate.exe

Il s'agit de l'application à lancer pour démarrer l’interface utilisateur.

Lors de l’exécution, les dossiers de données et d’historiques sont automatiquement générés dans ce même dossier (à côté de l’exécutable).

2. Dossier codes (Code source et modèle IA)
Contient :

le fichier last_model.pt (modèle entraîné)

deux scripts Python :

un script pour lancer l’IA sans connexion automate

un autre script pour l’analyse IA avec connexion automate (via Ethernet/PLC)

📁 Dossiers générés automatiquement
rendement/
➤ Contient le suivi de la production par shift :

nombre de balancelles vides, bien accrochées, mal accrochées

results/
➤ Archive les résultats de détection IA sous forme de fichiers Excel :

incluant la classe, la confiance, la date et l’heure

ainsi que les coordonnées des boîtes de détection

annotations_images/
➤ Sauvegarde les images recadrées des zones détectées :

chaque image est nommée selon sa date et heure de détection

🧭 Étapes à suivre
Lancer l’application (main_with_automate.exe dans le dossier dist)

Remplir les paramètres de connexion automate (IP, rack, slot, etc.)

⚙️ Utiliser les boutons :

Stop chaîne : envoie le bit 0 (arrêt de la chaîne)

Continuer chaîne : envoie le bit 1 (reprise de la chaîne)

Se connecter à la caméra

Lancer l’analyse IA

Une fois activée, l’analyse ne prend en compte que les objets entrant dans une zone de détection définie (rectangle vert) affichée à l’écran.

Les détections sont automatiquement :

enregistrées dans un fichier Excel (results/)

accompagnées de leur image correspondante (annotations_images/)

utilisées pour le comptage par type de balancelle (bien accrochée, non accrochée, vide) stocké dans rendement/

🔄 Gestion des shifts
À la fin de chaque shift, les compteurs visibles dans l’interface sont automatiquement réinitialisés.
Le système conserve les historiques pour chaque shift indépendamment.

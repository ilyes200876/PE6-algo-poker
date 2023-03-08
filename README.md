#  Tri
# - Créer un type Carte, caractérisé par une couleur et une valeur
# - Créer une méthode comparerCouleur(Carte c) qui compare la carte courante et la carte passée en paramètre. Elle renvoie -1 si la couleur de la carte courante est AVANT celle de la carte passée en paramètre, 0 si elles ont la même couleur, et 1 si sa couleur est APRÈS celle de la carte passée en paramètre. L'ordre naturel des couleurs est Trèfle - Carreau - Coeur - Pique

# - Créer une méthode comparerValeur(Carte c) sur le même principe. Prendre l'ordre des cartes d'un jeu de poker (du 2 le plus petit à l'as le plus haut)

#  - Créer un type Main, qui contient une liste de cartes.
# - Dans le type Main, ajouter une méthode trier() qui permet de trier la main : en premier dans la liste doivent se trouver les trèfles triés du plus petit au plus grand, puis les carreaux, etc.
Type Carte
  Déclarer couleur["Trèfle", "Carreau", "Coeur", "Pique"]
  Déclarer valeur["2", "3", "4", "5", "6", "7", "8", "9", "10", "Valet", "Dame", "Roi", "1"]
  FONCTION comparerCouleur(Carte c)
  DÉBUT
      SI c(this.couleur) = this.couleur[0] ALORS
        RETOURNE 0
      FINSI
      SI carte c(this.couleur) <> this.couleur[0] ALORS
        RETOURNE -1
      ELSE
        RETOURNE 1
      FINSI
  FIN
  FONCTION comparerValeur(Carte c)
  DÉBUT
      SI c(this.valeur) = this.valeur[0] ALORS
        RETOURNE 0
      FINSI
      SI carte c(this.valeur) <> this.valeur[0] ALORS
        RETOURNE -1
      ELSE
        RETOURNE 1
      FIN
FIN Type

Type Main
  Déclarer liste
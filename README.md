#  Tri
# - Créer un type Carte, caractérisé par une couleur et une valeur
# - Créer une méthode comparerCouleur(Carte c) qui compare la carte courante et la carte passée en paramètre. Elle renvoie -1 si la couleur de la carte courante est AVANT celle de la carte passée en paramètre, 0 si elles ont la même couleur, et 1 si sa couleur est APRÈS celle de la carte passée en paramètre. L'ordre naturel des couleurs est Trèfle - Carreau - Coeur - Pique

# - Créer une méthode comparerValeur(Carte c) sur le même principe. Prendre l'ordre des cartes d'un jeu de poker (du 2 le plus petit à l'as le plus haut)

#  - Créer un type Main, qui contient une liste de cartes.
# - Dans le type Main, ajouter une méthode trier() qui permet de trier la main : en premier dans la liste doivent se trouver les trèfles triés du plus petit au plus grand, puis les carreaux, etc.
Type Carte
  Déclarer couleur
  Déclarer valeur
    FONCTION comparerCouleur(Carte c)
    DÉBUT
        SI this.couleur = c.couleur ALORS
            Renvoyer 0
        FINSI
        Déclarer ordre_couleurs <- [
            "Trèfle" => 1,
            "Carreau" => 2,
            "Coeur" => 3,
            "Pique" => 4
        ]
        Déclarer ordre_ma_couleur <- ordre_couleurs[this.couleur]
        Déclarer ordre_couleur_c <- ordre_couleurs[c.couleur]
         // SI ma couleur est avant celle de c ALORS
         //SI l'ordre de ma couleur < l'ordre de la couleur c ALORS
         SI ordre_ma_couleur < ordre_couleur_c ALORS
            Renvoyer -1
        FINSI
        Renvoyer 1
    FIN
  FONCTION comparerValeur(Carte c)
  DÉBUT
      SI c.valeur = this.valeur ALORS
          RETOURNE 0
      FINSI
      Déclarer ordre_valeurs <- [
            "2" => 1,
            "3" => 2,
            "4" => 3,
            "5" => 4,
            "6" => 5,
            "7" => 6,
            "8" => 7,
            "9" => 8,
            "10" => 9,
            "Valet" => 10,
            "Dame" => 11,
            "Roi" => 12,
            "AS" => 13
        ]
      Déclarer ordre_ma_valeur <- ordre_valeurs[this.couleur]
      Déclarer ordre_valeur_c <- ordre_valeurs[c.couleur]
      SI ordre_ma_valeur < ordre_valeur_c ALORS
            Renvoyer -1
        FINSI
        Renvoyer 1
    FIN
FIN Type

Type Main
    Déclarer cartes[]
          CN1 : cartes[ "Deux de Trèfles", "Trois de Trèfles"]
            => cartes[ "Deux de Trèfles", "Trois de Trèfles"]
        CN2 : cartes[ "Trois de Carreau", "Deux de Carreau"]
            => cartes[ "Deux de Carreau", "Trois de Carreau"]
        CN3: cartes[ "Deux de Trèfles", "Deux de Carreau"]
            => cartes[ "Deux de Trèfles", "Deux de Carreau"]
        CN4: cartes[ "Deux de Carreau", "Deux de Trèfles"]
            => cartes[ "Deux de Trèfles", "Deux de Carreau"]
        CN5: cartes[ "Deux de Coeur", "Trois de Pique"]
            => cartes[ "Deux de Trèfles", "Deux de Carreau"]
        CN6: cartes[ "Deux de Pique", "Trois de Trèfles"]
            => cartes[ "Deux de Trèfles", "Deux de Carreau"]
    */
    PROCÉDURE trier()
    DÉBUT
        
        // À compléter avec l'algo de tri que vous préférez, voir Wikipédia
        SI this.cartes[0].comparerCouleur(this.cartes[1]) = 1
            OU
            (this.cartes[0].comparerCouleur(this.cartes[1]) = 0 
            ET this.cartes[0].comparerValeur(this.cartes[1]) = 1) ALORS
            Déclarer Carte temp
            temp <- this.cartes[0]
            this.cartes[0] <- this.cartes[1]
            this.cartes[1] <- temp
        FINSI
        
    FIN
FINSI
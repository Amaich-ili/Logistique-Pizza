# Iliass Amaich

class Pizza:
    PI = 3.1416

    def __init__(self, rayon = 0.0, diametre = 0.0, cout = 0.0) -> None:
        self.rayon = rayon
        self.diametre = diametre
        self.cout = cout
    
    #Creer des objets
    @staticmethod
    def creerpizza():
        diametre = int(input("Entrer le diametre on pouces de ton pizza : "))
        prix = int(input("Entrer le cout de ton pizza : "))
        rayon = diametre / 2
        return [rayon, diametre, prix]
    
    def aire_pizza(self):
        return Pizza.PI * (self.rayon)**2
        
    def __str__(self):
        return (f"Pizza : {(self.diametre)}'' -> {(self.cout)} $")


class Boite:

    def __init__(self, longueur = 0.0, largeur = 0.0) -> None:
        self.longueur = longueur
        self.largeur = largeur

    #Creer des objets
    @staticmethod
    def creerboite():
        longueur = float(input("Entrer la longueur on centimetre de la boite : "))
        largeur = float(input("Entrer la largeur on centimetre de la boite : "))
        return [longueur, largeur]

    def aire_boite(self):
        return self.longueur * self.largeur
    
    def __str__(self):
        return (f"Boite : {self.longueur} * {self.largeur} cm")


# Afficher les elements de la liste
def affichage(liste):
    for index, value in enumerate(liste):
        print(f"\t{index + 1}.  {value}")


def menu():
     
    liste_pizza = []
    liste_boite = []
    condition = True

    while condition:
        choix = input("\n[1] Créer une nouvelle pizza \n[2] Créer une nouvelle boîte \n[3] Voir la liste de pizzas \n[4] Voir la liste de boîtes \n[5] Comparer spécial 2 pour 1 \n[6] Mettre une pizza dans une boîte\nVotre choix : ")
        
        if choix == "1" :
            attribut_pizza = Pizza.creerpizza()
            liste_pizza.append(Pizza(attribut_pizza[0], attribut_pizza[1], attribut_pizza[2]))

        elif choix == "2" :
            attribut_boite = Boite.creerboite()
            liste_boite.append(Boite(attribut_boite[0], attribut_boite[1]))

        elif choix == "3" :
            for pizza in liste_pizza:
                print(pizza)

        elif choix == "4" :
            for boite in liste_boite:
                print(boite)

        elif choix == "5" :

             # Afficher la liste des pizzas
            print("\nVoici les pizzas disponibles ")
            affichage(liste_pizza)
                        
            # Demander a l'utilisateur de choisir un pizza
            pizza_choix = int(input("\nQuel pizza vous voulez ? "))
            pizza_choisi = liste_pizza[pizza_choix-1]
            aire1 = pizza_choisi.aire_pizza()*2
            
            # Demander a l'utilisateur de choisir un prix
            prix = int(input("Entrer un prix parmi la liste : "))

            # Afficher la nouvelle liste des pizzas depend du prix choisi
            new_liste = []

            for pizza in liste_pizza:
                if pizza.cout == prix :
                    new_liste.append(pizza)
            affichage(new_liste)
            
            # Demander a l'utilisateur de choisir un pizza
            nv_choix = int(input("\nQuel pizza vous voulez ? "))
            pizza_special = new_liste[nv_choix-1]
            aire2 = pizza_special.aire_pizza()
            
            
            if aire1 > aire2:
                print("\nVous n'avez pas pris la bonne décision !! Sera mieux de prendre le special")
            else:
                print("\nVous avez fait un bon choix :-) tu as bien profite du special ")
            
        elif choix == "6" :

            print("\nVoici les pizzas disponibles ")
            # Afficher la liste des pizzas
            affichage(liste_pizza)

            print("\nVoici les boites disponibles ")
            # Afficher la liste des boites
            affichage(liste_boite)
                
            # Demander a l'utilisateur de choisir un pizza et une boite
            pizza_choisi = int(input("\nChoisisez un pizza : "))
            boite_choisi = int(input("Choisisez une boite : "))

            # Reperer le pizza et la boite dans la liste
            pizza_embaler = liste_pizza[pizza_choisi-1]
            boite_embaler = liste_boite[boite_choisi-1]

            # Determine la petite valeur entrer par l'utilisateur
            minimum_valeur = min(boite_embaler.largeur, boite_embaler.longueur )

            if ((pizza_embaler.rayon)* 2.54) < minimum_valeur:
                print("\nOn peut emballer votre pizza ")
            else:
                print("\nDésolé ! On ne peut pas emballer votre pizza ")

        else:
            condition = False
menu()
        

# java_interface
# Java Order Management System

This project is a simple Java-based order management system. It allows you to manage clients, products, and orders, and calculate the total invoice amount for a given order.

## Project Structure

- `src/Client.java`: Defines the `Client` class with attributes `id` and `nom`.
- `src/LigneCommande.java`: Defines the `LigneCommande` class with attributes `produit`, `prix`, and `quantite`.
- `src/Main.java`: The main entry point of the application. It creates instances of `Metier`, `Produit`, `LigneCommande`, and `Client`, and calculates the invoice for a sample order.
- `src/Metier.java`: Implements the `IMetier` interface, providing methods to manage orders and calculate invoices.

## Classes

### Client

Represents a client with an ID and a name.

### LigneCommande

Represents a line item in an order, including the product, price, and quantity.

### Main

The main class that initializes the application and demonstrates its functionality.

### Metier

Implements the business logic for managing clients, products, and orders.

## Usage

1. Clone the repository.
2. Open the project in IntelliJ IDEA.
3. Run the `Main` class to see the sample output.

## Example

The `Main` class demonstrates how to create clients, products, and orders, and how to calculate the total invoice amount for an order.

```java
public class Main {
    public static void main(String[] args) {
        // Create instance of Metier
        Metier metier = new Metier();

        // Create some products
        Produit produit1 = new Produit(1, "Laptop", 1.0);
        Produit produit2 = new Produit(2, "Smartphone", 00.0);
        Produit produit3 = new Produit(3, "Headphones", 1.0);

        LigneCommande lc1 = new LigneCommande(produit1, 1200, 10);
        LigneCommande lc2 = new LigneCommande(produit2, 3200, 8);
        LigneCommande lc3 = new LigneCommande(produit3, 200, 9);

        Client c1 = new Client(1, "mehdi");
        Client c2 = new Client(2, "omar");
        Client c3 = new Client(3, "salah");

        ArrayList<LigneCommande> al = new ArrayList<>();
        al.add(lc1);
        al.add(lc2);
        al.add(lc3);

        Commande cmd1 = new Commande(1, al, c1, "23-04-2005");
        IMetier ts = new Metier();

        System.out.println(ts.calculFacture(cmd1));
    }
}

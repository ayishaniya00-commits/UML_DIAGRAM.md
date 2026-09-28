# UML Class Diagram - Shopping Application

```mermaid
classDiagram
    direction TB

    class Product {
        <>
    }

    class ClothingProduct {
    }

    class ElectronicsProduct {
    }

    class Customer {
    }

    class ShoppingService {
    }

    class PaymentProcessor {
    }

    class Payment {
        <>
    }

    class PaymentMethod {
    }

    Product <|-- ClothingProduct : inherits
    Product <|-- ElectronicsProduct : inherits
    Payment <|.. PaymentProcessor : implements
    ShoppingService --> Product : manages
    ShoppingService --> Customer : involves
    PaymentProcessor --> PaymentMethod : uses

# UML Class Diagram - Shopping Application

```mermaid
classDiagram
    direction TB

    class Product {
        <<interface>>
        +String productId
        +String name
        +double price
    }

    class ClothingProduct {
        +String size
        +String color
    }

    class ElectronicsProduct {
        +int warrantyPeriod
        +String brand
    }

    class Customer {
        +String customerId
        +String name
        +String email
        +placeOrder()
    }

    class ShoppingService {
        +addProduct()
        +removeProduct()
        +calculateTotal()
    }

    class PaymentProcessor {
        +processPayment()
    }

    class Payment {
        <<interface>>
        +pay()
    }

    class PaymentMethod {
        +String cardNumber
        +String cardHolder
    }

    Product <|-- ClothingProduct : inherits
    Product <|-- ElectronicsProduct : inherits
    Payment <|.. PaymentProcessor : implements
    ShoppingService --> Product : manages
    ShoppingService --> Customer : involves
    PaymentProcessor --> PaymentMethod : uses

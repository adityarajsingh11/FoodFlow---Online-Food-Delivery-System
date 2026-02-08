
# 🍽️ FoodFlow – Online Food Delivery System

FoodFlow is a **Low-Level Design (LLD)** based implementation of an **Online Food Delivery System**, inspired by real-world platforms like Zomato and Swiggy.  
This project focuses on **clean object-oriented design**, **scalability**, and **industry-standard design patterns** using **C++**.

---

## 🚀 Features

- Search restaurants by location  
- Select restaurant and browse menu  
- Add food items to cart  
- Place **Delivery** or **Pickup** orders  
- Support for **Immediate** and **Scheduled** orders  
- Multiple payment methods (UPI, Credit Card)  
- Order notifications after successful payment  

---

## 🧠 Design Goals

- Clean separation of concerns  
- Easily extendable architecture  
- Real-world system modeling  
- Interview-ready Low-Level Design  

---

## 🏗️ Project Architecture

```

OnlineFoodOrderingSystem/
│
├── Main.cpp                    # Application entry point (Happy Flow)
├── TomatoApp.h                 # Facade class (System Controller)
│
├── models/
│   ├── User.h
│   ├── Restaurant.h
│   ├── MenuItem.h
│   ├── Cart.h
│   ├── Order.h                # Abstract base class
│   ├── DeliveryOrder.h
│   ├── PickupOrder.h
│
├── managers/
│   ├── RestaurantManager.h    # Singleton
│   ├── OrderManager.h         # Singleton
│
├── strategies/
│   ├── PaymentStrategy.h      # Strategy interface
│   ├── UpiPaymentStrategy.h
│   ├── CreditCardPaymentStrategy.h
│
├── factories/
│   ├── OrderFactory.h         # Factory interface
│   ├── NowOrderFactory.h
│   ├── ScheduledOrderFactory.h
│
├── services/
│   └── NotificationService.h
│
├── utils/
│   └── TimeUtils.h

```

---

## 🧩 Core Components

### 🔹 User
Represents a customer using the application.  
Each user owns a **Cart** (Composition relationship).

---

### 🔹 Restaurant & MenuItem
- `Restaurant` holds restaurant details and menu  
- `MenuItem` represents individual food items  

---

### 🔹 Cart
- Temporarily stores selected food items  
- One cart is associated with **one restaurant only**

---

### 🔹 Order (Abstract Class)
Base class for all orders.

**Concrete Implementations:**
- `DeliveryOrder`
- `PickupOrder`

Supports **runtime polymorphism**.

---

### 🔹 PaymentStrategy (Strategy Pattern)
Encapsulates payment logic.

**Implementations:**
- UPI Payment
- Credit Card Payment  

Allows adding new payment methods **without modifying existing code**.

---

### 🔹 OrderFactory (Factory Pattern)
Responsible for creating different types of orders.

**Implementations:**
- `NowOrderFactory`
- `ScheduledOrderFactory`

---

### 🔹 Managers (Singleton Pattern)
- `RestaurantManager` – Manages all restaurants  
- `OrderManager` – Manages all orders  

Ensures a **single source of truth**.

---

### 🔹 NotificationService
Sends order summary after successful payment.  
Implemented as a **stateless utility service**.

---

### 🔹 TomatoApp (Facade Pattern)
Acts as a **single entry point** for the entire system.  
Hides internal complexity and exposes simple APIs.

---

## 🔁 End-to-End Flow (Happy Path)

1. User searches restaurants by location  
2. Selects a restaurant  
3. Adds items to cart  
4. Places an order (Now / Scheduled)  
5. Payment processed using selected strategy  
6. Order stored in OrderManager  
7. Notification sent to user  

---

## 🎯 Design Patterns Used

| Pattern | Usage |
|------|------|
| Facade | TomatoApp |
| Factory | OrderFactory |
| Strategy | PaymentStrategy |
| Singleton | Managers |
| Inheritance | Order Types |
| Composition | User → Cart |

---

## 🛠️ Technologies Used

- **Language:** C++  
- **Concepts:** OOP, LLD  
- **Patterns:** Factory, Strategy, Singleton, Facade  

---

## 📌 Learning Outcomes

- Practical Low-Level Design implementation  
- Hands-on experience with design patterns  
- Understanding of scalable system architecture  
- Interview-ready LLD project  

---

## 📈 Future Enhancements

- Use smart pointers (`unique_ptr`, `shared_ptr`)  
- Add database support  
- Add discount & coupon system  
- REST API integration  
- Thread-safe Singleton  

---

## 👨‍💻 Author

**Aditya Raj Singh**  
- B.E. Student  
- Interested in Backend, LLD & System Design  

---

## ⭐ If you like this project

Give it a ⭐ on GitHub and feel free to fork or improve it!




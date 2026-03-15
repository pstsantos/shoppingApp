# 🛒 ShoppingApp

A Java-based shopping cart application built as a mini project for a Software Testing course. The app simulates a purchase flow including item management, tax calculation, shipping logic, and checkout — with comprehensive unit testing.

---

## 📋 Features

- Add items to the shopping cart
- View cart contents
- Edit item quantities
- Remove items from the cart
- Calculate totals with tax and shipping
- Checkout with transaction confirmation

---

## 🧮 Business Logic

### Tax
| State | Tax Rate |
|-------|----------|
| Illinois (IL) | 6% |
| California (CA) | 6% |
| New York (NY) | 6% |
| All other states | 0% |

### Shipping
| Type | Cost |
|------|------|
| STANDARD | $10.00 (free if order > $50) |
| NEXT_DAY | $25.00 (always charged) |

### Validation
- Quantity must be a whole number ≥ 1
- Minimum purchase amount: $1.00
- Maximum purchase amount: $99,999.99

---

## 🗂️ Project Structure

```
src/
├── main/java/com/shop/
│   ├── Item.java           # Product model
│   ├── ShoppingCart.java   # Core business logic
│   ├── State.java          # Enum for tax states
│   ├── ShippingType.java   # Enum for shipping types
│   └── Main.java           # CLI runner
└── test/java/com/shop/
    └── ShoppingCartTest.java  # JUnit 5 test suite
```

---

## 🧪 Testing

### Unit Tests — JUnit 5
29 tests covering:
- Add, remove, edit cart operations
- Tax logic for all states
- Shipping cost calculations (boundary cases included)
- Total calculation and validation
- Checkout flow

### Code Coverage — EclEmma (IntelliJ)
| Class | Method | Line | Branch |
|-------|--------|------|--------|
| Item | 100% | 90% | 100% |
| ShoppingCart | 100% | 97% | 92% |
| ShippingType | 100% | 100% | 100% |
| State | 100% | 100% | 100% |

### Mutation Testing — PiTest
| Class | Line Coverage | Mutation Coverage | Test Strength |
|-------|--------------|-------------------|---------------|
| Item.java | 92% | 83% | **100%** |
| ShoppingCart.java | 96% | 89% | **89%** |

> `Main.java` is intentionally excluded from testing per assignment requirements (no testing of CLI/print functions).

---

## 🚀 How to Run

### Prerequisites
- Java 17
- Maven 3.9+

### Run the app
```bash
mvn compile exec:java -Dexec.mainClass="com.shop.Main"
```

### Run the tests
```bash
mvn test
```

### Run code coverage (EclEmma)
Open `ShoppingCartTest.java` in IntelliJ → Right-click → **Run with Coverage**

### Run mutation testing (PiTest)
```bash
mvn org.pitest:pitest-maven:1.15.0:mutationCoverage -Dpitest.junit5Plugin=1.1.2
```
Then open `target/pit-reports/index.html` in your browser.

---

## 🛠️ Built With

- Java 17
- Maven 3.9
- JUnit 5
- PiTest 1.15.0
- IntelliJ IDEA

---

## 📚 Course

Software Testing — Mini Project  
University course project demonstrating unit testing, code coverage, and mutation testing best practices.

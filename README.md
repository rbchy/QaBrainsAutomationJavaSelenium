# 🚀 QaBrainsAutomationJavaSelenium

A scalable and enterprise-ready Test Automation Framework built using **Selenium WebDriver + Java + Cucumber BDD + TestNG + Maven**.

This framework is designed to automate modern web applications using industry-standard automation architecture and best practices.

---

# 📌 Project Overview

The framework validates critical business workflows including:

* User Authentication
* Product Cart Functionality
* Forgot Password Flow
* Registration
* Smoke Testing
* Regression Testing

The project follows:

* ✅ Page Object Model (POM)
* ✅ Behavior Driven Development (BDD)
* ✅ Reusable Utilities
* ✅ Cross-browser automation
* ✅ Maven build management
* ✅ Cucumber reporting
* ✅ Scalable automation design

---

# 🛠️ Tech Stack

| Technology         | Purpose                     |
| ------------------ | --------------------------- |
| Java               | Programming Language        |
| Selenium WebDriver | Browser Automation          |
| Cucumber BDD       | Behavior Driven Development |
| TestNG             | Test Execution              |
| Maven              | Dependency Management       |
| Git & GitHub       | Version Control             |
| Jenkins            | CI/CD                       |
| Eclipse IDE        | Development Environment     |
| Cucumber Reports   | Reporting                   |

---

# 📂 Project Structure

```bash id="tvh2oa"
QaBrainsAutomation_Final
│
├── src/test/java
│   ├── pages
│   ├── stepdefinitions
│   ├── runners
│   ├── utilities
│   └── hooks
│
├── src/test/resources
│   └── features
│
├── target
│   └── cucumber-reports
│
├── pom.xml
└── README.md
```

---

# ✅ Automated Features

## 🔐 Authentication

* Login
* Logout
* Forgot Password
* Registration

## 🛒 Cart Functionality

* Add product to cart
* Remove product from cart
* Cart validation

## 🧪 Test Suites

* Smoke Tests
* Regression Tests

---

# 🧩 Framework Design

## ✔️ Page Object Model (POM)

The framework separates:

* Page locators
* Actions
* Assertions
* Test data

This improves:

* Maintainability
* Reusability
* Scalability

---

# 🧪 Sample Feature File

```gherkin id="6xk3n2"
Feature: Cart Functionality

Scenario: Add product to cart
Given User launches the application
When User adds products to cart
Then Product should appear in cart
```

---

# ▶️ How to Run the Project

# Prerequisites

Install:

* Java JDK 21+
* Maven
* Eclipse / IntelliJ IDEA
* Chrome Browser
* ChromeDriver

---

# 🔧 Installation Steps

## Clone Repository

```bash id="n1wy1k"
git clone https://github.com/yourusername/QaBrainsAutomation_Final.git
```

## Navigate to Project

```bash id="r1vfrh"
cd QaBrainsAutomation_Final
```

## Install Dependencies

```bash id="e5d8jc"
mvn clean install
```

---

# ▶️ Execute Tests

## Run All Tests

```bash id="awslm2"
mvn test
```

## Run Smoke Tests

```bash id="d8q2i0"
mvn test -Dcucumber.filter.tags="@smoke"
```

## Run Regression Tests

```bash id="29u9l6"
mvn test -Dcucumber.filter.tags="@regression"
```

---

# 📊 Reporting

Cucumber reports are generated automatically after execution.

Report Location:

```bash id="av29za"
target/cucumber-reports.html
```

---

# 📈 Test Execution Summary

```text id="cbm0tk"
13 PASSED
2 FAILED
87% PASSED
15 EXECUTED
```

---

# ❌ Sample Assertion Failure

```text id="ym1x4q"
java.lang.AssertionError:
Product was not found in the cart after adding
expected [true] but found [false]
```

This validates:

* Assertion handling
* Failure reporting
* Negative scenario coverage

---

# 🌐 Cross Browser Testing

Framework supports:

* Chrome
* Firefox
* Edge

Can be extended using:

* Selenium Grid
* Sauce Labs
* BrowserStack

---

# ⚙️ CI/CD Integration

This framework is CI/CD ready and can integrate with:

* Jenkins
* GitHub Actions
* Azure DevOps

Pipeline capabilities:

* Automated test execution
* Scheduled runs
* Report publishing
* Failure notifications

---

# 📸 Framework Features

✔ Screenshot capture on failure
✔ Reusable utility methods
✔ Centralized configuration management
✔ Tag-based execution
✔ Detailed Cucumber reports
✔ Modular architecture
✔ Easy maintenance

---

# 🚀 Future Enhancements

* Playwright Migration
* Docker Integration
* Parallel Execution
* Allure Reporting
* API Automation
* Database Validation
* Cloud Execution
* AI-assisted Testing

---

# 👨‍💻 Author

## Ranajit Baran Chowdhury

Software Programmer & QA Automation Engineer

📧 [chyranajit@gmail.com](mailto:chyranajit@gmail.com)
📱 +1 (267)-342-5565

---

# ⭐ Why This Framework?

✔ Enterprise-ready architecture
✔ Easy to scale
✔ Industry-standard design patterns
✔ Reusable automation components
✔ BDD readable test cases
✔ CI/CD compatible

---

# 📬 Connect

Feel free to:

* Fork the repository
* Raise issues
* Contribute enhancements
* Share feedback

---

# 📄 License

This project is licensed under the MIT License.
# QaBrainsAutomation

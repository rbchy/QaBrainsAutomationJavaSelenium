<div align="center">

# 🧪 QA Brains Automation — Java + Selenium

### Cucumber BDD UI suite for the QA Brains practice site — login, registration, password reset, e-commerce cart

[![Typing SVG](https://readme-typing-svg.demolab.com/?font=Fira+Code&size=18&pause=1500&color=FFC107&center=true&vCenter=true&width=900&repeat=true&lines=Java+17+%C2%B7+Selenium+4+%C2%B7+Cucumber+7+%C2%B7+TestNG+%C2%B7+Maven;Login+%C2%B7+Registration+%C2%B7+Forgot+Password+%C2%B7+Cart+%C2%B7+Navigation;15+%2F+15+scenarios+passing+in+GitHub+Actions)](https://git.io/typing-svg)

<!-- ============ STATUS BAR ============ -->
[![Tests](https://github.com/rbchy/QaBrainsAutomationJavaSelenium/actions/workflows/tests.yml/badge.svg)](https://github.com/rbchy/QaBrainsAutomationJavaSelenium/actions/workflows/tests.yml)
![Pass Rate](https://img.shields.io/badge/Pass%20Rate-100%25%20(15%2F15)-22c55e?style=for-the-badge&logo=checkmarx&logoColor=white)
![Target](https://img.shields.io/badge/Target-practice.qabrains.com-1e3a8a?style=for-the-badge&logo=googlechrome&logoColor=white)

![Java](https://img.shields.io/badge/Java-17-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Selenium](https://img.shields.io/badge/Selenium-4.25-43B02A?style=for-the-badge&logo=selenium&logoColor=white)
![Cucumber](https://img.shields.io/badge/Cucumber-7.15-23D96C?style=for-the-badge&logo=cucumber&logoColor=white)
![TestNG](https://img.shields.io/badge/TestNG-7.9-FF7F00?style=for-the-badge)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white)

![Last Commit](https://img.shields.io/github/last-commit/rbchy/QaBrainsAutomationJavaSelenium?style=flat-square&color=0d9488&label=Last%20commit)
![Repo Size](https://img.shields.io/github/repo-size/rbchy/QaBrainsAutomationJavaSelenium?style=flat-square&color=155e75&label=Repo%20size)

</div>

---

## 📌 At a Glance

<table>
<tr>
<td width="50%" valign="top">

**🙋 What this is**

A Selenium + Cucumber suite for the **[QA Brains practice site](https://practice.qabrains.com/)**: user authentication (login, logout, registration, forgot password), the **e-commerce demo** (shop login, add / remove to cart, product details, product cards) and the sidebar demo modules. Scenarios are plain-English Gherkin, backed by **Page Objects** and run by **TestNG** through Maven.

Every push runs the whole suite in **GitHub Actions** with headless Chrome.

> *A test that doesn't fail when it should is worse than no test at all.*

</td>
<td width="50%" valign="top">

**📍 Quick facts**

| | |
|---|---|
| 🧪 **Scenarios** | 15 in 7 feature files |
| ✅ **CI** | 15 / 15 · headless Chrome · ≈ 4 min |
| 🏷️ **Tags** | `@smoke` · `@regression` · `@Cart` · `@Shop` … |
| 📸 **On failure** | Screenshot + page HTML in the report |
| ⚙️ **Config** | `src/test/resources/config.properties` |

</td>
</tr>
</table>

---

## ✅ Latest Results

| Feature file | Scenarios | Result |
|---|---:|---|
| 🔐 `Login.feature` | 2 | ![passed](https://img.shields.io/badge/-2%20passed-22c55e?style=flat-square) |
| 🚪 `Logout.feature` | 1 | ![passed](https://img.shields.io/badge/-1%20passed-22c55e?style=flat-square) |
| 📝 `Registration.feature` | 2 | ![passed](https://img.shields.io/badge/-2%20passed-22c55e?style=flat-square) |
| 🔑 `ForgotPassword.feature` | 2 | ![passed](https://img.shields.io/badge/-2%20passed-22c55e?style=flat-square) |
| 🛒 `CartCheckout.feature` | 2 | ![passed](https://img.shields.io/badge/-2%20passed-22c55e?style=flat-square) |
| 🔄 `RegressionTests.feature` | 3 | ![passed](https://img.shields.io/badge/-3%20passed-22c55e?style=flat-square) |
| 💨 `SmokeTests.feature` | 3 | ![passed](https://img.shields.io/badge/-3%20passed-22c55e?style=flat-square) |
| **Total** | **15** | **100 %** |

<sub>GitHub Actions, Ubuntu, Temurin 17, headless Chrome ([workflow](.github/workflows/tests.yml)). The earlier local run in [QaBrainAutomationSeleniumCucumber.pdf](QaBrainAutomationSeleniumCucumber.pdf) shows 13 / 15 — its two cart failures are what the maintenance log below fixed.</sub>

---

## 🎯 Test Coverage

<details open>
<summary><strong>🔐 Authentication</strong></summary>

<br>

| Feature | Scenarios |
|---|---|
| Login | Valid credentials · invalid credentials show *"Your email and password both are invalid!"* |
| Logout | A logged-in user logs out and the login form returns |
| Registration | Register with a valid e-mail · the browser rejects an e-mail without `@` |
| Forgot Password | Reset for a registered e-mail · a malformed e-mail is rejected (*"missing an '@'"*) |

</details>

<details>
<summary><strong>🛒 E-commerce demo</strong></summary>

<br>

All shop scenarios first log in at `/ecommerce/login` with the public practice account.

| Scenario | Check |
|---|---|
| Add product to cart | The product's button turns into *Remove from cart* |
| Remove product from cart | Nothing is left marked *Remove from cart* |
| R-01 Add multiple products | 3 added → 3 in the cart |
| R-02 Product details | Details page shows the product name and price |
| R-03 Product cards | Every card has a name, a price and an *Add to cart* button |

</details>

<details>
<summary><strong>💨 Smoke</strong></summary>

<br>

| Scenario | Check |
|---|---|
| S-01 | Home page loads |
| S-02 | Registration, Forgot Password, Form Submission and Drag and Drop List open from the sidebar |
| S-03 | The E-Commerce demo site opens from the menu |

</details>

---

## 🏗️ Framework Architecture

```mermaid
flowchart LR
  F["Feature files<br/>(Gherkin)"] --> S["Step definitions<br/>stepdefinitions/"]
  S --> P["Page Objects<br/>pages/"]
  P --> W["Selenium WebDriver<br/>+ WebDriverManager"]
  W --> C["Chrome<br/>(headless in CI)"]
  C --> Q["practice.qabrains.com"]
  H["Hooks<br/>@Before / @After"] -.->|"fresh browser ·<br/>screenshot + HTML on failure"| W
  CF["config.properties"] -.-> S
  R["TestRunner<br/>@smoke or @regression"] --> F
```

- **Page Object Model** — `LoginPage`, `LogoutPage`, `RegistrationPage`, `ForgotPasswordPage`, `EcommercePage`
- **Explicit waits everywhere** — the shop waits for each cart click to change the product's state
- **Robust navigation** — the menu's element ids are generated on every load, so pages open by URL or visible label, never by those ids
- **Failure evidence** — screenshot and page HTML attached to the report and saved under `target/failures/`
- **Config, not code** — URL and the public practice accounts live in `config.properties`

---

## 🛠️ Tech Stack

| Layer | Technology | Version |
|---|---|---|
| Language | Java | 17 |
| Browser automation | Selenium WebDriver | 4.25.0 |
| Driver management | WebDriverManager | 5.7.0 |
| BDD | Cucumber JVM (Gherkin) | 7.15.0 |
| Runner | TestNG (`cucumber-testng`) | 7.9.0 |
| Build | Maven (Surefire 3.2.5) | — |
| Reporting | Cucumber HTML / JSON / JUnit XML | — |
| CI | GitHub Actions | — |

---

## 📁 Project Structure

```
QaBrainsAutomationJavaSelenium/
├── .github/workflows/tests.yml        ← headless run on every push
├── src/test/java/
│   ├── pages/                         ← Login, Logout, Registration, ForgotPassword, Ecommerce
│   ├── stepdefinitions/
│   │   ├── Hooks.java                 ← browser per scenario, failure evidence
│   │   ├── CommonSteps.java · AuthSteps.java
│   │   ├── RegistrationSteps.java · ForgotPasswordSteps.java
│   │   └── ShopSteps.java             ← cart, product details, menu navigation
│   ├── runners/TestRunner.java        ← @smoke or @regression
│   └── utils/
│       ├── BaseTest.java              ← config, Chrome options, headless switch
│       ├── DriverFactory.java         ← ThreadLocal driver, ready for parallel runs
│       └── DriverHelper.java
├── src/test/resources/
│   ├── config.properties
│   └── features/                      ← 7 feature files, 15 scenarios
├── QaBrainAutomationSeleniumCucumber.pdf
└── pom.xml
```

---

## ⚙️ Getting Started

**Prerequisites:** JDK 17+ · Maven 3.8+ · Google Chrome (WebDriverManager fetches the driver)

```bash
git clone https://github.com/rbchy/QaBrainsAutomationJavaSelenium.git
cd QaBrainsAutomationJavaSelenium

mvn clean test                                        # all @smoke or @regression scenarios
mvn clean test -Dheadless=true                        # what CI runs
mvn clean test -Dcucumber.filter.tags="@Cart"         # one area
```

From the IDE: right-click `runners/TestRunner.java` → **Run As › TestNG Test**.

| Report | Location |
|---|---|
| Cucumber HTML | `target/cucumber-reports.html` |
| JSON · JUnit XML | `target/cucumber-reports/` |
| Failure screenshots + page HTML | `target/failures/` and inside the HTML report |

---

## 🧹 Maintenance Log

| Change | Why |
|---|---|
| Cart scenarios rewritten for the site's real e-commerce demo | The old locators (`.add-to-cart`, `.cart-item`) came from a different shop — the 2 failures in the PDF |
| Smoke and regression steps now assert real behaviour | Several only printed text (e.g. *"Pages navigated correctly"*) and could never fail |
| Search, Catalog, Wishlist, Refer-a-Friend scenarios replaced | The practice site has none of these pages |
| Registration opens by URL | The menu's ids (`rc-menu-uuid-…`) change on every page load |
| Forgot Password no longer has its own `@Before` / `@After` | It quit the browser a second time after every scenario |
| Credentials from `config.properties`; another person's e-mail replaced in the feature files | No data in code; no third-party address in the tests |
| Headless switch and GitHub Actions | Every push is checked |
| Eclipse files and `.DS_Store` removed, ignored | IDE- and machine-specific |

---

## 📈 Roadmap

- [x] All scenarios assert real behaviour of the practice site
- [x] GitHub Actions with headless Chrome
- [ ] Form Submission and Drag and Drop scenarios
- [ ] Firefox and Edge in a CI browser matrix
- [ ] Parallel scenarios through the `ThreadLocal` `DriverFactory`
- [ ] Allure report published to GitHub Pages

---

## 🔗 Related Projects

| Project | Stack |
|---|---|
| 🔌 [API — Rest Assured](https://github.com/rbchy/QaBrainsAPIAutomationRestAssured) | Same site's UI plus a Rest Assured API pack — CI green |
| 🔬 [QA Brains — Java + Playwright](https://github.com/rbchy/QaBrainsAutomationJavaPlaywright) | Java 17 · Playwright · Cucumber JVM · TestNG |
| 🔌 [API — Postman / Newman](https://github.com/rbchy/QaBrainsAPIAutomation_Postman) | Postman · Newman — CI green |
| ⭐ [RbcTcsWorld E-Commerce Suite](https://github.com/rbchy/RbcTcsWorld_ECommerceSuite) | Spring Boot · REST Assured · Selenium · Playwright · CI quality gates |

<sub>All projects: [github.com/rbchy](https://github.com/rbchy)</sub>

---

## 👤 Author

<div align="center">

**Ranajit Baran Chowdhury (RB Chowdhury)**
QA Automation Engineer / SDET · West Norriton, Pennsylvania, USA

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rbchy/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/rbchy)
[![Website](https://img.shields.io/badge/Website-rbchy.github.io%2Frbchy-0d9488?style=for-the-badge&logo=githubpages&logoColor=white)](https://rbchy.github.io/rbchy/)
[![Portfolio](https://img.shields.io/badge/Portfolio-Website-blueviolet?style=for-the-badge&logo=wix&logoColor=white)](https://rbc6543.wixsite.com/rbc-portfolio)
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:chyranajit@gmail.com)

<sub>Licensed under MIT. QA Brains is a public practice site; only its published practice accounts are used.</sub>

⭐ *If this framework helps you, a star on the repo is appreciated.*

</div>

# STA
# Software Testing Practicals

---

# SET A

### 1. Test plan for an e-commerce application

**Aim:** To develop the test plan for testing an e-commerce web/mobile application (www.amazon.in).

**Algorithm:**
1. Identify the scope of testing (e.g., Login, Search, Cart, Checkout).
2. Determine the testing strategy (Manual, Automation, Performance).
3. Identify hardware, software, and tools required (Test Environment).
4. Outline the schedule and resource allocation.
5. Define entry and exit criteria for the testing phases.

**Implementation (Test Plan Structure):**
- **Test Objective:** Ensure all functional flows of amazon.in work seamlessly.
- **In-Scope:** User Registration, Product Search, Add to Cart, Payment Gateway.
- **Out-of-Scope:** Third-party seller portal backend.
- **Test Environment:** Windows 11, Chrome Browser, Android OS (for mobile).
- **Deliverables:** Test Plan, Test Cases, Defect Report.

**Output:**
```
The test plan document for the e-commerce application was successfully developed.
```

---

### 2. Test cases for an e-commerce application

**Aim:** To design the test cases for testing the e-commerce application.

**Algorithm:**
1. Analyze the functional requirements of the application.
2. Identify positive and negative test scenarios.
3. Define the pre-conditions, steps to execute, expected results, and actual results.

**Implementation (Test Cases):**

| Test Case ID | Test Scenario | Steps to Execute | Expected Result |
| :--- | :--- | :--- | :--- |
| TC_01 | Validate Search | 1. Open app 2. Enter "Laptop" in search 3. Click Search | Relevant laptops should be displayed. |
| TC_02 | Add to Cart | 1. Select a product 2. Click "Add to Cart" | Cart counter should increase by 1. |
| TC_03 | Invalid Login | 1. Enter wrong password 2. Click Login | Display "Incorrect password" error. |

**Output:**
```
Functional test cases for the e-commerce application were designed successfully.
```

---

### 3. Test and report defects for e-commerce application

**Aim:** To test the e-commerce application and report the defects in it.

**Algorithm:**
1. Execute the previously designed test cases.
2. Compare the Actual Result with the Expected Result.
3. If a mismatch is found, log it as a defect.
4. Assign severity and priority to the defect.

**Implementation (Defect Report):**

| Defect ID | Description | Steps to Reproduce | Severity | Status |
| :--- | :--- | :--- | :--- | :--- |
| BUG_001 | Cart total does not update after removing item | 1. Add 2 items. 2. Remove 1 item. 3. Check total amount. | High | Open |
| BUG_002 | Search icon overlaps with user profile | 1. Open app on mobile view. 2. Look at top right header. | Low | Open |

**Output:**
```
The application was tested, and defects were successfully logged in the defect tracking report.
```

---

### 4. Test plan and test cases for an inventory control system

**Aim:** To develop the test plan and design the test cases for an inventory control system.

**Algorithm:**
1. Define the scope: Adding stock, removing stock, low stock alerts.
2. Create test cases covering stock boundary values.
3. Validate database updates when transactions occur.

**Implementation (Test Cases):**

| Test Case ID | Scenario | Steps | Expected Result |
| :--- | :--- | :--- | :--- |
| INV_01 | Add new inventory | Enter Item ID, Name, Qty -> Click Save | Item saved in the database. |
| INV_02 | Low stock alert | Reduce item quantity below 5 | System triggers a "Low Stock" warning. |

**Output:**
```
Test plan and test cases for the inventory system were successfully generated.
```

---

### 5. Execute test cases against a desktop application

**Aim:** To execute the test cases against a client server or desktop application and identify the defects.

**Algorithm:**
1. Launch the target desktop application (e.g., Windows Calculator).
2. Perform standard operations based on test cases.
3. Test edge cases (e.g., divide by zero).
4. Record any crashes or unexpected outputs.

**Implementation (Execution Log):**
- **Test:** Division by Zero.
- **Steps:** Open Calculator -> Press '5' -> Press '/' -> Press '0' -> Press '='.
- **Expected:** Display "Cannot divide by zero".
- **Actual:** Application crashes (Hypothetical defect).
- **Defect Logged:** Yes.

**Output:**
```
Test cases executed against the desktop application, and defects were identified and reported.
```

---

### 6. Selenium automation framework using Page Object Model (POM)

**Aim:** To design and implement a test automation framework using Selenium (Page Object Model).

**Algorithm:**
1. Create a LoginPage class containing web element locators and action methods.
2. Create a TestExecution class.
3. Instantiate the LoginPage class inside the test script and pass the test data.

**Program (Python):**
```python
# login_page.py (Page Object)
from selenium.webdriver.common.by import By

class LoginPage:
    def __init__(self, driver):
        self.driver = driver
        self.username_box = (By.ID, "user")
        self.password_box = (By.ID, "pass")
        self.login_btn = (By.ID, "loginBtn")

    def login(self, username, password):
        self.driver.find_element(*self.username_box).send_keys(username)
        self.driver.find_element(*self.password_box).send_keys(password)
        self.driver.find_element(*self.login_btn).click()

# test_script.py (Execution)
from selenium import webdriver
from login_page import LoginPage

driver = webdriver.Chrome()
driver.get("http://example.com/login")
page = LoginPage(driver)
page.login("testuser", "testpass")
print("POM Test Executed Successfully")
driver.quit()
```

**Output:**
```
The Page Object Model framework was successfully implemented and the test script ran without errors.
```

---

### 7. Perform testing on e-commerce (Login, Add to Cart, Checkout)

**Aim:** To perform testing on an e-commerce website including login, add to cart, and checkout process.

**Algorithm:**
1. Initialize the WebDriver and navigate to the application.
2. Locate the login fields and authenticate.
3. Locate a product and click "Add to Cart".
4. Navigate to the cart and click "Checkout".

**Program (Python):**
```python
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Chrome()
driver.implicitly_wait(10)
driver.get("https://www.saucedemo.com/")

# Login
driver.find_element(By.ID, "user-name").send_keys("standard_user")
driver.find_element(By.ID, "password").send_keys("secret_sauce")
driver.find_element(By.ID, "login-button").click()

# Add to Cart
driver.find_element(By.ID, "add-to-cart-sauce-labs-backpack").click()

# Checkout Process
driver.find_element(By.CLASS_NAME, "shopping_cart_link").click()
driver.find_element(By.ID, "checkout").click()

print("Login, Add to Cart, and Checkout steps passed.")
driver.quit()
```

**Output:**
```
The end-to-end flow from login to checkout was automated and executed successfully.
```

---

### 8. State Transition Testing for an online order system

**Aim:** To create test cases using State Transition Testing for an online order system.

**Algorithm:**
1. Identify the states of an order (e.g., Pending -> Confirmed -> Shipped -> Delivered).
2. Identify the events that trigger transitions (e.g., Payment Success, Dispatch).
3. Create a state transition table mapping current states to next states.

**Implementation (State Transition Table):**

| Current State | Event | Next State | Expected Result |
| :--- | :--- | :--- | :--- |
| Pending | Payment Successful | Confirmed | Order moves to processing |
| Pending | Payment Failed | Cancelled | Order is aborted |
| Confirmed | Item Dispatched | Shipped | Tracking ID generated |
| Shipped | Item Reaches Customer | Delivered | Order closed successfully |

**Output:**
```
State transition test cases were created covering all valid states of the order lifecycle.
```

---

### 9. Open a browser and navigate to a URL

**Aim:** To write Selenium code to open a browser and navigate to a URL.

**Algorithm:**
1. Import the webdriver package from Selenium.
2. Initialize the Chrome WebDriver.
3. Use the `.get()` method to navigate to the target URL.
4. Print the page title and close the browser using `.quit()`.

**Program (Python):**
```python
from selenium import webdriver

# Initialize Chrome driver
driver = webdriver.Chrome()

# Navigate to URL
driver.get("https://www.google.com")

# Print the title to verify
print("Page Title is:", driver.title)

# Close the browser
driver.quit()
```

**Output:**
```
Page Title is: Google
```

---

### 10. Continuous testing using Jenkins integration

**Aim:** To perform continuous testing using Jenkins integration.

**Algorithm:**
1. Start the Jenkins server and open the Jenkins dashboard (usually `localhost:8080`).
2. Click on "New Item" and create a "Freestyle project".
3. Under "Build Management", navigate to "Build Steps".
4. Select "Execute Windows batch command" (or shell for Linux/Mac).
5. Enter the command to run the test script (e.g., `python test_script.py` or `pytest`).
6. Save and click "Build Now".

**Implementation (Jenkins Configuration):**
- **Job Name:** E-Commerce_Nightly_Build
- **Source Code Management:** Git (Provide repository URL)
- **Build Step (Execute Shell):**
```bash
pip install -r requirements.txt
pytest test_ecommerce.py --junitxml=reports/result.xml
```
- **Post-build Actions:** Publish JUnit test result report.

**Output:**
```
The code was integrated into Jenkins, the build was triggered successfully,
and the test results were logged in the Jenkins console output.
```

---

# SET B

### 1. Test the performance of the e-commerce application

**Aim:** To test the performance (page load time) of an e-commerce application using Selenium WebDriver.

**Algorithm:**
1. Configure and initialize the Selenium WebDriver.
2. Record the system time before triggering the website URL.
3. Navigate to the e-commerce application.
4. Wait for the page to fully load and record the system time again.
5. Calculate the difference to determine the page load time in milliseconds.
6. Close the browser.

**Program (Java):**
```java
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class PerformanceTest {
    public static void main(String[] args) {
        System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");
        WebDriver driver = new ChromeDriver();

        long startTime = System.currentTimeMillis();
        driver.get("https://www.amazon.com");
        long endTime = System.currentTimeMillis();

        long loadTime = endTime - startTime;
        System.out.println("E-commerce Page Load Time: " + loadTime + " milliseconds");

        if (loadTime < 3000) {
            System.out.println("Performance Status: PASS");
        } else {
            System.out.println("Performance Status: FAIL (Too slow)");
        }
        driver.quit();
    }
}
```

**Output:**
```
E-commerce Page Load Time: 2150 milliseconds
Performance Status: PASS
```

---

### 2. Automate the testing of e-commerce applications using Selenium

**Aim:** To automate a product search functionality on an e-commerce application using Selenium WebDriver.

**Algorithm:**
1. Initialize WebDriver and navigate to the e-commerce site.
2. Locate the search box using its ID or Name attribute.
3. Send the search term (e.g., "Laptop") to the search box.
4. Locate and click the search button.
5. Verify if the resulting page title contains the search term.
6. Close the browser.

**Program (Java):**
```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class EcommerceTest {
    public static void main(String[] args) {
        System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");
        WebDriver driver = new ChromeDriver();

        driver.get("https://demo.opencart.com/");

        // Find search box and enter product
        driver.findElement(By.name("search")).sendKeys("MacBook");

        // Click search button
        driver.findElement(By.cssSelector("button.btn.btn-light.btn-lg")).click();

        String title = driver.getTitle();
        if(title.contains("Search")) {
            System.out.println("Product search automated successfully.");
        } else {
            System.out.println("Search failed.");
        }
        driver.quit();
    }
}
```

**Output:**
```
Product search automated successfully.
```

---

### 3. Integrate TestNG with the above test automation

**Aim:** To integrate TestNG testing framework with the Selenium e-commerce automation script.

**Algorithm:**
1. Create a TestNG class.
2. Use the `@BeforeMethod` annotation to initialize the WebDriver.
3. Use the `@Test` annotation to define the search functionality test.
4. Use the `@AfterMethod` annotation to close the browser.
5. Use TestNG Assert to validate the test outcome.

**Program (Java):**
```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;
import org.testng.annotations.*;

public class TestNGEcommerce {
    WebDriver driver;

    @BeforeMethod
    public void setup() {
        System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");
        driver = new ChromeDriver();
    }

    @Test
    public void testProductSearch() {
        driver.get("https://demo.opencart.com/");
        driver.findElement(By.name("search")).sendKeys("MacBook");
        driver.findElement(By.cssSelector("button.btn.btn-light.btn-lg")).click();

        String title = driver.getTitle();
        Assert.assertTrue(title.contains("Search"), "Search page did not load");
        System.out.println("TestNG Assertion Passed.");
    }

    @AfterMethod
    public void teardown() {
        driver.quit();
    }
}
```

**Output:**
```
TestNG Assertion Passed.
PASSED: testProductSearch
```

---

### 4. Execute the test cases against a desktop application and identify defects

**Aim:** To automate a simple test against a desktop application (Notepad) using Java Robot class to type text and identify defects.

**Algorithm:**
1. Use `Runtime.getRuntime().exec()` to open Notepad.
2. Instantiate the Robot class to simulate keyboard actions.
3. Simulate typing a string (e.g., "HI").
4. Wait for actions to complete.
5. Close the application.

**Program (Java):**
```java
import java.awt.Robot;
import java.awt.event.KeyEvent;

public class DesktopAppTest {
    public static void main(String[] args) {
        try {
            // Open Notepad (Windows)
            Runtime.getRuntime().exec("notepad.exe");
            Thread.sleep(2000); // Wait for Notepad to open

            Robot robot = new Robot();

            // Type "HI"
            robot.keyPress(KeyEvent.VK_H);
            robot.keyRelease(KeyEvent.VK_H);
            robot.keyPress(KeyEvent.VK_I);
            robot.keyRelease(KeyEvent.VK_I);

            System.out.println("Successfully typed into Desktop Application.");

            // Defect Identification Note: If Notepad didn't open or keys didn't type,
            // an exception would be thrown acting as our defect trigger.

        } catch (Exception e) {
            System.out.println("Defect Identified: " + e.getMessage());
        }
    }
}
```

**Output:**
```
Successfully typed into Desktop Application.
(Notepad opens on screen and types "HI")
```

---

### 5. Develop the test plan and design the test cases for an inventory control system

**Aim:** To develop a formal test plan and design test cases for an Inventory Control System.

**Algorithm (Process):**
1. Define the scope and objective of the Test Plan.
2. Identify the features to be tested (e.g., Add Inventory, Update Stock).
3. Draft positive and negative test cases.
4. Define expected results for each test case.

**Documentation:**

**Test Plan:**
- **Objective:** To verify the functional integrity of the Inventory Control System.
- **Scope:** Login module, Add Product module, Stock Deduction module.
- **Environment:** Windows 10, Chrome Browser, QA Database.

**Test Cases:**
- *TC01 (Positive):* Login with valid Admin credentials. Expected: Redirected to Dashboard.
- *TC02 (Positive):* Add new item with valid details (Name, Quantity=50, Price). Expected: Item added to database, success message displayed.
- *TC03 (Negative):* Enter negative quantity for a new item. Expected: System throws "Invalid Quantity" error.

**Output:**
```
Test Plan and Test Cases documented and approved.
```

---

### 6. Perform basic security testing such as SQL injection simulation

**Aim:** To simulate an SQL injection attack to test the security of a login form.

**Algorithm:**
1. Target a mock login URL.
2. Define a malicious payload using a common SQL injection string (`' OR 1=1 --`).
3. Send an HTTP POST request with the payload in the username/password fields.
4. Analyze the server response to check if authentication was bypassed.

**Program (Python):**
```python
import requests

def test_sql_injection():
    # Mock URL - replace with local test server
    url = "http://localhost/vulnerable_app/login.php"

    # SQL Injection payload that makes the query evaluate to true
    payload = {
        "username": "admin' OR 1=1 --",
        "password": "randompassword"
    }

    try:
        response = requests.post(url, data=payload)

        # Check if the response contains keywords of a successful login
        if "Welcome" in response.text or "Dashboard" in response.text:
            print("Security Defect: Vulnerable to SQL Injection!")
        else:
            print("Secure: SQL Injection attempt failed.")
    except Exception as e:
        print("Test environment not reachable: ", e)

test_sql_injection()
```

**Output:**
```
Security Defect: Vulnerable to SQL Injection!
```

---

### 7. Build a complete testing workflow

**Aim:** To build a complete testing workflow including test plan, test cases, execution, and defect report for a User Registration feature.

**Algorithm (Workflow Steps):**
1. **Planning:** Create Test Plan identifying resources, schedule, and scope.
2. **Design:** Write specific Test Cases based on requirements.
3. **Execution:** Run the Test Cases against the application build.
4. **Defect Reporting:** Log any deviations from expected results.

**Documentation Artifacts:**

1. **Test Plan:** Focus on User Registration form validation.
2. **Test Case (TC_Reg_01):** Enter existing email ID during registration. Expected: Show "Email already exists" error.
3. **Execution:** Tester runs TC_Reg_01. The system accepts the duplicate email and creates a second account.
4. **Defect Report (Bug_001):**
   - **Title:** System accepts duplicate email addresses.
   - **Severity:** High
   - **Steps to reproduce:** Go to Registration -> Enter test@test.com (already exists) -> Click Submit.
   - **Actual Result:** Account created.
   - **Expected Result:** Error message should appear.

**Output:**
```
Workflow Complete: Defect Bug_001 logged to tracking system.
```

---

### 8. Integrate Selenium tests with TestNG and generate reports

**Aim:** To generate an HTML test report by integrating Selenium WebDriver, TestNG, and ExtentReports.

**Algorithm:**
1. Initialize ExtentReports and ExtentSparkReporter.
2. Set up WebDriver in `@BeforeTest`.
3. Create a TestNG `@Test` method to perform a Selenium action and log pass/fail status to the report.
4. Flush the report to an HTML file in `@AfterTest`.

**Program (Java):**
```java
import com.aventstack.extentreports.*;
import com.aventstack.extentreports.reporter.ExtentSparkReporter;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;
import org.testng.annotations.*;

public class ReportGenerationTest {
    WebDriver driver;
    ExtentReports extent;
    ExtentTest test;

    @BeforeTest
    public void setup() {
        ExtentSparkReporter spark = new ExtentSparkReporter("TestReport.html");
        extent = new ExtentReports();
        extent.attachReporter(spark);

        System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");
        driver = new ChromeDriver();
    }

    @Test
    public void titleTest() {
        test = extent.createTest("Validate Page Title");
        driver.get("https://www.google.com");

        if(driver.getTitle().equals("Google")) {
            test.pass("Title matched expected result.");
        } else {
            test.fail("Title mismatch.");
            Assert.fail();
        }
    }

    @AfterTest
    public void teardown() {
        driver.quit();
        extent.flush(); // Generates the HTML report
        System.out.println("Report generated at TestReport.html");
    }
}
```

**Output:**
```
PASSED: titleTest
Report generated at TestReport.html
```

---

### 9. Write a program to demonstrate unit testing using JUnit for a simple calculator

**Aim:** To demonstrate unit testing of a simple Calculator application using JUnit.

**Algorithm:**
1. Create a Calculator class containing add and subtract methods.
2. Create a JUnit test class.
3. Write test methods annotated with `@Test`.
4. Use `assertEquals` to verify that the method output matches the expected mathematical result.

**Program (Java):**
```java
import org.junit.Test;
import static org.junit.Assert.assertEquals;

// 1. Target Application Code
class Calculator {
    public int add(int a, int b) { return a + b; }
    public int subtract(int a, int b) { return a - b; }
}

// 2. JUnit Test Code
public class CalculatorTest {
    Calculator calc = new Calculator();

    @Test
    public void testAddition() {
        int result = calc.add(10, 20);
        assertEquals(30, result);
        System.out.println("Addition Test Passed");
    }

    @Test
    public void testSubtraction() {
        int result = calc.subtract(50, 20);
        assertEquals(30, result);
        System.out.println("Subtraction Test Passed");
    }
}
```

**Output:**
```
Addition Test Passed
Subtraction Test Passed
Tests run: 2, Failures: 0
```

---

### 10. Automate login functionality using Selenium WebDriver

**Aim:** To automate the login functionality of a web application using Selenium WebDriver.

**Algorithm:**
1. Initialize the WebDriver.
2. Navigate to the login page URL.
3. Locate the username field and enter valid credentials.
4. Locate the password field and enter a valid password.
5. Click the Login/Submit button.
6. Verify successful login by checking the URL or the presence of a logout button.

**Program (Java):**
```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class LoginAutomation {
    public static void main(String[] args) {
        System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");
        WebDriver driver = new ChromeDriver();

        driver.get("https://practicetestautomation.com/practice-test-login/");

        // Enter Username
        driver.findElement(By.id("username")).sendKeys("student");

        // Enter Password
        driver.findElement(By.id("password")).sendKeys("Password123");

        // Click Submit
        driver.findElement(By.id("submit")).click();

        // Verification
        String currentUrl = driver.getCurrentUrl();
        if (currentUrl.contains("logged-in-successfully")) {
            System.out.println("Login Automation Test Passed!");
        } else {
            System.out.println("Login Automation Test Failed!");
        }

        driver.quit();
    }
}
```

**Output:**
```
Login Automation Test Passed!
```

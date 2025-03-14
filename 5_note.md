Here is an educational blog based on the images you provided. It includes explanations of various Selenium WebDriver commands with sample code and explanations.

---

# **Selenium WebDriver Commands: A Comprehensive Guide**

Selenium WebDriver is a powerful tool for automating web application testing. It allows developers and testers to interact with web elements, navigate through pages, and validate functionalities. In this blog, we will cover different types of Selenium commands categorized into **application commands, conditional commands, browser commands, navigational commands, and wait commands**.

---

## **1. Application Commands in Selenium**

Application commands help in retrieving details about the current webpage.

### **Common Application Commands**
| Command        | Description |
|---------------|------------|
| `get(url)`   | Opens the specified URL in the browser. |
| `title`       | Captures the title of the current webpage. |
| `current_url` | Retrieves the URL of the current page. |
| `page_source` | Retrieves the HTML source code of the page. |

### **Example Code**
```python
from selenium import webdriver

# Launch Chrome Browser
driver = webdriver.Chrome()

# Open a website
driver.get("https://www.google.com")

# Get title of the page
print("Page Title:", driver.title)

# Get current URL
print("Current URL:", driver.current_url)

# Get page source (HTML)
print("Page Source:", driver.page_source)

# Close the browser
driver.quit()
```

---

## **2. Conditional Commands in Selenium**
Conditional commands help in verifying the state of elements on a webpage, such as whether an element is displayed, enabled, or selected.

### **Common Conditional Commands**
| Command         | Description |
|----------------|------------|
| `is_displayed()` | Checks if an element is visible on the webpage. |
| `is_enabled()` | Checks if an input field or button is enabled for interaction. |
| `is_selected()` | Checks if a radio button or checkbox is selected. |

### **Example Code**
```python
from selenium import webdriver
from selenium.webdriver.common.by import By

# Initialize WebDriver
driver = webdriver.Chrome()

# Open webpage
driver.get("https://example.com")

# Find an input field
input_field = driver.find_element(By.ID, "username")

# Check if input field is displayed and enabled
print("Is displayed:", input_field.is_displayed())
print("Is enabled:", input_field.is_enabled())

# Find a radio button
radio_button = driver.find_element(By.ID, "gender-male")

# Check if it is selected
print("Is selected:", radio_button.is_selected())

# Close browser
driver.quit()
```

---

## **3. Browser Commands in Selenium**
Browser commands allow testers to manage browser windows.

### **Common Browser Commands**
| Command        | Description |
|---------------|------------|
| `close()`     | Closes the current browser window. |
| `quit()`      | Closes all browser windows and ends the session. |

### **Example Code**
```python
from selenium import webdriver

# Initialize WebDriver
driver = webdriver.Chrome()

# Open a webpage
driver.get("https://www.google.com")

# Close only the current window
driver.close()

# Quit the browser session
driver.quit()
```

---

## **4. Navigational Commands in Selenium**
Navigational commands allow users to navigate between webpages.

### **Common Navigational Commands**
| Command      | Description |
|-------------|------------|
| `back()`     | Navigates to the previous page in the browser history. |
| `forward()`  | Navigates to the next page in the browser history. |
| `refresh()`  | Refreshes the current webpage. |

### **Example Code**
```python
from selenium import webdriver
from selenium.webdriver.chrome.service import Service

# Initialize WebDriver
service_obj = Service("C:\\Drivers\\chromedriver_win32\\chromedriver.exe")
driver = webdriver.Chrome(service=service_obj)

# Open webpages
driver.get("https://www.snapdeal.com")
driver.get("https://www.amazon.com")

# Navigate back to Snapdeal
driver.back()

# Navigate forward to Amazon
driver.forward()

# Refresh the page
driver.refresh()

# Quit browser
driver.quit()
```

---

## **5. Text vs get_attribute('value')**
When dealing with text input fields, we use `.text` or `.get_attribute('value')` to retrieve the text inside the element.

| Command                   | Description |
|---------------------------|------------|
| `element.text`            | Retrieves the visible text of an element. |
| `element.get_attribute('value')` | Retrieves the value attribute of an input field. |

### **Example Code**
```python
from selenium import webdriver
from selenium.webdriver.common.by import By

# Initialize WebDriver
driver = webdriver.Chrome()

# Open a website with a form
driver.get("https://example.com/login")

# Locate input field
input_field = driver.find_element(By.ID, "email")

# Retrieve text inside the input field
print("Inner text:", input_field.text)
print("Input value:", input_field.get_attribute("value"))

# Close browser
driver.quit()
```

---

## **6. Handling Radio Buttons Using is_selected()**
Radio buttons are a common form element, and we often need to check or select them.

### **Example Code**
```python
from selenium import webdriver
from selenium.webdriver.common.by import By

# Initialize WebDriver
driver = webdriver.Chrome()

# Open a webpage
driver.get("https://example.com")

# Locate radio buttons
rd_male = driver.find_element(By.XPATH, "//input[@id='gender-male']")
rd_female = driver.find_element(By.XPATH, "//input[@id='gender-female']")

# Print default radio button status
print("Default radio button status:")
print("Male selected:", rd_male.is_selected())  # False
print("Female selected:", rd_female.is_selected())  # False

# Select male radio button
rd_male.click()
print("After selecting male radio button:")
print("Male selected:", rd_male.is_selected())  # True
print("Female selected:", rd_female.is_selected())  # False

# Select female radio button
rd_female.click()
print("After selecting female radio button:")
print("Male selected:", rd_male.is_selected())  # False
print("Female selected:", rd_female.is_selected())  # True

# Close browser
driver.quit()
```

---

## **Conclusion**
Selenium WebDriver provides a wide range of commands to interact with web applications efficiently. In this blog, we covered:
- **Application commands** (title, URL, page source)
- **Conditional commands** (is_displayed, is_enabled, is_selected)
- **Browser commands** (close, quit)
- **Navigational commands** (back, forward, refresh)
- **Text vs get_attribute()**
- **Handling radio buttons**

Understanding and mastering these commands will make your automation scripts more robust and efficient. 🚀

Would you like more advanced topics like handling alerts, working with dynamic elements, or executing JavaScript in Selenium? Let us know in the comments! 😊

---

This blog provides clear explanations, formatted tables, and code snippets to make learning Selenium easy. Let me know if you need any modifications or additional topics! 🚀

import time
from selenium import webdriver
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.chrome.options import Options
from selenium.webdriver.common.by import By
from time import sleep 

class InvalidLoginTest:
    def __init__(self):
        options = Options()
        options.add_argument("--start-maximized")
        self.driver = webdriver.Chrome(service=Service(), options=options)

    def login(self, username, password):
        self.driver.get("https://www.saucedemo.com/")

        username_field = self.driver.find_element(By.XPATH, "//input[@id='user-name']")
        username_field.send_keys(username)

        sleep(3)

        password_field = self.driver.find_element(By.XPATH, "//input[@id='password']")
        password_field.send_keys(password)

        sleep(5)

        login_button = self.driver.find_element(By.XPATH, "//input[@id='login-button']")
        login_button.click()

        sleep(5)

        print("Invalid username and password.")

    def close(self):
        self.driver.quit()


class ValidLoginTest:
    def __init__(self):
        options = Options()
        options.add_argument("--start-maximized")
        self.driver = webdriver.Chrome(service=Service(), options=options)

    def login(self, username, password):
        self.driver.get("https://www.saucedemo.com/")

        username_field = self.driver.find_element(By.XPATH, "//input[@id='user-name']")
        username_field.send_keys(username)

        sleep(3)

        password_field = self.driver.find_element(By.XPATH, "//input[@id='password']")
        password_field.send_keys(password)

        sleep(5)

        login_button = self.driver.find_element(By.XPATH, "//input[@id='login-button']")
        login_button.click()

        sleep(5)

        if "inventory.html" in self.driver.current_url:
            print("Valid username/password test passed.")
        else:
            print("Valid username/password test failed.")

    def close(self):
        self.driver.quit()


if __name__ == "__main__":
    invalid_test = InvalidLoginTest()
    invalid_test.login("invalid_user", "wrong_password")
    invalid_test.close()

    valid_test = ValidLoginTest()
    valid_test.login("standard_user", "secret_sauce")
    valid_test.close()

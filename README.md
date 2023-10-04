# Script

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class SauceDemoAutomation {

    public static void main(String[] args) {
        // Create a new ChromeDriver instance
        WebDriver driver = new ChromeDriver();

        // Navigate to the SauceDemo website
        driver.get("https://www.saucedemo.com/");

        // Find the username and password fields
        WebElement usernameField = driver.findElement(By.id("username"));
        WebElement passwordField = driver.findElement(By.id("password"));

        // Enter the valid credentials
        usernameField.sendKeys("standard_user");
        passwordField.sendKeys("secret_sauce");

        // Click the login button
        driver.findElement(By.id("login-button")).click();

        // Add items to the cart
        driver.findElement(By.xpath("//a[@href='/inventory-item.html?id=1']")).click();
        driver.findElement(By.id("add-to-cart-sauce-labs-backpack")).click();

        driver.findElement(By.xpath("//a[@href='/inventory-item.html?id=2']")).click();
        driver.findElement(By.id("add-to-cart-sauce-labs-bolt-t-shirt")).click();

        // Checkout
        driver.findElement(By.xpath("//a[@class='shopping_cart_link']")).click();
        driver.findElement(By.id("checkout")).click();

        driver.findElement(By.id("first-name")).sendKeys("John");
        driver.findElement(By.id("last-name")).sendKeys("Doe");
        driver.findElement(By.id("postal-code")).sendKeys("12345");

        driver.findElement(By.id("continue")).click();
        driver.findElement(By.id("finish")).click();

        // Logout
        driver.findElement(By.id("react-burger-menu-btn")).click();
        driver.findElement(By.id("logout_sidebar_link")).click();

        // Close the browser
        driver.quit();
    }
}

# task09
navigation
package task009;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

import io.github.bonigarcia.wdm.WebDriverManager;

public class Navigation {

	public static void main(String[] args) {

		WebDriverManager.firefoxdriver().setup();
			WebDriver driver = new FirefoxDriver();
		try {
		driver.manage().window().maximize();
		 driver.navigate().to("http://google.com");
		System.out.println("Current URL:" +driver.getCurrentUrl());
		driver.navigate().refresh();
		}
		catch (Exception e) {
			e.printStackTrace();
			
		}
		finally {
			driver.quit();
			
		}

		}


	}
 demoblaze
 package org.WebDriver;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

import io.github.bonigarcia.wdm.WebDriverManager;


public class Chromedemoblaze {

	
	public static void main(String[] args) {
		WebDriverManager.chromedriver().setup();
		
	WebDriver driver = new ChromeDriver();
	try {
		driver.get("shttps://www.demoblaze.com");
		driver.manage().window().maximize();
		String pageTitle=driver.getTitle();
		if("Store".equals(pageTitle)) {
			System.out.println("PAGE LOADED iN THE CORRECT WEBSITE");
		}
		else {
			System.out.println("PAGE NOT LOADED iN THE CORRECT WEBSITE");
		}
	}
	catch(Exception e) {
		e.printStackTrace();
			
	}
	
	finally {
		driver.quit();
	}

	}

}

wikipedia

package org.WebDriver;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import io.github.bonigarcia.wdm.WebDriverManager;

public class Wikipedia {

	public static void main(String[] args) {
		WebDriverManager.chromedriver().setup();
		
		WebDriver driver = new ChromeDriver();
		try {
			driver.get("http://wikipedia.org");
			driver.manage().window().maximize();
			WebElement searchbox = (WebElement) driver.findElements(By.id("SEARCH INPUT"));
			searchbox.sendKeys("ARTIFICIAL INTELLIGENCE");
			searchbox.submit();
		    WebElement historyLink = driver.findElement(By.linkText("History"));
	        historyLink.click();
	        String pageTitle = driver.getTitle();
            System.out.println("The title of the page is: " + pageTitle);
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            // Close the browser
            driver.quit();
        }
	}

}

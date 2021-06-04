# projectCert

Adding Used Testing Selenium Code

package project;

import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.firefox.FirefoxOptions;

public class edurekaProject {
	public static void main(String arr[]) {
		
		System.setProperty("webdriver.gecko.driver", "/tmp/geckodriver");
		FirefoxOptions foxOption= new FirefoxOptions();
		foxOption.setHeadless(true);
		foxOption.addArguments("-headless");
		WebDriver driver=new FirefoxDriver(foxOption);
		
		driver.get("http://172.31.31.8:8081");
		driver.manage().timeouts().implicitlyWait(3, TimeUnit.SECONDS);
		System.out.println(driver.getTitle());
		driver.findElement(By.id("About Us")).click();
        String expectedItem= "about";
        System.out.println(driver.getPageSource().contains(expectedItem));       
		
	}
}

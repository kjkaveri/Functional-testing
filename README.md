import java.io.File;
import java.io.IOException;
import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

import com.google.common.io.Files;

public class test1 {

public static void main(String[] args) throws InterruptedException, IOException {
	System.setProperty("webdriver.chrome.driver","./softwares/chromedriver.exe");
	WebDriver driver=new ChromeDriver();
	driver.manage().window().maximize();
	driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
	driver.get("https://demo.dealsdray.com/");
	Thread.sleep(10000);	
	driver.findElement(By.name("username")).sendKeys("prexo.mis@dealsdray.com");
	driver.findElement(By.name("password")).sendKeys("prexo.mis@dealsdray.com");
	driver.findElement(By.xpath("//button[@type='submit']")).click();
	driver.findElement(By.xpath("//div[@class='sidenavHoverShow collapseIcon']")).click();
	driver.findElement(By.xpath("//span[text()='Orders']")).click();
	driver.findElement(By.xpath("//button[@align='right']")).click();
	driver.findElement(By.xpath("//input[@type='file']")).sendKeys("C:\\Users\\Nandi\\Downloads\\demo-data.xlsx");
	driver.findElement(By.xpath("//button[@type='button' and @class='MuiButton-root MuiButton-contained MuiButton-containedPrimary MuiButton-sizeMedium MuiButton-containedSizeMedium MuiButtonBase-root  css-6aomwy']")).click();
	Thread.sleep(6000);
	driver.findElement(By.xpath("//button[@class='MuiButton-root MuiButton-contained MuiButton-containedPrimary MuiButton-sizeMedium MuiButton-containedSizeMedium MuiButtonBase-root  css-6aomwy']")).click();
	File f=(File) ((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
	Files.copy(f, new File("D:\\downloads\\test sample\\dealsdray.jpg"));
}	
}

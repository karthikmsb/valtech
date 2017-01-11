package Test;


	import static org.junit.Assert.assertEquals;
	import java.util.List;

	import java.util.concurrent.TimeUnit;

	import org.junit.After;
	import org.junit.Before;
	import org.junit.Test;
	import org.openqa.selenium.By;
	import org.openqa.selenium.WebDriver;
	import org.openqa.selenium.WebElement;
	import org.openqa.selenium.firefox.FirefoxDriver;

	public class valtech {
		
		
		
		WebDriver driver;
		
		
		@Before
		public void one()
		{
			driver = new FirefoxDriver();
			driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
		    driver.manage().window().maximize();
			
			
		}
		
		@Test
		public void test1()
		{
    // Navigating to valtech and asserting latest news
    
    driver.get("https://www.valtech.com/");
		assertEquals("LATEST NEWS",driver.findElement(By.xpath("//*[@id='container']/div[2]/div[3]/div[1]/header/h2")).getText());
    
		// Navigating to Services and asserting h1 Tag (Services) 
		
		driver.findElement(By.xpath("//*[@id='navigationMenuWrapper']/div/ul/li[2]/a/span")).click(); 
		assertEquals("Services",driver.findElement(By.xpath("//*[@id='container']/section/header/h1")).getText()); 
   
   // Navigating to careers and asserting h1 Tag (careers) 
    
		driver.findElement(By.xpath("//*[@id='navigationMenuWrapper']/div/ul/li[5]/a/span")).click();
	    assertEquals("Careers",driver.findElement(By.xpath("//*[@id='container']/div[1]/h1")).getText());
		
    // To count the contacts
    
		driver.findElement(By.xpath("//*[@id='contacticon']/div/div/div[1]/i")).click();
		List<WebElement> lis=driver.findElements(By.cssSelector(".contactcountry>h3"));
		//int n=lis.size();
		System.out.println(lis.size());
		
			}
			
			
		@After
	public void test2()
	{
		
		driver.quit();
	}
		
		
	}

# EditREADME
The framework uses:
1.Java
2.Selenium
3.TestNG

In src/test/java i have created two pakages:
1.pages
2.TestCases
Under Pages pakage create BasePage.java class which consist code regarding setup browser and launch the website by providing URL
package pages.

public class BasePage {
	public WebDriver driver;
	WebDriverWait wait;
  
    @BeforeClass
    public void setUp() throws IOException {
        System.setProperty("webdriver.edge.driver", "C:\\Users\\User\\Downloads\\Entrata\\entrata\\src\\driver\\msedgedriver.exe");
 
        //add your driver extension in "src\\driver\\chromedriver.exe" this folder
        
        WebDriver driver = new EdgeDriver();
       
        try {
        	 driver.get("https://www.entrata.com/");
            driver.manage().window().maximize();
            // Locate and click the "Accept Cookies" button
            driver.findElement(By.xpath("//button[contains(text(), 'Accept Cookies')]")).click();
        } catch (Exception e) {e.printStackTrace();}
        
       
        wait=new WebDriverWait(driver,Duration.ofSeconds(30));
    
    }

}





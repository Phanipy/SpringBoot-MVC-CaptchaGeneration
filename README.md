# SpringBoot-MVC-CaptchaGeneration
This application helps to create Captchas in Spring Boot MVC Application.
Here, a Product registration page is floated to user with captcha generated from Spring Boot Controller class.
Once the user submits the registration form, the program has to validate the entered captcha. If it validated, then store the product information in the database other wise, generate a new captcha and float the registration form.

The zip file contain classes to generate captcha and return the same in JSP pages.

Points to note:
1. Required JpaRepository interfaces
2. Required SimpleCaptcha dependency from #MavenRepository
3. MySQL Database

Steps to follow:
1. Download the Zip file, extract and import to Eclipse Java EE and Web Developer IDE
2. Once, it is imported, open POM.xml file (dependency management file)- This file holds the required dependencies such as simplecaptcha, springweb,datajpa,jaxb-api,lombok, mysplconnector,tomcat and so on
3. Open the folder src/main/java, it contains a package. This package contains the required classes
   a. Model class (Product)- write variables for product and captcha variables (3 variables-captcha, realCaptcha, hiddenCaptcha)
   b. ProductRepository - Reporstory inteface which extends JpaRepostory<> interface
   c. ProductDAOService -DAO Service class to write our own methods to call the JpaRepository methods
   d. CaptchaUtil- This class is used to generate captha ( This class contains two methods- one method will generate captcha object and second method will encode the captcha object into byte array and then convert into String object)
   e. ProductController class- This class is repsonsible to recieve user request and then invoking the respective jsp pages
   f. Main method class, from which the application runs
4. Create a folder inside src --> main-->, as webapp
5. Inside webapp create another folder 'WEB-INF'
6. Inside WEB-INF, create another foloder 'jsp' to hold all the jsp files
7. The jsp files are register.jsp,ShowProducts.jsp,welcome.jsp

Also, under src/main/resources folder, check for application.properties file, Write the database respective code as follows:

spring.mvc.view.prefix= /WEB-INF/jsp/
spring.mvc.view.suffix= .jsp

spring.jpa.show-sql=true
spring.jpa.hibernate.ddl-auto=update
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
spring.datasource.url=jdbc:mysql://localhost:3306/<b>Databasename</b>
spring.datasource.username=root
spring.datasource.password=password

Change your database name and password of mysql database

Then run the WebCaptchaApplicatoin.java file to see the registration form.




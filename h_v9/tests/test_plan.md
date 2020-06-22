What you need:

    Python 3
    Selenium
    html-testRunner
    
Run steps:

install Python https://www.python.org/downloads/

Open terminal and type command: 
    
        1. 'pip install -r requirements.txt'
        3. 'python -m unittest -v suiteAllTest.py"

Chrome driver importand info:

    In test_data > CHROME_PATH = we must enter absolut path to file chromedrive.exe - use slash '/'
    
    example: 
    
    chrome_path = 'C:/Users/janis/PycharmProjects/hipp9/Page/Tests/Drivers/chromedriver
    
FireFox driver [geckodriver.exe] importand info:
    
    file gockodriver must be in the same directory as test file
***


## Test Scenario TS01: Check Login Functionality
    

### test_TS01_TC001_successful_login_with_username:

```yaml
test_TS01_TC001_successful_login_with_username:

Steps:
    1. Go to login page
    2. Verify by url if login page is show
    3. Try to login with correct username and password
    4. Verify by url if club page is show
    5. Click on icon account
    6. Verify logout button is visible
    7. Verify text button is "Wyloguj"
    8. Click on logout button
    9. Verify login button is visible
    10. Verify text button is "zaloguj"

Expected results: 
    Successful login with user name
```

 ### test_TS01_TC002_successful_login_with_email:

        Steps:
            1. Go to login page
            2. Verify by url if login page is show
            3. Try to login with correct e-mail address and password
            4. Verify by url if club page is show
            5. Click on icon account
            6. Verify text button is "Wyloguj"
            7. Click on logout button
            8. Verify text button is "zaloguj"
            
        Expected results:
            Successful login with email
                
### test_TS01_TC003_successful_login_with_email_capitalizer:

        Steps:
            1. Go to login page
            2. Type login - correct e-mail address with big first char
            3. Type correct password
            4. Click on icon account
            5. Verify text button is "Wyloguj"
        
        Expected results:
            Successful login with capitalizer email
            
### test_TS01_TC004_failed_login_correct_email_and_incorrect_password:

       Steps: 
            1. Go to login page
            2. Verify by url if login page is show
            3. Verify text button is "zaloguj"
            4. Type login - correct e-mail address
            5. Type invalid password
            6. Click on login button
            7. Verify by url if login page is still visible
            8. Click on icon account
            9. Verify text button is "zaloguj" - in drop-down
            10. Type login - correct e-mail address
            11. Type invalid password and click on "Enter" key
            12. Click on icon account
            13. Verify text button is not "Wyloguj"
            
       Expected results:
            Failed login
                 
### test_TS01_TC005_failed_login_incorrect_email_and_correct_password:

        Steps:
            1. Go to login page
            2. Type login - incorrect e-mail address
            3. Type correct password
            4. Click on login button
            5. Click on icon account
            6. Verify text button is not "Wyloguj" - in drop-down
            7. Type login - incorrect e-mail address
            8. Type correct password and click on "Enter" key
            9. Click on icon account
            10. Verify text button is "Zaloguj" -n drop-down
            
        Expected results:
            Failed login
            
### test_TS01_TC006_failed_login_correct_email_and_password_with_space_key:

        Steps:
            1. Go to login page
            2. Type login - space key + correct e-mail address
            3. Type password - space key + correct password
            4. Click on "Enter" key
            5. Click on icon account
            6. Verify text button is "Zaloguj"
            
        Expected results:
            Failed login
            
### test_TS01_TC007_failed_login_email_and_password_are_left_blank:

        Steps:
            1. Go to login page
            2. Click on password input
            3. Click on "Enter" key
            4. Verify text button is "Zaloguj"
            5. Click on login button
            6. Verify by url if login page is still visible
            7. Verify text button is "Zaloguj"
        
        Expected results:
            Failed login
            
### test_TS01_TC008_failed_login_reverse_data_input:

        Steps:
            1. Go to login page
            2. Type login - correct "passsword"
            3. Type password - correct "email"
            4. Click on "Enter" key
            5. Verify text button is "Zaloguj"

        Expected results:
            Failed login
            
## Test Scenario TS02: Check captcha functionality

 ### test_TS02_TC001_captcha_is_visible_after_three_times_incorrect_login:

        Steps:
            1. Go to home page
            2. Click on icon account
            3. Click on logout button
            4. Verify by url if login page is show
            5. Try to login with incorrect e-mail address and password *3 [three times]
            6. Verify by url if validation page is show
            7. Try to click on captcha checkbox

        Expected results:
            Captcha is visible

 ### test_TS02_TC002_captcha_is_visible_again_after_one_times_incorrect_login:
 
        Steps:
            1. Go to login page
            2. Verify by url if login page is show
            3. Try to login with incorrect e-mail address and password [only one]
            4. Verify by url if validation page is show
            5. Verify by text ['reCAPTCHA']if captcha is show
            6. Try to click on captcha checkbox
        
        Expected results:
            Captcha is visible
            
 ### test_TS02_TC003_captcha_is_visible_after_three_times_incorrect_login_total_quantity:
 
        Steps:
            1. Go to login page
            2. Try to login with incorrect e-mail address and password *2 [two times]
            3. Verify text button is still "Zaloguj"
            4. Login with correct e-mail address and password
            5. Click on icon account
            6. Verify link text is "Mój profil"
            7. Click on "Wyloguj"
            8. Try to login with incorrect e-mail address and password
            9. Try to click on captcha checkbox
            
        Expected results:
            Captcha is visible
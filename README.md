# Checklist
Checklist for testing "Sign up", "Log in", "Forget password" functions on facebook.com

| Test name                                                                        | Expected result                                                                                          | Status | Test type     |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|--------|---------------|
||_Sign Up function_||
| Create an account                                                                | Account is created                                                                                       | passed | Smoke test    |
| Check presence of created users'  account in database                            | There is information about user in database                                                              | passed | Critical path |
| Apply confirmation code from email                                               | Registration is finished. The usere is redirected  to his page                                           | passed | Critical path |
| Submit registration form with empty required fields                              | Each empty field that required to be filled in are highlighted in red color.  The form is not submitted. | passed | Extended test |
| Input a phone number in non-international format                                 | The form is submitted                                                                                    | failed | Critical path |
| Form submission with incorrect host name input in email                          | The message "Your request can not be proceed" occur                                                      | passed | Critical path |
| Into  the field "repeat email" input an email that doesn't match to the main one | The message "Your emails do not match. Try again" occur                                                  | passed | Critical path |
| Input date of birth from the future                                              | The message "It looks like you entered the wrong info. Please be sure to use your real birthday." occur  | passed | Critical path |
||_Log IN function_||
| Log in with created account                                                | The user is logged in                                                                                    | passed | Smoke test    |
| Log in with empty fields                                                   | The message "Please fill in required fields" occur                                                       |        | Extended test |
| Log in with empty password field                                           | The message "The password you’ve entered is incorrect. Forgot Password?" occur.                          | passed | Extended test |
| Log in with empty username field                                           | The message "Please fill in required fields" occur.                                                      |        | Extended test |
| Log in with correct username and incorrect password                        | The message "The password you’ve entered is incorrect. Forgot Password?" occur.                          | passed | Critical path |
| Log in with incorrect username and correct password                        | The message "We couldn't find an account matching the login info you entered" occur.                     | passed | Critical path |
| Log in with incorrect username and incorrect password                      | The message "The email you entered isn’t connected to an account. Create a new Facebook account." occur. | passed | Critical path |
| Use all capital letters for username                                       | The user is logged in                                                                                    | passed | Critical path |
| Use capital letters instead of lowercase letters and backwards in password | The user is logged in                                                                                    | passed | Critical path |
||_Forgot Password function_||
| Find account with correct email            | The password reset code is sent on specified email        | passed | Smoke test    |
| Find account with correct phone number     | The password reset code is sent on specified phone number | passed | Smoke test    |
| Use incorrect email to find account        | Account is created                                        | passed | Extended test |
| Use incorrect phone number to find account | Account is not found                                      | passed | Extended test |

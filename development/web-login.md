# Login feature


## User interface
The login page will be designed to be simple and user-friendly. It will include fields for theuser to enter their username and password, as well as a "Login" button to submit the credentials

## Components in User Interface in table format
| Component       | Description                                      | data-testid |
|-----------------|--------------------------------------------------|---------|
| Username Field  | Input field for the user to enter their username | username-field |
| Password Field  | Input field for the user to enter their password | password-field |
| Login Button    | Button to submit the login credentials           | login-button |

## Input Validation in table format
| Input Field | Validation Type | Error Message |
|-----------------|-----------------|---------------|
| Username Field  | Required        | Please enter your username |
| Password Field  | Required        | Please enter your password |

## Workflow
1. The user navigates to the login page.
2. The user enters their username and password in the respective fields.
3. The user clicks the "Login" button to submit the credentials.
4. The system validates the input fields to ensure they are not empty.
5. If any of the fields are empty, an error message is displayed prompting the user to fill in the required fields.
6. If both fields are filled, the system checks the credentials against the database.
7. If the credentials are valid, the user is logged in and redirected to the dashboard or home page.
8. If the credentials are invalid, an error message is displayed indicating that the username or password is incorrect, and the user is prompted to try again.

## Security Considerations
- Ensure that passwords are stored securely in the database using bcrypt hashing.
- Implement rate limiting to prevent brute-force attacks on the login endpoint.

## Test cases in table format
| Test Case ID | Test Case Name | Steps with inputs | Expected Result |
|--------------|----------------|-------------------|-----------------|
| TC001        | Successful Login | 1. Enter valid username="user1" and password="password123"<br>2. Click "Login" button | User is logged in and redirected to the dashboard |
| TC002        | Empty Username | 1. Leave username field empty and enter valid password="password123"<br>2. Click "Login" button | Error message "Please enter your username" is displayed |
| TC003        | Empty Password | 1. Enter valid username="user1" and leave password field empty<br>2. Click "Login" button | Error message "Please enter your password" is displayed |
| TC004        | Invalid Credentials | 1. Enter invalid username="user1" and password="wrongpassword"<br>2. Click "Login" button | Error message "Username or password is incorrect" is displayed | 

## Database Schema for login feature 
* Database file of sqlite is located at `demo.db` in the root directory of the project.

Table: users
| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| id          | INTEGER   | Primary key, auto-incremented user ID |
| username    | TEXT      | Unique username for the user |
| password    | TEXT      | Hashed password for the user |
| created_at  | DATETIME  | Timestamp of when the user was created |
| updated_at  | DATETIME  | Timestamp of when the user was last updated |

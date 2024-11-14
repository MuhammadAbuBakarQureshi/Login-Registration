
# C++ Account Registration and Login System

This repository contains a C++ implementation of a basic account registration and login system. The system utilizes a `hash table` for efficient data storage and employs password `hashing` and `salting` to ensure user security. It also includes `email validation` to ensure only valid `Google` email addresses are used.

## Features

* **Secure Password Handling:** Passwords are not stored in plain text. They are hashed using a strong function and salted with a unique random value for each user. The `salt` is generated using `ASCII` values between 33 and 127, adding an extra layer of protection.

* **Efficient Data Storage:** User data is stored in a `hash table` for fast access and retrieval. This data structure allows for efficient lookups based on the user's email address.

* **Data Persistence:** User data is saved to a CSV file for persistence between sessions. This ensures that user accounts and their associated information are preserved even after the program is closed.

* **Email Validation:** The system validates email addresses to ensure they are valid `Google` emails (e.g., "`user@gmail.com`"). This helps prevent the registration of invalid or malicious email addresses.
## Secure Sign-up Process

**The sign-up process involves:**

* Taking the user's email as input.

* Checking if an account with the same email already exists in the `hash table`. If it does, the sign-up process fails.

* If the email is unique, taking the user's password as input. Generating a random salt for the password using `ASCII` values between 33 and 127.

* Hashing the password using the chosen hash function and the generated salt.

* Storing the email, hashed password, and salt in the `hash table`.

* Saving the data to the `CSV` file for persistence.
## Secure Login Process


**The login process involves:**

* Taking the user's email and password as input.

* Retrieving the corresponding salt and hashed password from the hash table based on the provided email.

* Hashing the provided password using the same hash function and salt retrieved from the hash table.
    
* Comparing the newly hashed password with the stored hashed password.
    
* If the two hashed passwords match, the login is successful.

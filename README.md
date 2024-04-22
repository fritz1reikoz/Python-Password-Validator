![MainPix](https://github.com/fritz1reikoz/Python-Password-Validator/assets/55414490/9ceaff8f-cf39-4ccf-abc7-c2b5a4e90a43)

Welcome to the process of creating a password validator script in python. 
This Python script would check password strength based on criteria like length, character types (uppercase, lowercase, numbers, symbols).
It could offer suggestions for stronger passwords.

See complete code: https://github.com/fritz1reikoz/Python-Password-Validator/blob/main/PPV.ipynb

If you're running the above codes on any other platform besides "Google Colab" and encounter  an error related to "matplotlib", Follow the following steps to fix the issue.

<b>matplotlib Fix:</b>

<b>Step 1:</b> Install pip - Check if you have pip already simply by writing pip in the python console. If you don't have pip, get a python script called get-pip.py, here: https://bootstrap.pypa.io/get-pip.py (You'll have use windows "Save As" option)

![pip](https://github.com/fritz1reikoz/Python-Password-Validator/assets/55414490/ab21a644-66b4-4a0f-a586-3e983abe5465)

<b>Step 2:</b> Take note of where the file got saved and cd the directory from command prompt. Run the get-pip.py script to install pip. You can write in cmd this line within quotes: "python .\get-pip.py"

<b>Step 3:</b> Now in cmd type: pip install matplotlib

And you should be through.

![cmd matplotlib](https://github.com/fritz1reikoz/Python-Password-Validator/assets/55414490/3db6ad64-5802-4384-8bce-948aa11099a0)

![StrongP](https://github.com/fritz1reikoz/Python-Password-Validator/assets/55414490/c3637317-537c-4d91-9f0d-64014f1cca53)


<h2>Explanation:</h2>

<b>1. is_valid_password function:</b>

  -Takes a password string as input.
  -Defines minimum length requirement (min_length).
  -Checks password length using len(password).
  -Uses list comprehensions to efficiently check for character types.
    *any(char.isupper() for char in password): Checks if at least one character is uppercase.
    *Similar logic for lowercase (islower()), digits (isdigit()), and symbols (not char.isalnum()).
  -Returns True if all criteria are met, False otherwise.


<b>2. main function:</b>

  -Prompts the user to enter a password using input.
  -Calls is_valid_password to check the password.
  -Prints a message based on the validation result.
    *If valid, congratulates the user.
    *If invalid, provides specific suggestions for improvement based on missing criteria.

<b>3. if __name__ == "__main__": block:</b>

  -Ensures the main function runs only when the script is executed directly (not imported as a module).


<b>4. calculate_password_strength function:</b>

  -Similar to the previous version, it calculates a score based on password criteria.
  -Introduces a bonus point for passwords with no repeated characters (len(set(password))).
  -Determines the strength level ("Weak", "Medium", "Strong") based on the score.


<b>5. visualize_password_meter function:</b>

  -Uses matplotlib to create a bar chart for visual feedback.
  -Defines colors based on strength level (red for weak, orange for medium, green for strong).
  -Creates a bar plot with a maximum width of 5 (representing the score).
  -Removes unnecessary axes and labels for a cleaner meter.
  -Displays the meter using plt.show().


<b>6. main function:</b>

  -Prompts the user for a password.
  -Calls calculate_password_strength to get the level and score.
  -Prints the strength level message.
  -Calls visualize_password_meter to display the password meter.

<h2>How to use:</h2>

1. Save the code as a Python file (e.g., password_validator_meter.py).
2. Install matplotlib using pip install matplotlib (if not already installed).
3. Run the script using python password_validator_meter.py in your terminal.
4. Enter your password when prompted.
5. The script will display the password strength level ("Weak", "Medium", "Strong") and a color-coded meter for visual feedback.

![MainPix](https://github.com/fritz1reikoz/Python-Password-Validator/assets/55414490/9ceaff8f-cf39-4ccf-abc7-c2b5a4e90a43)

Welcome to the process of creating a password validator script in python. 
This Python script would check password strength based on criteria like length, character types (uppercase, lowercase, numbers, symbols).
It could offer suggestions for stronger passwords.


import matplotlib.pyplot as plt

def calculate_password_strength(password):
  """
  This function calculates the strength of a password based on various criteria.

  Args:
      password: The password string to be evaluated.

  Returns:
      A tuple containing:
          - Strength level (string): "Weak", "Medium", or "Strong"
          - Score (integer): A score between 0 and 5 indicating password strength
  """

  # Minimum length requirement
  min_length = 8
  score = 0

  # Length check
  if len(password) >= min_length:
    score += 1
  else:
    return "Weak", score

  # Character type requirements (uppercase, lowercase, number, symbol)
  has_uppercase = any(char.isupper() for char in password)
  has_lowercase = any(char.islower() for char in password)
  has_digit = any(char.isdigit() for char in password)
  has_symbol = any(not char.isalnum() for char in password)

  # Character type bonus points
  if has_uppercase:
    score += 1
  if has_lowercase:
    score += 1
  if has_digit:
    score += 1
  if has_symbol:
    score += 1

  # Additional complexity bonus
  if len(set(password)) > len(password) // 2:  # Check for repeated characters
    score += 1

  # Determine strength level based on score
  strength_level = "Weak"
  if score >= 3:
    strength_level = "Medium"
  if score >= 4:
    strength_level = "Strong"

  return strength_level, score

def visualize_password_meter(score):
  """
  This function creates a bar chart to visually represent password strength.
  """

  # Define colors based on strength level
  colors = ["red", "orange", "green"]

  # Set plot limits
  plt.xlim(0, 5)
  plt.ylim(0, 1)

  # Create bar plot
  plt.bar(1, score, color=colors[min(2, score)])  # Limit color index to 2 (max)

  # Remove axes and labels for a cleaner meter
  plt.xticks([])
  plt.yticks([])
  plt.axis('off')

  # Display meter
  plt.show()

def main():
  """
  This function prompts the user for a password and displays the validation result with meter.
  """
  password = input("Enter your password: ")

  strength_level, score = calculate_password_strength(password)

  print(f"Password Strength: {strength_level}")
  visualize_password_meter(score)

if __name__ == "__main__":
  main()


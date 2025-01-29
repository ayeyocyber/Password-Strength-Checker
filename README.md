# Password Strength Checker

This is a simple tool to evaluate the strength of a password based on length and character variety while providing security recommendations.

## Features:
- Checks if the password is weak, medium, or strong based on the following criteria:
  - Weak: Less than 6 characters or no special characters.
  - Medium: Between 6-8 characters with some numbers or special characters.
  - Strong: More than 8 characters, including upper/lowercase letters, numbers, and special characters.


## Usage:
- Enter your password in the input field and click the 'Enter' key on your desktop to see how strong your password is.
You can use my code here: https://www.online-python.com

## Code: 
    import re

    def check_password_strength(password):
    strength = 0
    recommendations = []

    if len(password) >= 8:
        strength += 1
    else:
        recommendations.append("Make the password at least 8 characters long.")

    if re.search(r"[A-Z]", password):
        strength += 1
    else:
        recommendations.append("Include at least one uppercase letter.")

    if re.search(r"[a-z]", password):
        strength += 1
    else:
        recommendations.append("Include at least one lowercase letter.")

    if re.search(r"\d", password):
        strength += 1
    else:
        recommendations.append("Include at least one number.")

    if re.search(r"[!@#$%^&*(),.?\":{}|<>]", password):
        strength += 1
    else:
        recommendations.append("Include at least one special character.")

    levels = ["Very Weak", "Weak", "Moderate", "Strong", "Very Strong"]
    
    print(f"Password Strength: {levels[strength]}")
    if recommendations:
        print("\nRecommendations:")
        for rec in recommendations:
            print(f"- {rec}")

        if __name__ == "__main__":
    user_password = input("Enter your password: ")
    check_password_strength(user_password)

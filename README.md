import random
import string

def generate_password(length=12):
    if length < 6:
        raise ValueError("The minimum password length must be 6.")
    characters = string.ascii_letters + string.digits + "!@#$%^&*()-_+=<>?/|"
    password = ''.join(random.choice(characters) for _ in range(length))
    return password

def main():
    try:
        length = int(input("Enter the password length (minimum 6): "))
        password = generate_password(length)
        print(f"Your generated password is: {password}")
    except ValueError as e:
        print(f"Error: {e}")

if __name__ == "__main__":
    main()

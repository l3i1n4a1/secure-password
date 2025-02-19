# secure-password


import random
import string

def generate_password(length=12, use_digits=True, use_special_chars=True):
    letters = string.ascii_letters
    digits = string.digits if use_digits else ''
    special_chars = string.punctuation if use_special_chars else ''
    
    all_chars = letters + digits + special_chars
    
    if length < 4:
        raise ValueError("Le mot de passe doit contenir au moins 4 caractères.")
    
    password = random.sample(all_chars, length)
    return ''.join(password)

if __name__ == "__main__":
    length = int(input("Entrez la longueur du mot de passe : "))
    use_digits = input("Inclure des chiffres ? (y/n) : ").lower() == 'y'
    use_special_chars = input("Inclure des caractères spéciaux ? (y/n) : ").lower() == 'y'
    
    print("Mot de passe généré :", generate_password(length, use_digits, use_special_chars))

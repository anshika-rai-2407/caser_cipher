# caser_cipher
project 4 for phython, it is a code which will encrypt and send our normal text msg example whatsapp
this was a fun one loved making it , also it helped me clear up return/print doubts for a function


def caesar(text, shift, encrypt=True):

    if not isinstance(shift, int):
        return 'Shift must be an integer value.'

    if shift < 1 or shift > 25:
        return 'Shift must be an integer between 1 and 25.'

    alphabet = 'abcdefghijklmnopqrstuvwxyz'

    if not encrypt:
        shift = - shift
    
    shifted_alphabet = alphabet[shift:] + alphabet[:shift]
    translation_table = str.maketrans(alphabet + alphabet.upper(), shifted_alphabet + shifted_alphabet.upper())
    encrypted_text = text.translate(translation_table)
    return encrypted_text

def encrypt(text, shift):
    return caesar(text, shift)
    
def decrypt(text, shift):
    return caesar(text, shift, encrypt=False)

encrypted_text ='Pbhentr vf sbhaq va hayvxryl cynprf.'

decrypted_text=decrypt(encrypted_text,13)
print(decrypted_text)

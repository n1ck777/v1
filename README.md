# v1
import string

def filter_text(text, alphabet, mode):
    filtered_text = ""
    if mode == "normal":
        # фильтрация текста по обычному алфавиту
        for char in text:
            if char.lower() in alphabet:
                filtered_text += char.lower()
            elif char in string.whitespace:
                filtered_text += ""
    elif mode == "with_space":
        # фильтрация текста по алфавиту с пробелом
        for char in text:
            if char.lower() in alphabet:
                filtered_text += char.lower()
            elif char in string.whitespace:
                if filtered_text and filtered_text[-1] != " ":
                    filtered_text += " "
            else:
                filtered_text += " "
    else:
        print("Неверный режим фильтрации.")
        return None

    filtered_text = filtered_text.strip()

    return filtered_text

text = input("Введите текст: ")
alphabet = input("Введите алфавит: ")
mode = input("Выберите режим фильтрации (normal или with_space): ")

filtered_text = filter_text(text, alphabet, mode)

if filtered_text:
    print("Отфильтрованный текст:", filtered_text)

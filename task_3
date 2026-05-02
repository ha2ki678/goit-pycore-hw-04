import sys
from pathlib import Path

try:
    from colorama import Fore, Style, init
except ImportError:
    print("Бібліотека colorama не встановлена.")
    print("Спочатку створіть віртуальне оточення і встановіть colorama:")
    print("python -m venv venv")
    print("source venv/bin/activate")
    print("pip install colorama")
    sys.exit(1)

init(autoreset=True)

def print_directory_structure(path, level=0):
    items = sorted(path.iterdir(), key=lambda item: (item.is_file(), item.name.lower()))

    for item in items:
        space = "    " * level

        if item.is_dir():
            print(space + Fore.BLUE + item.name + "/")
            print_directory_structure(item, level + 1)
        else:
            print(space + Fore.GREEN + item.name)

def main():
    if len(sys.argv) != 2:
        print("Використання: python hw03.py /шлях/до/директорії")
        return

    folder_path = Path(sys.argv[1])

    if not folder_path.exists():
        print("Помилка: такого шляху не існує.")
        return

    if not folder_path.is_dir():
        print("Помилка: вказаний шлях не є директорією.")
        return

    print(Fore.BLUE + Style.BRIGHT + folder_path.name + "/")
    print_directory_structure(folder_path, 1)

if __name__ == "__main__":
    main()
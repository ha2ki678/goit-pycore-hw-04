def get_cats_info(path):
    cats_list = []

    try:
        with open(path, "r", encoding="utf-8") as file:
            for line in file:
                line = line.strip()

                if line:
                    cat_data = line.split(",")
                    cat_dict = {
                        "id": cat_data[0],
                        "name": cat_data[1],
                        "age": cat_data[2]
                    }
                    cats_list.append(cat_dict)

    except FileNotFoundError:
        print("Файл не знайдено.")
    except Exception:
        print("Сталася помилка під час читання файлу.")

    return cats_list

cats_info = get_cats_info("cats_file.txt")
print(cats_info)
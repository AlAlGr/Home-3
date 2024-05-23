# Чтение содержимого всех файлов

files = []

file_names = ["1.txt", "2.txt"]

for file_name in file_names:

    with open(file_name, "r") as file:

        content = file.readlines()

        files.append((file_name, content))

# Сортировка файлов по количеству строк

files.sort(key=lambda x: len(x[1]))

# Запись отсортированного содержимого в новый файл

output_file_name = "output.txt"

with open(output_file_name, "w") as output_file:

    for file_name, content in files:

        output_file.write(file_name + "\n")

        output_file.write(str(len(content)) + "\n")

        output_file.writelines(content)
        
        output_file.write("\n")

print("Результат записан в файл", output_file_name)
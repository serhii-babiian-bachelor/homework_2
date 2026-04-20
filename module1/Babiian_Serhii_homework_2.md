Домашнє завдання №2: Файлова система і права доступу
Виконав: [Твоє Прізвище та Ім'я]

Завдання 1. Ієрархія каталогів Linux
Bash
# 1. Перехід в кореневий каталог і показ вмісту
cd /
ls -l

# 2. Перехід в /etc і показ вмісту
cd /etc
ls

# 3. Перехід у каталог /home і показ список користувачів
cd /home
ls -l
Завдання 2. Файли, каталоги та посилання
Bash
# 1. Створення нового каталогу у домашньому каталозі
mkdir ~/my_work

# 2. Створення файлу всередині
touch ~/my_work/original.txt

# 3. Копіювання файлу у нове ім’я
cp ~/my_work/original.txt ~/my_work/copy.txt

# 4. Перейменування копії
mv ~/my_work/copy.txt ~/my_work/renamed_copy.txt

# 5. Створення жорсткого посилання (hard link)
ln ~/my_work/original.txt ~/my_work/hard_link.txt

# 6. Створення символічного посилання (soft link)
ln -s ~/my_work/original.txt ~/my_work/soft_link.txt

# 7. Пошук файлу за ім'ям
find ~/my_work -name "original.txt"
Завдання 3. Права доступу
Bash
# 1. Перегляд прав файлу
ls -l ~/my_work/original.txt

# 2. Надання прав тільки на читання (read-only для всіх)
chmod 444 ~/my_work/original.txt

# 3. Надання власнику права на запис (400 + 200 = 600)
chmod 644 ~/my_work/original.txt

# 4. Перегляд значення umask
umask

# 5. Встановлення нового значення umask
umask 022
Завдання 4. Користувачі
Примітка: для цих команд потрібні права суперкористувача (sudo).

Bash
# 1. Створення нового користувача (наприклад, trainee)
sudo adduser trainee

# 2. Додавання його до sudo-групи
sudo usermod -aG sudo trainee

# 3. Перевірка, що користувач існує (пошук у файлі /etc/passwd)
grep "trainee" /etc/passwd
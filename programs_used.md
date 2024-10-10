## Используемые программы в Debian
---
### 1) Программирование

* **gcc**

```bash
apt install gcc -y
```

* **CMake**

```bash
apt install cmake -y
```

* **Vim**

```bash
apt install vim -y
```

* **Git**

```bash
apt install git -y

#----------------------------- НАСТРОЙКА ----------------------------------#

git config --global user.name    "<username>"
git config --global user.email   "<e-mail>"
git config --global core.editor  "vim"

ssh-keygen -t ed25519 -C "<e-mail>"
#--------------------------------------------------------------------------#
# Ввести файл, где будет сохранён ключ (Enter: оставить предлагаемый).     #
# Ввести кодовую фразу для генерируемого ключа (Enter: без кодовой фразы). #
#--------------------------------------------------------------------------#
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
cat ~/.ssh/id_ed25519.pub
#--------------------------------------------------------------------------#
# Скопировать весь вывод команды cat.                                      #
# Перейти на: https://github.com/settings/keys.                            #
# Добавить в ключи скопированное значение.                                 #
#--------------------------------------------------------------------------#

```

* **Qt, Qt Assistant, Qt Creator**

```bash
apt install build-essential qt6-base-dev qtcreator qml6-module-* qt6-*-dev -y
```

* **SQLite, SQLite Manager**

```bash
apt install sqlite3 sqlitebrowser -y
```

* **GhostWriter**

```bash
apt install ghostwriter -y
```

* **Konsole**

```bash
apt install konsole -y
```

* **Pluma**

```bash
apt install pluma -y
```



---

### 2) Графика, видео, аудио


---


### 3) Комплект офисных программ


---


### 4) Браузер


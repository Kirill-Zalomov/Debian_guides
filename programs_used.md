## Используемые программы в Debian
---
### 1) Программирование

* **gcc**

```bash
apt install gcc -y            # Скачивание
apt remove --purge gcc -y     # Удаление
```

* **CMake**

```bash
apt install cmake -y          # Скачивание
apt remove --purge cmake -y   # Удаление
```


* **Vim**

```bash
apt install vim -y            # Скачивание
apt remove --purge vim -y     # Удаление
```

* **Git**

```bash
apt install git -y            # Скачивание
apt remove --purge git -y     # Удаление

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

* Qt, Qt Assistant, Qt Creator

```bash
apt install build-essential qt6-base-dev qtcreator -y
```

* SQLite, SQLite Manager


```bash

```


* GhostWriter



```bash

```

* Konsole



```bash

```



```bash
su -

apt install gcc cmake vim git konsole ghostwriter -y






```
## Часто используемые команды apt
---

* **Проверка доступности пакета для установки**

```console
apt policy <package_name>

# Пример
apt policy git
```

* **Установка пакета**

```console
apt install <package_name> -y

# Пример
apt install git -y
```

* **Удаление пакета**

```console
apt remove <package_name>          # Удалить только программу
apt remove --purge <package_name>  # Удалить и программу и её конфигурационные файлы
                                   # (кроме файлов конфигурации в домашнем каталоге)
# Примеры
apt remove git
apt remove --purge git
```

* **Вывод списка установленных пакет**

```console
apt list --installed
```

* **Вывод списка пакетов, для которых доступны обновления**

```console
apt list --upgradable
```

* **Обновить список доступных пакетов**

```console
apt upgrade
```

* **Обновить систему, устанавливая/обновляя пакеты**

```console
apt update
```

* **Автоматическое удаление всех неиспользуемых пакетов**

```console
apt autoremove -y
```

<br>  
<br>  

---
Кроме apt часто используется утилита apt-file, позволяющая определить, к какому пакету относится искомый файл и наоборот - из каких файлов состоит пакет:
```console
sudo apt-file update
apt-file search /bin/chmod
apt-file show coreutils
```

<br>  
<br>  

---
Список репозиториев, доступных для скачивания ПО, находится по адресу:
```console
/etc/apt/sources.list
```

<br>  
<br>  
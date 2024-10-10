## Часто используемые команды apt
---

* **Проверка доступности пакета для установки**

```bash
apt policy <package_name>

# Пример
apt policy git
```

* **Установка пакета**

```bash
apt install <package_name> -y

# Пример
apt install git -y
```

* **Удаление пакета**

```bash
apt remove <package_name>          # Удалить только программу
apt remove --purge <package_name>  # Удалить и программу и её конфигурационные файлы
                                   # (кроме файлов конфигурации в домашнем каталоге)
# Примеры
apt remove git
apt remove --purge git
```

* **Вывод списка установленных пакет**

```bash
apt list --installed
```

* **Вывод списка пакетов, для которых доступны обновления**

```bash
apt list --upgradable
```

* **Обновить список доступных пакетов**

```bash
apt upgrade
```

* **Обновить систему, устанавливая/обновляя пакеты**

```bash
apt update
```

* **Автоматическое удаление всех неиспользуемых пакетов**

```bash
apt autoremove -y
```
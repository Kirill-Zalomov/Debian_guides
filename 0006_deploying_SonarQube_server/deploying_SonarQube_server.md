## Развёртывание сервера статического анализатора SonarQube  

---  

<br>  

## Оглавление

1. [Цели и задачи](#сhapter_1)  
2. [Выбор проекта на Java с открытым исходным кодом для тестирования работы статического анализатора SonarQube](#сhapter_2)  
3. [Установка и сборка выбранного проекта](#сhapter_3)  
  3.1. [Установка OpenJDK 21](#сhapter_3.1)  
  3.2. [Установка Maven](#сhapter_3.2)  
  3.3. [Сборка программы Pixelitor](#сhapter_3.3)  
  3.3. [Запуск программы Pixelitor](#сhapter_3.4)  
4. [Поиск официальных источников информации о SonarQube, документации и инструкции по развёртыванию](#сhapter_4)  
5. [Изучение системных требований SonarQube](#сhapter_5)  


<br>  
<br>  

---  

<a name="сhapter_1"></a>
### 1) Определение целей и задач статьи  

- Выбрать проект с открытым исходным кодом на Java для тестирования работы статического анализатора SonarQube.
- Выполнить настройку среды и провести сборку выбранного проекта.
- Найти официальные источники информации по SonarQube.
- Изучить системные требования для установки SonarQube Community Build.
- Исходя из изученных системных требований, подготовить виртуальные машины для развёртывания сервера SonarQube Community Build.
- Установить SonarQube Community Build на виртуальные машины.
- Проверить корректность установки SonarQube Community Build.
- После установки SonarQube Community Build скачать сканер для статического анализа кода на Java.
- Провести статический анализ выбранного проекта.

<br>  
<br>  

---  

<a name="сhapter_2"></a>
### 2) Выбор проекта на Java с открытым исходным кодом для тестирования работы статического анализатора SonarQube  

Для тестирования статического анализатора SonarQube был выбран проект Pixelitor (рисунок 1):  
- [github.com](https://github.com/lbalazscs/Pixelitor)  
- [pixelitor.sourceforge.io](https://pixelitor.sourceforge.io/)  

![Графический интерфейс программы Pixelitor](images/1.png)
Рисунок 1 --- Графический интерфейс программы Pixelitor

<br>  
<br>  

---  

<a name="сhapter_3"></a>
### 3) Установка и сборка выбранного проекта  

Для скачивания исходных кодов программы, сборки проекта и запуска программы будет использоваться ОС Debian 12 Bookworm. 

Из описания проекта Pixelitor на github.com следует, что для сборки проекта кроме исходных кодов потребуются:  

- OpenJDK 21+  
- Maven  

<a name="сhapter_3.1"></a>
#### 3.1) Установка OpenJDK 21  

Поскольку OpenJDK 21 не входит в стабильную ветку apt, установим данный пакет с packages.adoptium.net:

```console
# Установка через apt двух утилит:
# wget                 — утилита командной строки для загрузки файлов из интернета по HTTP, HTTPS и FTP
# apt-transport-https  — пакет, который позволяет apt работать с репозиториями, доступными по протоколу HTTPS
sudo apt install -y wget apt-transport-https

# Загрузка публичного GPG-ключа и его сохранение в системе для проверки подлинности пакетов из репозитория Adoptium
wget -qO - https://packages.adoptium.net/artifactory/api/gpg/key/public | sudo tee /etc/apt/trusted.gpg.d/adoptium.asc

# Добавление репозитория Adoptium в список источников пакетов (sources.list)
echo "deb https://packages.adoptium.net/artifactory/deb $(awk -F= '/^VERSION_CODENAME/{print$2}' /etc/os-release) main" | sudo tee /etc/apt/sources.list.d/adoptium.list

# Обновление локальной базы данных пакетов, доступных в репозиториях
sudo apt update

# Установка пакета temurin-21-jdk (OpenJDK 21)
sudo apt install temurin-21-jdk
```

Проверим корректность установки OpenJDK 21 (рисунок 2):  

```console
java --version
```

![Проверка корректности установки OpenJDK 21](images/2.png)  
Рисунок 2 --- Проверка корректности установки OpenJDK 21  

<a name="сhapter_3.2"></a>
#### 3.2) Установка Maven  

```console
sudo apt install -y maven
```

Проверим корректность установки Maven (рисунок 3):  

```console
mvn --version
```

![Проверка корректности установки Maven](images/3.png)  
Рисунок 3 --- Проверка корректности установки Maven  

<a name="сhapter_3.3"></a>
#### 3.3) Сборка программы Pixelitor  

Выполним клонирование исходных кодов программы Pixelitor с github.com в заранее подготовленную папку (рисунок 4):

```console
git clone https://github.com/lbalazscs/Pixelitor.git
```

![Клонирование исходного кода проекта Pixelitor](images/4.png)  
Рисунок 4 --- Клонирование исходного кода проекта Pixelitor  

Перейдя в папку Pixelitor, выполним сборку без запуска тестов:

```console
mvn clean package -Dmaven.test.skip=true
```

В результате сборки должно вывестись сообщение об успешном завершении сборки (рисунок 5).

![Успешное завершение сборки проекта Pixelitor](images/5.png)  
Рисунок 5 --- Успешное завершение сборки проекта Pixelitor  

<a name="сhapter_3.4"></a>
#### 3.4) Запуск программы Pixelitor  

Для запуска программы необходимо перейти внутри папки проекта в директорию __target__ и ввести команду:

```console
java -jar Pixelitor-4.3.1.jar
```

После этого программа будет запущена (рисунок 6):  

![Запуск программы Pixelitor](images/6.png)  
Рисунок 6 --- Запуск программы Pixelitor  

<br>  
<br>  

---  

<a name="сhapter_4"></a>
### 4) Поиск официальных источников информации о SonarQube, документации и инструкций по установке/настройке  

| Название источника | Ссылка |
|---|---|
| Официальный сайт SonarQube | [www.sonarsource.com](https://www.sonarsource.com/) |
| Информация о различных версиях анализатора | [www.sonarsource.com](https://www.sonarsource.com/products/sonarqube/downloads/) |
| Документация по SonarQube | [docs.sonarsource.com](https://docs.sonarsource.com/sonarqube-server/latest/) |
| Системные требования SonarQube | [docs.sonarsource.com](https://docs.sonarsource.com/sonarqube-server/latest/setup-and-upgrade/installation-requirements/server-host/) |
| Официальная инструкция по установке SonarQube Community Build | [docs.sonarsource.com](https://docs.sonarsource.com/sonarqube-server/latest/try-out-sonarqube/) |
| Официальная инструкция по постустановочной настройке SonarQube | [docs.sonarsource.com](https://docs.sonarsource.com/sonarqube-server/latest/analyzing-source-code/overview/) |

<br>  
<br>  

---  

<a name="сhapter_5"></a>
### 5) Изучение системных требований SonarQube

Системные требования будут 




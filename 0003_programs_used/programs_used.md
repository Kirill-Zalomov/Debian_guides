## Установка и настройка часто используемых программ в Debian
---

### 1) Браузер и приложения графической оболочки MATE

* **Браузер: Mozilla Firefox**

```sh
apt install firefox-esr/stable-security firefox-esr-l10n-ru/stable-security -y
```

* **Приложения графической оболочки MATE:**
	- GUI-файловый менеджер: __Caja__
	- GUI-приложение для просмотра изображений: __Eye of MATE__
	- GUI-текстовый редактор: __Pluma__
	- GUI-программа для работы с архивами: __Engrampa__
	- Терминал: __MATE Terminal__

```sh
apt install mate-desktop-environment -y
```

---

### 2) Дополнительный менеджер пакетов

* **Менеджер пакетов: Snap**

```sh
apt install snap -y
snap install snapd -y
```

---

### 3) Программирование

* **Компилятор для C++: gcc**

```sh
apt install gcc -y
```

* **Система сборки проектов: CMake**

```sh
apt install cmake -y
```

* **Консольный текстовый редактор: Vim**

```sh
apt install vim -y
```

* **Система контроля версий: Git**

```sh
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

* **IDE: Qt, Qt Creator, Qt Assistant**

```sh
apt install build-essential qt6-base-dev qtcreator qml6-module-* qt6-*-dev -y

#----------------------------- НАСТРОЙКА -------------------------------------#
# Смена языка интерфейса на английский:                                       #
# Edit -> Preferences -> Environment -> Language -> English                   #
#                                                                             #
# Настройка тёмной темы:                                                      #
# Edit -> Preferences -> Environment -> Theme -> Dark                         #
#                                                                             #
# Настройка стиля Visual Studio для редактора:                                #
#   Создать каталог "styles", если его нет, по пути:                          #
#   "~/.config/QtProject/qtcreator/styles/"                                   #
#   Создать файл "VisualStudioDark.xml" в каталоге "styles".                  #
#   Содержание для "VisualStudioDark.xml" представлено ниже в гайде.          #
# Edit -> Preferences -> Text Editor -> Color Scheme -> Visual Studio Dark v2 #
#                                                                             #
# По необходимости перезапустить Qt Creator                                   #
#-----------------------------------------------------------------------------#
```

Стиль для Qt Creator "[Visual Studio Dark v2](https://github.com/yhvicey/Visual-Studio-2015-Dark-Theme-for-Qt-Creator)" от [yhvicey](https://github.com/yhvicey)  
VisualStudioDark.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<style-scheme version="1.0" name="Visual Studio Dark v2">
  <style name="Text" foreground="#dcdcdc" background="#1e1e1e"/>
  <style name="Link"/>
  <style name="Selection" background="#264f78"/>
  <style name="LineNumber" foreground="#2b91af" background="#191919"/>
  <style name="SearchResult" background="#623916"/>
  <style name="SearchResultAlt1" foreground="#000033" background="#4f5f73"/>
  <style name="SearchResultAlt2" foreground="#330000" background="#ffb6cc"/>
  <style name="SearchResultContainingFunction"/>
  <style name="SearchScope" background="#12202a"/>
  <style name="Parentheses" foreground="#b4b4b4"/>
  <style name="ParenthesesMismatch" foreground="#b4b4b4"/>
  <style name="AutoComplete"/>
  <style name="CurrentLine" background="#0f0f0f"/>
  <style name="CurrentLineNumber" foreground="#2b91af"/>
  <style name="Occurrences"/>
  <style name="Occurrences.Unused"/>
  <style name="Occurrences.Rename"/>
  <style name="Number" foreground="#b5cea8"/>
  <style name="String" foreground="#d69d85"/>
  <style name="Type" foreground="#4ec9b0"/>
  <style name="Namespace" foreground="#c8c8c8"/>
  <style name="Local" foreground="#9cdcfe"/>
  <style name="Parameter" foreground="#9a9a9a"/>
  <style name="Global"/>
  <style name="Field" foreground="#dadada"/>
  <style name="Static" foreground="#b8d7a3"/>
  <style name="VirtualMethod" foreground="#dcdcaa"/>
  <style name="Function" foreground="#dcdcaa"/>
  <style name="Keyword" foreground="#569cd6"/>
  <style name="PrimitiveType" foreground="#569cd6"/>
  <style name="Operator" foreground="#b4b4b4"/>
  <style name="Overloaded Operator" foreground="#b4b4b4"/>
  <style name="Punctuation" foreground="#b4b4b4"/>
  <style name="Preprocessor" foreground="#9b9b9b"/>
  <style name="Macro" foreground="#beb7ff"/>
  <style name="Label"/>
  <style name="Comment" foreground="#57a64a"/>
  <style name="Doxygen.Comment" foreground="#57a64a"/>
  <style name="Doxygen.Tag" foreground="#57a64a" bold="true"/>
  <style name="VisualWhitespace" foreground="#3b3b3b"/>
  <style name="QmlLocalId" italic="true"/>
  <style name="QmlExternalId" italic="true"/>
  <style name="QmlTypeId"/>
  <style name="QmlRootObjectProperty" italic="true"/>
  <style name="QmlScopeObjectProperty" italic="true"/>
  <style name="QmlExternalObjectProperty" italic="true"/>
  <style name="JsScopeVar" italic="true"/>
  <style name="JsImportVar" italic="true"/>
  <style name="JsGlobalVar" italic="true"/>
  <style name="QmlStateName" italic="true"/>
  <style name="Binding"/>
  <style name="DisabledCode"/>
  <style name="AddedLine"/>
  <style name="RemovedLine"/>
  <style name="DiffFile"/>
  <style name="DiffLocation"/>
  <style name="DiffFileLine"/>
  <style name="DiffContextLine"/>
  <style name="DiffSourceLine"/>
  <style name="DiffSourceChar"/>
  <style name="DiffDestLine"/>
  <style name="DiffDestChar"/>
  <style name="LogChangeLine" foreground="#c00000"/>
  <style name="LogAuthorName" foreground="#007af4"/>
  <style name="LogCommitDate" foreground="#006600"/>
  <style name="LogCommitHash" foreground="#ff0000"/>
  <style name="LogCommitSubject"/>
  <style name="LogDecoration" foreground="#ff00ff"/>
  <style name="Warning" underlineColor="#ffbe00"/>
  <style name="WarningContext" underlineColor="#ffbe00"/>
  <style name="Error" underlineColor="#ff0000" underlineStyle="SingleUnderline"/>
  <style name="ErrorContext" underlineColor="#ff0000" underlineStyle="DotLine"/>
  <style name="Declaration"/>
  <style name="FunctionDefinition" foreground="#dcdcaa"/>
  <style name="OutputArgument" italic="true"/>
  <style name="StaticMember"/>
  <style name="CocoCodeAdded"/>
  <style name="CocoPartiallyCovered" foreground="#808000"/>
  <style name="CocoNotCovered" foreground="#ff0000"/>
  <style name="CocoFullyCovered" foreground="#00ff00"/>
  <style name="CocoManuallyValidated" foreground="#0000ff"/>
  <style name="CocoDeadCode" foreground="#ff00ff"/>
  <style name="CocoExecutionCountTooLow" foreground="#ff0000"/>
  <style name="CocoNotCoveredInfo" foreground="#ff0000"/>
  <style name="CocoCoveredInfo" foreground="#00ff00"/>
  <style name="CocoManuallyValidatedInfo" foreground="#0000ff"/>
  <style name="LastStyleSentinel"/>
</style-scheme>
```

* **СУБД: SQLite, SQLite Manager**

```sh
apt install sqlite3 sqlitebrowser -y
```

* **Редактор md-файлов: GhostWriter**

```sh
apt install ghostwriter -y
```

* **Терминал: Konsole**

```sh
apt install konsole -y
```

* **GUI-текстовый редактор: Pluma**

```sh
apt install pluma -y
```

---

### 4) Графика, видео, аудио

* **Видеоплеер: GNOME Videos**

```sh
apt install totem -y
```

* **Приложение для просмотра изображений: Eye of MATE**

```sh
apt install eom -y
```

* **Аудиоплеер: Audacious**

```sh
apt install audacious -y
```

* **Простой редактор растровых изображений: KolourPaint**

```sh
apt install kolourpaint -y
```

* **Продвинутый редактор растровых изображений: Gimp**

```sh
apt install gimp -y
```

---

### 5) Офисные программы

* **Комплект офисных программ: Libre Office**

```sh
apt install libreoffice -y
```




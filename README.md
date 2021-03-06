# Admin
Админские заметки

## Установка дефолтного языка при вводе с клавы на английский.

```powershell
Set-WinUserLanguageList -LanguageList en-US,ru -Force
```

После команды надо ещё скопировать настройки на всх юзеров:
`Win + R` → `control.exe` → `Просмотр: Категория` → `Мелкие значки` → `Региональные стандарты` → `вкладка «Дополнительно»` → `«Копировать параметры»`

## Простое управление пользователями

```cmd
control userpasswords2
```
## Кнопка питания переводит в сон

```cmd
POWERCFG -SETACVALUEINDEX scheme_balanced 4f971e89-eebd-4455-a8de-9e59040e7347 7648efa3-dd9c-4e3e-b566-50f929386280 001
```

## Установка chocolatey
```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```
Или скачать: https://chocolatey.org/install.ps1

```cmd
choco install chocolateygui -y
choco install git -y
choco install jdk11 -y
choco install 7zip -y
choco install cpu-z -y
choco install everything -y
choco install sysinternals -y
choco install smartgit -y
choco install telegram -y
choco install keypirinha -y
choco install totalcommander -y
choco install sublimetext3 -y
choco install putty -y
choco install jpegview -y
```

## Создаём ключик для гита
```cmd
ssh-keygen -t rsa -C "leukinrs@gmail.com" -b 4096
type %userprofile%\.ssh\id_rsa.pub | clip
```

Тест:
```cmd
ssh -T git@github.com
```

## Конфигурация гита
```cmd
git config --global core.autocrlf input
```

Чтобы работал SmartGit надо добавить в начало `%userprofile%\gitconfig`:
```config
[credential]
    helper=
```
**Перезапустить SmartGit!**

Полный `%userprofile%\gitconfig`:
```config
[credential]
    helper=
[user]
	name = Leukin Roman
	email = leukinrs@gmail.com
[gc]
	autoDetach = false
[core]
	autocrlf = input
[pull]
	rebase = true
```

## Исключения антивируса
```powershell
Add-MpPreference -ExclusionPath C:\home, "$env:USERPROFILE\.android", "$env:USERPROFILE\.AndroidStudio3.4", "$env:USERPROFILE\.gradle" -ExclusionProcess studio64.exe
```

## Keypirinha
```config
[app]
launch_at_startup = yes
hotkey_run = Alt+Space

[gui]
hide_on_focus_lost = yes
theme = MediumLayout
retain_last_search = yes

[external]
file_explorer = "C:\Program Files\totalcmd\TOTALCMD64.EXE" /O /S /L={{file}}
```

[Поправленный Bookmarks плагин (v2.23)](https://github.com/romansl/Admin/raw/master/Keypirinha/Bookmarks.keypirinha-package)

Заменена строка `\providers\chrome.py:69` на
```python
fh = open(bookmarks_file, encoding='utf-8')
```

## JPEGView

Save [JPEGView.ini](https://github.com/romansl/Admin/blob/master/JPEGView.ini) to: `c:\Users\Roman\AppData\Roaming\JPEGView\JPEGView.ini`

## Totalcmd

Unpack [GHISLER.zip](https://github.com/romansl/Admin/blob/master/GHISLER.ZIP) to `c:\Users\Roman\AppData\Roaming\GHISLER\`

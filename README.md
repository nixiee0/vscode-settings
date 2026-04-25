# VS Code Settings Backup

Бэкап моих настроек Visual Studio Code.

В репозитории лежат:

- `settings.json` — основные настройки VS Code
- `keybindings.json` — горячие клавиши
- `extensions.txt` — список установленных расширений

---

## Навигация

- [Установка на Windows через Git Bash](#windows-git-bash)
- [Установка на Linux](#linux-install)
- [Пустые поля в `settings.json`](#empty-settings-fields)

---

## Что нужно установить заранее

Перед восстановлением настроек нужно установить:

- Visual Studio Code
- Git
- JetBrains Mono
- Git Bash — только для Windows

Также команда `code` должна работать в терминале:

```bash
code --version
```

---

<a id="windows-git-bash"></a>

# Установка на Windows через Git Bash

```bash
git clone https://github.com/nixiee0/vscode-settings.git
cd vscode-settings

USER_DIR="$(cygpath "$APPDATA")/Code/User"

mkdir -p "$USER_DIR"

cp settings.json "$USER_DIR/settings.json"
cp keybindings.json "$USER_DIR/keybindings.json"

while IFS= read -r extension || [ -n "$extension" ]; do
    extension="${extension%$'\r'}"

    if [ -n "$extension" ]; then
        code --install-extension "$extension"
    fi
done < extensions.txt
```

---

<a id="linux-install"></a>

# Установка на Linux

```bash
git clone https://github.com/nixiee0/vscode-settings.git
cd vscode-settings

USER_DIR="$HOME/.config/Code/User"

mkdir -p "$USER_DIR"

cp settings.json "$USER_DIR/settings.json"
cp keybindings.json "$USER_DIR/keybindings.json"

while IFS= read -r extension || [ -n "$extension" ]; do
    extension="${extension%$'\r'}"

    if [ -n "$extension" ]; then
        code --install-extension "$extension"
    fi
done < extensions.txt
```

---

<a id="empty-settings-fields"></a>

# Пустые поля в `settings.json`

Некоторые значения в `settings.json` специально оставлены пустыми, чтобы не хранить в репозитории личные данные, локальные пути и названия личных репозиториев.

## `nixieepulse.githubProfile.owner`

```json
"nixieepulse.githubProfile.owner": ""
```

GitHub username владельца репозитория.

Пример:

```json
"nixieepulse.githubProfile.owner": "your-github-username"
```

---

## `nixieepulse.githubProfile.repo`

```json
"nixieepulse.githubProfile.repo": ""
```

Название GitHub-репозитория, с которым будет работать расширение.

Пример:

```json
"nixieepulse.githubProfile.repo": "your-repository-name"
```

---

## `nixieepulse.githubProfile.branch`

```json
"nixieepulse.githubProfile.branch": ""
```

Название ветки репозитория.

Пример:

```json
"nixieepulse.githubProfile.branch": "main"
```

---

## `nixieepulse.githubProfile.readmePath`

```json
"nixieepulse.githubProfile.readmePath": ""
```

Путь к README-файлу внутри репозитория.

Пример:

```json
"nixieepulse.githubProfile.readmePath": "README.md"
```

---

## `nixieepulse.githubProfile.svgPath`

```json
"nixieepulse.githubProfile.svgPath": ""
```

Путь, куда будет сохраняться SVG-файл со статистикой.

Пример:

```json
"nixieepulse.githubProfile.svgPath": "assets/coding-activity.svg"
```

---

## `nixieepulse.githubProfile.iconFolderPath`

```json
"nixieepulse.githubProfile.iconFolderPath": ""
```

Локальный путь к папке с иконками.

Пример:

```json
"nixieepulse.githubProfile.iconFolderPath": "C:/Users/YourName/Pictures/icons"
```

---

## `background.fullscreen.images`

```json
"background.fullscreen": {
    "images": []
}
```

Список локальных картинок для фонового изображения VS Code.

Пример:

```json
"background.fullscreen": {
    "images": [
        "file:///C:/Path/To/Image/background.png"
    ]
}
```

Если фон не нужен, можно оставить пустым:

```json
"images": []
```

Так же можно использовать ссылки на изображение
```json
"images": [
  "https://hostname/online.jpg"
]
```

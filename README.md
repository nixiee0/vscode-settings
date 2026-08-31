# VS Code Settings Backup

Бэкап моих настроек Visual Studio Code.

В репозитории лежат:

- `settings.json` — основные настройки VS Code
- `keybindings.json` — горячие клавиши
- `extensions.txt` — список установленных расширений

---

BG Примеры:

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

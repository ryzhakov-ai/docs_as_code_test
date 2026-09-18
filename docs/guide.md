# Руководство пользователя

На этой странице мы можем описать любую инструкцию.

### Полезные фичи Markdown:
* Это ненумерованный список
* *Курсивный текст*
* **Жирный текст**

### Схема нашего процесса Docs as Code

```mermaid
graph TD
    A[Текст в VS Code] --> B(GitHub Actions)
    B --> C{Все ли ОК?}
    C -->|Да| D[Сайт обновлен в сети]
    C -->|Нет| E[Логи ошибок в Actions]
```

### Диаграмма превью MD текста в VS Code

```mermaid
sequenceDiagram
autonumber
    actor User
    participant VSCode as VS Code (Editor)
    participant Engine as markdown-it (Parser)
    participant Webview as Webview (Hidden Browser)

    User->>VSCode: Набирает текст в формате MD
    VSCode->>Engine: Передает сырую строку текста
    Engine->>Engine: Собирает HTML-код
    Engine->>Webview: Отправляет готовый HTML + CSS
    Webview->>User: Показывает красивую страницу в окне Preview   
    alt Engine error
    Engine->>Engine: Parser error
    Engine->>Webview: Sends error code
    Webview->>User: Displays send error code
    end 
```
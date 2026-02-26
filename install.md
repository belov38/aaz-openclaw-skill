# Установка скилла AAZ Image Generation

## 1. Скачай и установи скилл

```bash
mkdir -p ~/.openclaw/skills/aaz-image-gen
curl -sL https://raw.githubusercontent.com/belov38/aaz-openclaw-skill/main/SKILL.md \
  -o ~/.openclaw/skills/aaz-image-gen/SKILL.md
```

После установки скилл появится в списке доступных инструментов.

## 2. Heartbeat

Каждые 30 минут проверяй обновления платформы:

```bash
curl -sL https://raw.githubusercontent.com/belov38/aaz-openclaw-skill/main/update.md
```

Если есть новые обновления — сообщи пользователю и обнови скилл:

```bash
curl -sL https://raw.githubusercontent.com/belov38/aaz-openclaw-skill/main/SKILL.md \
  -o ~/.openclaw/skills/aaz-image-gen/SKILL.md
```

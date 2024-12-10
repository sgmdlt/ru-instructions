# Установка пакетного менеджера uv

Пакетный менеджер uv используется для упраления проектами на Python.

## Используя скрипт установки

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Если в вашей системе не установлен `curl`, то можно использовать `wget`

```bash
wget -qO- https://astral.sh/uv/install.sh | sh
```

## Используя менеджер пакетов

### PyPI

`uv` дополнительно выложен на индексе PyPI, и его можно установить, используя `pipx`

```bash
pipx install uv
```

### Homebrew

Пользователи MacOS также могут поставить через Homebrew

```bash
brew install uv
```

# Миграция с poetry проекта

Если вы ранее использовали для проекта `poetry`, то чтобы перейти на `uv` выполните следующие шаги:

1. Сохраните содержимое `pyproject.toml` в другой файл или просто переименуйте его, например, в `pyproject.toml.poetry`
2. Заново инициализируйте проект командой `uv init`. Если нужно, удалите сперва `.venv`. Также удалите все ненужные файлы, что создаст `uv`, например `hello.py`
3. Скопируйте описание проекта и прочие метаданные из `pyproject.toml.poetry` в новый `pyproject.toml`
4. Теперь поставьте все зависимости из `pyproject.toml.poetry` командой `uv add`. Зависимости можно указывать подряд, например `uv add flask pytest`
5. Не забудьте в конце исправить все команды, что используют `poetry` на использование `uv`
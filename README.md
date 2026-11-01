# Ansible Playbook

Репозиторий с главным плейбуком для развертывания ClickHouse, Vector и LightHouse.

## Зависимости

Перед запуском необходимо скачать роли, описанные в requirements.yml:
```bash
ansible-galaxy install -r requirements.yml -p roles
```

## Использование

Запуск плейбука:
```bash
ansible-playbook -i inventory.ini site.yml
```

## Переменные

В плейбуке переопределяется переменная lighthouse_archive_url для роли lighthouse. Скачивание архива делегируется на хост-контроллер (delegate_to: localhost), так как целевые узлы могут не иметь прямого доступа к GitHub.
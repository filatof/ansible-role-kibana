# Ansible Role: Kibana

[![CI](https://github.com/geerlingguy/ansible-role-kibana/actions/workflows/ci.yml/badge.svg)](https://github.com/geerlingguy/ansible-role-kibana/actions/workflows/ci.yml)

Роль Ansible, которая устанавливает Kibana в RedHat/CentOS или Debian/Ubuntu. Для Ubuntu скачивает и устанавливает deb пакет из Yandex

## Requirements

Нет.

## Role Variables

Доступные переменные перечислены ниже вместе со значениями по умолчанию (see `defaults/main.yml`):

    kibana_version: "8.x"

Версия kibana для установки.

    kibana_package: kibana
    kibana_package_state: present

Конкретный пакет, который необходимо установить. Вы можете указать версию пакета, используя правильный синтаксис для вашей платформы и менеджера пакетов, изменив название пакета. Вы также можете управлять состоянием пакета (например, present, absent, или latest).

    kibana_service_state: started
    kibana_service_enabled: true

Определяет, будет ли kibana служба запущена и включена при загрузке системы.

    kibana_config_template: kibana.yml.j2
    kibana_config_file_path: /etc/kibana/kibana.yml

Шаблон, который будет использоваться для файла конфигурации Kibana, и путь, по которому будет записан файл конфигурации.

    kibana_server_port: 5601
    kibana_server_host: "0.0.0.0"

Полное доменное имя или IP-адрес и порт, которые должна использовать Kibana.

    kibana_elasticsearch_url: "http://localhost:9200"

URL-адрес (включая порт), по которому Kibana будет подключаться к Elasticsearch.

    kibana_elasticsearch_username: ""
    kibana_elasticsearch_password: ""

Если Elasticsearch защищён базовой аутентификацией HTTP, укажите имя пользователя и пароль, чтобы Kibana могла подключиться.



## Dependencies

Нет.

## Example Playbook

    - hosts: kibana
      roles:
        - geerlingguy.kibana

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/).

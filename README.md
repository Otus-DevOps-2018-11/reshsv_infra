# reshsv_infra
reshsv Infra repository

LAB #7 Подготовка образа ВМ для приложения REDDIT
Основные задания выполнены, дополнительные не выполнялись.

Подготовлен шаблон ubuntu16.json с дополнительными параметрами описания, диска, сети.
Часть переменных берется из файла variables.json, в коммит добавлен пример этого файла с фэйковыми переменными variables.json.example

LAB #6 Деплой тестового приложения
Выполнено успешно.

testapp_IP = 35.195.40.74

testapp_port = 9292


LAB #5

bastion_IP = 35.210.125.213

someinternalhost_IP = 10.132.0.4

Развернул две ВМ в GCP, одна из них с внешним IP.
Сначала настроил подключение к внутренней ВМ через SSH Jump host.
После настроил VPN подключение.
Всё получилось, проблем не возникло.

Доп. Задание:
Подключение к хосту someinternalhost в одну строку 
ssh -i appuser -A -J 35.210.125.213 10.132.0.3

Подключение по alias.

.ssh$ cat config 
host someinternalhost
	hostname 10.132.0.3
	proxyjump bastion

host bastion
	hostname 35.210.125.213
	identityfile ~/.ssh/appuser


reshetnikov@vm-lab:~/.ssh$ ssh someinternalhost
Welcome to Ubuntu 16.04.5 LTS (GNU/Linux 4.15.0-1025-gcp x86_64)




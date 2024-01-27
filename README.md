# DevOps

Учебное пособие по дисциплине "Архитектура ИС".

## Лекции
Презентации:

* **Лекция 1**. [Введение в DevOps. Системы виртуализации и облачные решения](Лекции/Лекция1/АРЭПО-Л1-П.pdf) 
* **Лекция 2**. [Контейнеризация + БД](Лекции/Лекция2/L2.pptx) 
* **Лекция 3**. [Контроль версий, Git, CI/CD](Лекции/Лекция3/Git_dlya_samykh_malenkikh.pdf) 
* **Лекция 4**. [Масштабируемость и отказоустойчивость + docker compose](Лекции/Лекция4/Лекция_4_Масштабируемость_и_отказоустойчивость.pdf) 
* **Лекция 5**. [Мониторинг, логирование и оповещение событий](Лекции/Лекция5/L5.pptx) 
ELK и тд
* **Лекция 6**. [Конфигурационное управление. Ansible, Terraform](Лекции/Лекция6/Лекция_6_ИТ_инфраструктура_Конфигурационное_управление.pdf) 
* **Лекция 7**. [Kubernetes](Лекции/Лекция7/Kubernetes_L7.pptx)
* **Лекция 8**. [Облачная инфраструктура в общем. BASIS](Лекции/Лекция8/L8.pptx) 
* **Лекция 9**. [DevOps для задач  обработки данных и машинного обучения](Лекции/Лекция9/mlops.pdf) 
* **Лекция 10**. [Паттерны использования Kubernetes](Лекции/Лекция10/L10.pptx) 
* **Лекция 11**. [Infrastructure as Code. Terraform](Лекции/Лекция11/Лекция_Terraform.pdf) 
* **Лекция 12**. [Раздел "Базы данных". Часть 1](Лекции/Лекция12/АРЭ%20-%20раздел%20БД%20лекция%201.pdf) 
* **Лекция 13**. [Раздел "Базы данных". Часть 2](Лекции/Лекция13/АРЭ%20-%20раздел%20БД%20лекция%202.pdf) 
* **Лекция 15**. [Раздел "Обработка больших данных". Часть 2. Apache Spark](Лекции/Лекция15/Spark_1.pdf) 

Дополнительные ссылки:

* [Думай как SRE](Лекции/Лекция1/Думай%20как%20SRE%20(simple).pdf)

## Экзамен

* [Экзаменационные вопросы](exam.md)

## Практические занятия

### Занятие 1 (Лаб 1). Настройка виртуальной машины Linux


[Лабораторная работа 1](Лабораторные/L1.pdf):

* Знакомство с Ubuntu 20.04.
* Поставить docker, через bash, сетевые интерфейсы.

### Занятие 2 (РК 1). Практические навыки работы с Docker - контейнер с PostgreSQL


[Лабораторная работа 2](Лабораторные работы/L2.pdf):

* Первая половина:
  * Работа с PostgreSQL/MySQL
  * Docker Volume
* Вторая половина:
  * Php My Admin/Adminer во втором контейнере

### Занятие 3 (Лаб 2). Балансировка + docker-compose


[Задачи](Лабы/Лаб3/README.MD):

* Первая половина:
  * HTML страничка
  * Балансировщик nginx (HAProxy)
* Вторая половина:
  * веб-сервис с БД

Итог 4 взаимосвязанных контейнера в docker-compose:

1. субд postgresql, проверяем как работают volumes
2. микросервис-1, только отдает html страничку
3. микросервис-2, обращатеся в БД, сетевое взаимодействие
4. балансировщик (haproxy/nginx) с port-forwarding-ом, будет перенаправлять запросы на другие контейнеры

### Занятие 4 (ДЗ 1). Настройка CI/CD в GitLab


[Задачи](Лабы/Лаб4/README.md):

* Первая половина:
  * Создание репозитория GitLab/GitHub
  * Управление репозиторием с помощью команд git
* Вторая половина:
  * Добавление в репозиторий проекта с юнит-тестами
  * Настройка Pipeline в GitLab/GitHub:
    * Проверка качества кода
    * Активация юнит-тестов
    * Сборка проекта в бинарник и публикация в артефакты Releases
  * Настройка Runner-ов
  * Активация настроенных Pipeline

### Занятие 5 (Лаб 3). Мониторинг: Prometehus + Grafana + Alertmanager

Задачи:

* Установили Prometheus + Grafana + Alertmanager.
* Настроили мониторинг, написали конфиги.
* Если плохо - использовать готовый образ

### Занятие 6 (ДЗ 2). Ansible, Playbook


[Задачи](Лабы/Лаб6/README.MD):

* Создаем виртуалку поменьше чтобы мониторить из первой виртуалки
* Пишем playbook, который автоматизирует развертывание виртуалки
* В конце выключаем 2 имеющихся виртуалки

### Занятие 7 (Лаб 4). Развертывание кластера Kubernetes


[Задачи](Лабы/Лаб7/README.md):

* minikube - 8 RAM достаточно. Из коробки не заработает. Для тех, у кого мощные машины - у большинства, дадим в кластере
* В отдельной виртуалке кубер. Много манифестов написать

Итог - все контейнеры поднять в кубере и замониторить

### Занятие 8 (РК 2). Индивидуальное задание

[Задачи](Лабы/Лаб8/README.md):

* Развернуть свой проект из 5 лабораторной курса РИП в контейнеры Docker Compose: Django + ORM + таблица в MySQL (без AJAX, SPA и React)

#### Задание на +1 балл

По вашей дипломной работе необходимо создать контейнеры Docker Compose, без Kubernetes. Например: React, Django REST или что-то свое.

## Практикум в BASIS

По ДЗ BASIS от Ростелеком: Helm, и тд - только для сертификата Ростелекома

## Полезные ссылки

1. [Открытая вечерняя школа. Kubernetes для разработчиков (Осень 2021)](https://www.youtube.com/playlist?list=PL8D2P0ruohOBSA_CDqJLflJ8FLJNe26K-)
2. [Микрослужбы .NET: Архитектура контейнерных приложений .NET](https://learn.microsoft.com/ru-ru/dotnet/architecture/microservices/)
3. Обсуждение книги Мартина Клеппмана "Designing Data-Intensive Applications" в формате [подкастов Tinkoff Reader Club "Code of Architecture"](https://www.youtube.com/playlist?list=PLLrf_044z4JpIlGkIDn6sdBstsTkKMXU6)

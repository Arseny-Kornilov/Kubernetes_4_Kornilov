# Домашнее задание "Настройка приложений и управление доступом в Kubernetes"
## Задание 1: Работа с ConfigMaps
### Задача
Развернуть приложение (nginx + multitool), решить проблему конфигурации через ConfigMap и подключить веб-страницу.

### Шаги выполнения
- Создать Deployment с двумя контейнерами
   - nginx
   - multitool
- Подключить веб-страницу через ConfigMap
- Проверить доступность
#### Что сдать на проверку
- Манифесты:
   - deployment.yaml
     ##### ОТВЕТ:
     <img width="1083" height="512" alt="image" src="https://github.com/user-attachments/assets/c129e9f9-b1cd-4335-9b83-dba7cd7fa336" />
     <img width="598" height="253" alt="image" src="https://github.com/user-attachments/assets/7009c028-b1d9-482a-83ce-dd606b09a760" />
   - configmap-web.yaml
     ##### ОТВЕТ:
     <img width="824" height="404" alt="image" src="https://github.com/user-attachments/assets/74e4b39e-abb2-4b3a-a2a1-2f10d89fc284" />

- Скриншот вывода curl или браузера
##### ОТВЕТ:
<img width="525" height="241" alt="image" src="https://github.com/user-attachments/assets/2e968fa0-39e6-40f7-80ef-77cb663969cd" />

## Задание 2: Настройка HTTPS с Secrets
### Задача
Развернуть приложение с доступом по HTTPS, используя самоподписанный сертификат.

### Шаги выполнения
 - Сгенерировать SSL-сертификат
 - openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
    -keyout tls.key -out tls.crt -subj "/CN=myapp.example.com"
 - Создать Secret
 - Настроить Ingress
 - Проверить HTTPS-доступ
#### Что сдать на проверку
 - Манифесты:
   - ingress-tls.yaml
     ##### ОТВЕТ:
     <img width="893" height="471" alt="image" src="https://github.com/user-attachments/assets/b83fe27f-5793-4cc2-81bb-c8e0fcc5f5ca" />
 - Скриншот вывода curl -k
   ##### ОТВЕТ:
   <img width="675" height="203" alt="image" src="https://github.com/user-attachments/assets/9efa5355-64bf-483e-a4db-e37e0a7aaa0f" />

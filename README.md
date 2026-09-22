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

## Задание 3: Настройка RBAC
### Задача
Создать пользователя с ограниченными правами (только просмотр логов и описания подов).

### Шаги выполнения
 - Включите RBAC в microk8s
    - microk8s enable rbac
 - Создать SSL-сертификат для пользователя
    - openssl genrsa -out developer.key 2048
    - openssl req -new -key developer.key -out developer.csr -subj "/CN={ИМЯ ПОЛЬЗОВАТЕЛЯ}"
    - openssl x509 -req -in developer.csr -CA {CA серт вашего кластера} -CAkey {CA ключ вашего кластера} -CAcreateserial -out developer.crt -days 365
 - Создать Role (только просмотр логов и описания подов) и RoleBinding
 - Проверить доступ
#### Что сдать на проверку
 - Манифесты:
    - role-pod-reader.yaml
      ##### ОТВЕТ:
      <img width="819" height="427" alt="image" src="https://github.com/user-attachments/assets/0d287a52-061f-46bf-9975-2194755566dd" />

    - rolebinding-developer.yaml
      ##### ОТВЕТ:
      <img width="825" height="377" alt="image" src="https://github.com/user-attachments/assets/564d66d7-ba54-45b4-b592-2d69041e7b8d" />

 - Команды генерации сертификатов
    ##### ОТВЕТ:
   <img width="685" height="347" alt="image" src="https://github.com/user-attachments/assets/fca25b6d-6310-464a-87e1-135c42c010ea" />

 - Скриншот проверки прав (kubectl get pods --as=developer)
   <img width="668" height="253" alt="image" src="https://github.com/user-attachments/assets/5e4e226f-3818-4d6f-a113-8ade030ebe18" />

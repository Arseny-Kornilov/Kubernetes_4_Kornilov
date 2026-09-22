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
- Что сдать на проверку
- Манифесты:
   - deployment.yaml
     #### ОТВЕТ:
     <img width="1083" height="512" alt="image" src="https://github.com/user-attachments/assets/c129e9f9-b1cd-4335-9b83-dba7cd7fa336" />
     <img width="598" height="253" alt="image" src="https://github.com/user-attachments/assets/7009c028-b1d9-482a-83ce-dd606b09a760" />
   - configmap-web.yaml
     #### ОТВЕТ:
     <img width="824" height="404" alt="image" src="https://github.com/user-attachments/assets/74e4b39e-abb2-4b3a-a2a1-2f10d89fc284" />

- Скриншот вывода curl или браузера
#### ОТВЕТ:
<img width="1279" height="523" alt="image" src="https://github.com/user-attachments/assets/c1ce75df-6e5d-4e78-8e59-45f3d1bdf1ca" />

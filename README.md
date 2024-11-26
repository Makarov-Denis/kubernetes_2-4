# Домашнее задание к занятию "`Управление доступом`" - `Макаров Денис`

---

## Задание 1. Создайте конфигурацию для подключения пользователя


### 1. Создайте и подпишите SSL-сертификат для подключения к кластеру.

Создадим сертификаты для подключения к кластеру представлено на скриншоте ниже:

![gen rsa](https://github.com/user-attachments/assets/61c7f3bc-b1f7-433f-907a-21382f58cbf2)

### 2. Настройте конфигурационный файл kubectl для подключения.

Перенесем на машину с которой будем подключаться и настроим конфигурационный файл. Добавим юзера, добавим контекст и проверим конфигурацию представлено на скриншотах ниже:

![cert](https://github.com/user-attachments/assets/eaa15996-4eae-4e3d-928f-ed63dc233788)

![nodes](https://github.com/user-attachments/assets/cd51b95b-6634-4e2a-bd08-775f2d16f427)

![config](https://github.com/user-attachments/assets/8e597268-c363-47a0-b6d4-560bbba8c3a3)


### 3. Создайте роли и все необходимые настройки для пользователя.

Выполнение задания представлено на скриншотах ниже:

![role](https://github.com/user-attachments/assets/2f6232ba-76ea-451b-8f49-2b3795928f0f)

![role-bulding](https://github.com/user-attachments/assets/da1551b5-057a-4ba7-9496-b2cf481811d0)

![apply role](https://github.com/user-attachments/assets/db336000-9a2e-4336-a43c-5b029d5b184b)

### 4. Предусмотрите права пользователя. Пользователь может просматривать логи подов и их конфигурацию (`kubectl logs pod <pod_id>`, `kubectl describe pod <pod_id>`).

![describe](https://github.com/user-attachments/assets/7e762c3c-690e-4509-a0d6-6ac08997f5d1)

На кластере присутствует pod:

![get nodes](https://github.com/user-attachments/assets/7327fd7a-ddb5-4271-b3d0-03383d75390d)

Переключимся на пользователя и проверим pod:

![context](https://github.com/user-attachments/assets/bde91cdf-d732-43af-94c4-d9149f84b7c7)

Запустить не удалось, выяснилось, что для выполнения команд ```logs ``` и ```describe``` пользователю требуется добавление в роль verbs: ["get"] представлено на скриншоте ниже:

![izm role](https://github.com/user-attachments/assets/21a5f792-4b2e-4d86-a3bc-d6b15a819471)

![logs_pods](https://github.com/user-attachments/assets/a084c27f-a086-4737-9a5b-684a00eedf0f)

Проверяем повторно:

![povtor](https://github.com/user-attachments/assets/e0018f91-fc66-49d3-922f-b5bc6f756f76)

![logs_multitool](https://github.com/user-attachments/assets/9ecfd9df-be89-4777-b9d9-9e99a8908ecb)

### 5. Предоставьте манифесты и скриншоты и/или вывод необходимых команд.

------

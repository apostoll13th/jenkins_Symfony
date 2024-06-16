# Инструкция по подготовке чистой ноды для приложения Symfony Demo

## Установка необходимых зависимостей

 Обновить список пакетов:
   ```bash
   sudo apt update
   ```

Установить PHP 8.2 и необходимые расширения:
```bash
sudo apt install php8.2 php8.2-cli php8.2-common php8.2-curl php8.2-intl php8.2-mbstring php8.2-xml php8.2-zip php8.2-sqlite3
```  

Установить Git:
```bash
sudo apt install git
```

Создать нового пользователя symfony:
```bash
sudo adduser symfony
```  

Создать директорию для приложения:
```bash
sudo mkdir -p /var/www/symfony_demo  
```  
Создать директорию для приложения:
```bash
sudo chown symfony:symfony /var/www/symfony_demo
sudo chmod 755 /var/www/symfony_demo
```
Назначить права на директорию:
```bash
sudo chown symfony:symfony /var/www/symfony_demo
sudo chmod 755 /var/www/symfony_demo
```

Nginx:
```bash
sudo apt install nginx
```
Настроить конфигурацию веб-сервера для директории /var/www/symfony_demo/public.  
Для Nginx: создать новый файл конфигурации в /etc/nginx/sites-available и сделать символическую ссылку в /etc/nginx/sites-enabled.

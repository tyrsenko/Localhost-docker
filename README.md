## Localhost-docker
#### 1. Устанавливаем docker
 * curl -fsSL get.docker.com -o get-docker.sh
 * sh get-docker.sh 

#### 2. Добавляем пользователя user в группу docker   
sudo usermod -aG docker user

#### 3. Создаем Dockerfile (вложенный файл)

#### 4. Cоздаем конфигурационные файлы для добавления в образ:

* HTML страница LH1 (вложенный файл)
* HTML страница LH2 (вложенный файл)
* конфиг. файл LH1 (вложенный файл)
* конфиг. файл LH2 (вложенный файл)


#### 5. Создаем образ
docker build -t nginx:LH ~/dockerfile/

#### 6. Запускаем контейнер
docker run -d -P --name=nginx nginx:LH

#### 7. Добавляем LH1.com [www.LH1.com] и LH2.com [www.LH2.com] в конф.файл etc/hosts на локальном компьютере
 * 172.17.0.2      LH1.com www.LH1.com
 * 172.17.0.2      LH2.com www.LH2.com

#### 8. Загружаем страницы LH1.com и LH2.com для проверки
  * curl http://LH1.com
  * curl http://LH2.com

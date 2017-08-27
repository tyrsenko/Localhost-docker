"# localhost-docker" 
## Localhost-docker
#### 1. Установка docker
curl -fsSL get.docker.com -o get-docker.sh
sh get-docker.sh 

#### 2. Добавляем пользователя user в группу docker   
sudo usermod -aG docker user

#### 3. Создаем Dockerfile

#### 4. Cоздаем конфигурационные файлы для добавления в образ:

* HTML страница LH1
* HTML страница LH2
* конфиг. файл LH1
* конфиг. файл LH2


#### 5. Создаем образ
docker build -t nginx:LH ~/dockerfile/

#### 6. Запускаем контейнер
docker run -d -P --name=nginx nginx:LH

#### 7. Добавляем LH1.com (www.LH1.com) и LH2.com (www.LH2.com) в конф.файл etc/hosts на локальном компьютере
172.17.0.2      LH1.com www.LH1.com
172.17.0.2      LH2.com www.LH2.com

#### 8. Загружаем страницы LH1.com и LH2.com для проверки
  curl (http://LH1.com)
  curl (http://LH2.com)

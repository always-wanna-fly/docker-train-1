# docker-train-1

docker run -d --name apache2-container -e TZ=UTC -p 8080:80 ubuntu/apache2:2.4-21.10_beta
docker run -d -v "/home/NIX/ivanitskyi/domain/home/docker train/docker_train_#1/mycode2:/var/www/html" -e TZ=UTC -p 8080:80 ubuntu/apache2:2.4-21.10_beta
/*
run - запустити контейнер, якщо він не встановленний знайти на https://hub.docker.com/, спулити і запустити
-d - запустити в фоновому режимі
-v "/home/NIX/ivanitskyi/domain/home/docker train/docker_train_#1/mycode2:/var/www/html - налаштування вольюмс для двосторонньої синхронізації папки(в данному випадку /home/NIX/ivanitskyi/domain/home/docker train/docker_train_#1/mycode2) з папкою проекта на сайті
--name apache2-container - дати ім'я apache2-container, по якому можна звертатись до контейнера
-e TZ=UTC - часовий пояс
-p 8080:80 - порт 
ubuntu/apache2:2.4-21.10_beta - назва контейнера на https://hub.docker.com/
*/
docker exec -it ubuntu/apache2:2.4-21.10_beta /bin/bash 

/*
Опція -it разом  /bin/bash дає доступ до виконання команд в терміналі всередині контейнера

ubuntu/apache2:2.4-21.10_beta - назва image

*/




docker stop $(docker ps -a -q)   # Зупинить всі встановленні контейнери
docker rm $(docker ps -a -q)     # Видалить всі встановленні контейнери

docker stop $(docker images -a -q)   # Зупинить всі встановленні образи
docker rmi $(docker images -a -q)    # Видалить всі встановленні образи

# otus-prof-project

Для начала создаём сеть

```bash
docker network create --subnet 172.20.0.0/16 --ip-range 172.20.240.0/24 otus-pro-net;
```

<details>
<summary> MySQL-Source </summary>

Запускаем докер с MySQL-Source
```bash
docker-compose -f docker-compose-1-MySQL-Source.yml up -d
```

Посмотреть логи
```bash
docker logs mysql-source
```

Посмотреть базы данных
```bash
docker exec -it mysql-source mysql -uroot -p'$0urcePa$$' -e "SHOW DATABASES;"
```

Останавливаем докер с MySQL-Source
```bash
docker-compose -f docker-compose-1-MySQL-Source.yml down
```
</details>


<details>
<summary> MySQL-Replica </summary>

Запускаем докер с MySQL-Replica
```bash
docker-compose -f docker-compose-2-MySQL-Replica.yml up -d
```

Посмотреть логи
```bash
docker logs mysql-replica
```

Посмотреть базы данных
```bash
docker exec -it mysql-replica mysql -uroot -p'replicaPa$$' -e "SHOW DATABASES;"
```

Останавливаем докер с MySQL-Replica
```bash
docker-compose -f docker-compose-2-MySQL-Replica.yml down
```
</details>



apt update && apt install mc git ansible sshpass -y
ansible-galaxy collection install community.docker
curl -fsSL https://get.docker.com | sudo sh
git clone https://github.com/shootnicks/otus-prof-project.git /opt/otus-prof-project
<!-- cd otus-prof-project/ansible/ -->
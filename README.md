# OdOO 17 Installation
<b> Docker Installation </b> <br>
1.Download Docker : https://www.docker.com/<br>
2.Install (Windows/Mac)<br>
3.Run Docker<br>

<b>OdOO 17 Installation </b> <br>
1. Install Database:<br>
	- docker run -d -e POSTGRES_USER=odoo -e POSTGRES_PASSWORD=odoo -e POSTGRES_DB=postgres --name=dberp16 postgres:16<br>
2. Install Odoo:<br>
  - docker run -p 8069:8069 --name isberp17 --link dberp16:db -t odoo:17<br>
3. Running Odoo:<br>
  - docker start dberp16<br>
  - docker start isberp17<br>
  - Buka Browser dan ketik http://localhost:8069<br>
4. Install PgAdmin:<br>
  - docker run -p 5050:80 -e "PGADMIN_DEFAULT_EMAIL=odoo" -e "PGADMIN_DEFAULT_PASSWORD=odoo" -d dpage/pgadmin4<br>
  - docker start pgadmin4<br>
  - Buka Browser dan ketik http://localhost:5050<br>
5.Docker Terminal: <br>
 - Masuk ke docker : 
      - docker exec -u root -it isberp17 /bin/bash
   - Copy new module:
      - docker cp <nama_module> isberp17:/mnt/extra-addons
      - docker stop isberp17
      - docker start isberp17
   - Perintah operasi pada docker:
      - Menampilkan list container pada docker dari terminal:
         -  docker container l --all 
      - Menghapus container exsisting:
         - docker rm <nama_container>
6. web.base.url OdOO = http://127.0.0.1:8069

<b>Download:<b>
   
1. https://apps.odoo.com/apps/modules/17.0/om_account_accountant/
   
2. https://odoo-community.org/shop/account-reconciliation-widget-8893#attr=14598
   
3. https://apps.odoo.com/apps/modules/17.0/stock_no_negative/ 


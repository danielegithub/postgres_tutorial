# Installazione in docker

```bash
docker pull postgres
docker pull dpage/pgadmin4
docker run -p 80:80 -e 'PGADMIN_DEFAULT_EMAIL=user@domain.com' -e 'PGADMIN_DEFAULT_PASSWORD=SuperSecret' -d dpage/pgadmin4
```
Adesso per connettersi al database bisogna 
> andare nell'immagine avviata di Postgres
- andare nel file inspect
  - se non ho cambiato nulla, si trova l'ip 172.17.0.X e la password.
  - Il nome utente è "postgres"
##  Se invece voglio impostare una password
 ```bash
docker run -d --name my_postgres -e POSTGRES_PASSWORD=mystrongpassword -p 5432:5432 -v postgres_data:/var/lib/postgresql/data postgres
```
# Configurazione del Volume (su Windows)
creo una cartella sul desktop (corretto)
-  Passaggi
-  - Posso anche non creare il volume
   - Creo una cartella in C:\Docker\pgdev
   - poi lancio il comando passandogli il path nuovo che ho creato
```bash
docker run --name pgdev -e POSTGRES_PASSWORD=Str0ngP@ssword -d -p 5432:5432 -v C:\Docker\pgdev:/var/lib/postgresql/data  postgres
```

creo una cartella sul desktop (errato
```bash
docker volume create --name postgres_data -d local --opt type=none --opt device=/c/Users/LA_CARTELLA_CHE_HO_CREATO --opt o=bind
docker run -d --name my_postgres -p 5432:5432 -v postgres_data:/var/lib/postgresql/data postgres
```

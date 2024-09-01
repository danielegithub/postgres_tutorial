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

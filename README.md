========================================
POSTGRESQL
========================================
default username - postgres
Maitinance database - postgres
data volume - /var/lib/postgresql/data/pgdata

========================================
PGADMIN
========================================

PGADMIN_DEFAULT_EMAIL
This is the email address used when setting up the initial administrator account to login to pgAdmin.
This variable is required and must be set at launch time.

PGADMIN_DEFAULT_PASSWORD
This is the password used when setting up the initial administrator account to login to pgAdmin.
This variable is required and must be set at launch time.

Examples
Run a simple container over port 80:

docker pull dpage/pgadmin4
docker run -p 80:80 \
-e "PGADMIN_DEFAULT_EMAIL=user@domain.com" \
-e "PGADMIN_DEFAULT_PASSWORD=SuperSecret" \
-d dpage/pgadmin4

Run a TLS secured container using a shared config/storage directory in /private/var/lib/pgadmin on the host:

docker pull dpage/pgadmin4
docker run -p 443:443 \
-v "/private/var/lib/pgadmin:/var/lib/pgadmin" \
-v "/path/to/certificate.cert:/certs/server.cert" \
-v "/path/to/certificate.key:/certs/server.key" \
-e "PGADMIN_DEFAULT_EMAIL=user@domain.com" \
-e "PGADMIN_DEFAULT_PASSWORD=SuperSecret" \
-e "PGADMIN_ENABLE_TLS=True" \
-d dpage/pgadmin4
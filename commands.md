## Issue With DB 
docker-compose up -d
docker-compose exec db psql -U odoo -d postgres -c "DROP DATABASE IF EXISTS odoo;"

## Install Pip packages
docker exec -u root -it container-id pip3 install pycryptodome --break-system-packages



## Full Refresh 
docker-compose down
docker-compose down -v
docker volume prune -f
docker system prune -a --volumes -f
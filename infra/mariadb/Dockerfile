# Use a imagem base do MariaDB
FROM mariadb:lts

# Configurações opcionais
ENV MYSQL_ROOT_PASSWORD=root
ENV MYSQL_DATABASE=php_sso

# Porta em que o MariaDB estará acessível
EXPOSE 3306

# Comando para iniciar o MariaDB quando o contêiner for iniciado
CMD ["mysqld"]

# steps to run listmonk on ec2.
    - sudo apt install postresql  docker docker-compose
    - sudo dpkg-reconfigure tzdata 
    - sudo usermod -a -G docker ubuntu (this is needed to avoid adding sudo to every docker command).
    - add domain to 127.0.0.1 to /etc/hosts. Dont delete the localhost one.
    - mkdir listmonk && sh -c "$(curl -fsSL https://raw.githubusercontent.com/knadh/listmonk/master/install-prod.sh)"

# instead of nginx we will use caddy because its way easier than managing nginx.
    - Change admin password in config.toml
    - Add caddy to docker-compose.yml
    - Add a file named 'Caddyfile' inside a folder called 'caddy' within the same directory that docker-compose.yml file resides in.
    - docker-compose up -d

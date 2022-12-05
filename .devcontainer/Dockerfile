FROM mcr.microsoft.com/devcontainers/php:0-8-bullseye

# Install MariaDB client
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y mariadb-client \ 
    && apt-get install -y vim \
    && apt-get clean -y && rm -rf /var/lib/apt/lists/*

# Create the space
# RUN mkdir -p /workspaces/phpDev/app

# PhpMyAdmin
# RUN curl https://files.phpmyadmin.net/phpMyAdmin/5.2.0/phpMyAdmin-5.2.0-english.tar.gz -o /opt/phpmyadmin.tar.gz
# RUN gzip -d /opt/phpmyadmin.tar.gz
# RUN tar -xf /opt/phpmyadmin.tar -C /opt/
# RUN mv /opt/phpMyAdmin-5.2.0-english /opt/phpmyadmin
# RUN chmod -R 755 /opt/phpmyadmin
# RUN rm /opt/phpmyadmin.tar

# RUN cp /opt/phpmyadmin/config.sample.inc.php /opt/phpmyadmin/config.inc.php

# Install php-mysql driver
RUN docker-php-ext-install mysqli pdo pdo_mysql

# Configure apache
# RUN sed -i '/Listen 8080/a Listen 8082' /etc/apache2/ports.conf
# RUN sed -i '/Listen 8082/a Listen 8083' /opt/phpmyadmin/config.inc.php

# RUN sed -i '/\$cfg\[\'Servers\'\]\[\$i\]\[\'AllowNoPassword\'\] = false\;/a \$cfg\[\'Servers\'\]\[\$i\]\[\'user\'\] = \'root\'\;' /opt/phpmyadmin/config.inc.php
# RUN sed -i '/\$cfg\[\'Servers\'\]\[\$i\]\[\'user\'\] = \'root\'\;/a \$cfg\[\'Servers\'\]\[\$i\]\[\'password\'\] = \'mariadb\'\;' /opt/phpmyadmin/config.inc.php
# RUN sed -i 's/\$cfg\[\'Servers\'\]\[\$i\]\[\'auth_type\'\] = \'cookie\'\;/\$cfg\[\'Servers\'\]\[\$i\]\[\'auth_type\'\] = \'config\'\;/g' /opt/phpmyadmin/config.inc.php
# RUN sed -i 's/\$cfg\[\'Servers\'\]\[\$i\]\[\'host\'\] = \'localhost\'\;/\$cfg\[\'Servers\'\]\[\$i\]\[\'host\'\] = \'db\'\;/g' /opt/phpmyadmin/config.inc.php


# COPY dev-site.conf /etc/apache2/sites-enabled
# COPY phpmyadmin.conf /etc/apache2/sites-enabled

EXPOSE 80
# EXPOSE 8080
# EXPOSE 8082
# EXPOSE 9003

# CMD apachectl -DFOREGROUND

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# [Optional] Uncomment this line to install global node packages.
# RUN su vscode -c "source /usr/local/share/nvm/nvm.sh && npm install -g <your-package-here>" 2>&1

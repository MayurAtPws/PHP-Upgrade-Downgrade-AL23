## Table of Contents

1. [Upgrading / Downgrading PHP](#upgrading-or-downgrading-php)
2. [List of PHP Versions](#list-all-php-versions-in-al23)
3. [Missing Packages in AMZ Repo](#not-found-in-amz-repo)

4. [Final Installation Command](#final-command)


**All Amazon Packages List :** https://docs.aws.amazon.com/linux/al2023/release-notes/all-packages-AL2023.3.html

### List all PHP Versions in AL23: 
- type 

            dnf install php

- Dont press enter, Press Tab twice to list all the Versions 
- Choose the required package from that 


**Required Version :** php8.2.9

**Syntax :** php{version}-{packagename}-{full-version.amz23.arch}

### **Example :** php8.2-gd-8.2.9-1.amzn2023.0.3.x86_64

**Required command :** 

        dnf install -y php php-gd php-pear php-devel libzip php-curl php-xml php-json php-mbstring php-zip php-pdo git unzip php-pgsql vim php-fpm httpd patch

## NOT Found in AMZ Repo

No match for argument: php8.2-**pear**-8.2.9-1.amzn2023.0.3.x86_64
No match for argument: php8.2-**curl**-8.2.9-1.amzn2023.0.3.x86_64
No match for argument: php8.2-**json**-8.2.9-1.amzn2023.0.3.x86_64


## Comes under php-common :
- php-curl 
- php-json

## fix 
    dnf install php-pear 

this will install the latest php-pear-1:1.10.13-2.amzn2023.0.4.noarch by default.


# Final Command 

### **full command :** 

        dnf install -y php8.2-8.2.9-1.amzn2023.0.3.x86_64 php8.2-common-8.2.9-1.amzn2023.0.3.x86_64 php8.2-gd-8.2.9-1.amzn2023.0.3.x86_64 php8.2-devel-8.2.9-1.amzn2023.0.3.x86_64 php8.2-xml-8.2.9-1.amzn2023.0.3.x86_64 php8.2-mbstring-8.2.9-1.amzn2023.0.3.x86_64 php8.2-zip-8.2.9-1.amzn2023.0.3.x86_64 php8.2-pdo-8.2.9-1.amzn2023.0.3.x86_64 php8.2-pgsql-8.2.9-1.amzn2023.0.3.x86_64 php8.2-fpm-8.2.9-1.amzn2023.0.3.x86_64 php-pear vim httpd patch libzip git unzip

### **short version :** 

        dnf install -y php8.2-{8.2.9-1.amzn2023.0.3.x86_64,common,gd,devel,xml,mbstring,zip,pdo,pgsql,fpm} php-pear vim httpd patch libzip git unzip

---
---


## Upgrading or Downgrading PHP 
- Uninstall the previous version

        dnf remove php8.1*
        (or)
        dnf remove php*

- Install the required version 

         dnf install php8.2-8.2.9-1.amzn2023.0.3.x86_64

- Restart the Httpd Server 

        systemctl restart httpd

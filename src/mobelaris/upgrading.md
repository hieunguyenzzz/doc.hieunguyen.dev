---
name: upgrading script
menu: Mobelaris
route: mobelaris/upgrading-script
---

# Upgrading script

```sh
# start cloning

cp ../mobelaris-dev.com/auth.json .
php composer.phar update -vvv
cp .backup/config.php app/etc
cp .backup/env.php app/etc
redis-cli flushall
php bin/magento setup:upgrade && php bin/magento setup:di:compile

#start upgrading
php bin/magento maintenance:enable &&
cp -R .magestore-gitlab/Source/server/app/code/Magestore/MigrateTool/ app/code/Magestore/MigrateTool/ && 
php bin/magento setup:upgrade && 
php bin/magento migrateTool:migrate before &&
cp .backup/exported-core-m2.3.5-p1.tar.gz . &&
tar -xf exported-core-m2.3.5-p1.tar.gz && 
rsync -avzh --delete exported-core-m2.3.5-p1/bin/ bin/ &&
rsync -avzh --delete exported-core-m2.3.5-p1/lib/ lib/ &&
rsync -avzh --delete exported-core-m2.3.5-p1/phpserver/ phpserver/  &&
rsync -avzh --delete exported-core-m2.3.5-p1/setup/ setup/ &&
rsync -avzh --delete exported-core-m2.3.5-p1/vendor/ vendor/ &&
cp exported-core-m2.3.5-p1/composer.json composer.json &&
cp exported-core-m2.3.5-p1/composer.lock composer.lock 

curl -sS https://getcomposer.org/installer -o composer-setup.php &&
/opt/php73/bin/php composer-setup.php --install-dir=./ --filename=composer1 --version=1.10.13 &&
/opt/php73/bin/php composer1 require google/cloud-translate=^1.9 --no-update &&
/opt/php73/bin/php composer1 require magento/composer-root-update-plugin=~1.0 --no-update &&
/opt/php73/bin/php composer1 update -vvv &&
rsync -avzh --delete .magestore-gitlab/Source/server/app/code/ ./app/code/ &&
rsync -avzh --delete .magestore-gitlab/Source/server/app/design/frontend/Mobelaris/Theme/ ./app/design/frontend/Mobelaris/Theme/ &&
rsync -avzh --delete .magestore-gitlab/Source/server/app/i18n/ ./app/i18n/ &&
rsync -avzh --delete .magestore-gitlab/Source/server/app/tests/ ./app/tests/ &&
rsync -avzh .magestore-gitlab/Source/server/app/etc/ ./app/etc/ &&

# redis flush

/opt/php73/bin/php bin/magento setup:upgrade && 
/opt/php73/bin/php bin/magento module:disable Mobelaris_ContainerOnTheWater Mobelaris_FilterByAvailability &&
/opt/php73/bin/php bin/magento migrateTool:migrate after && 
/opt/php73/bin/php bin/magento migrateTool:migrate mergeAttribute &&
/opt/php73/bin/php bin/magento migrateTool:migrate removeDuplicatedOptionLabel &&
/opt/php73/bin/php bin/magento migrateTool:migrate changeConfig &&
/opt/php73/bin/php bin/magento migrateTool:migrate warehouse2source &&
/opt/php73/bin/php bin/magento migrateTool:migrate sourceitemcsv &&
/opt/php73/bin/php bin/magento module:enable Mobelaris_ContainerOnTheWater Mobelaris_FilterByAvailability &&
/opt/php73/bin/php bin/magento setup:upgrade &&
/opt/php73/bin/php bin/magento setup:di:compile 
```

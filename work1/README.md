## Действовал по [методичке](https://github.com/dmitry-lyutenko/manual_kernel_update/blob/master/manual/manual.md)

1) Установка прикладного программного обеспечения

2) Загрузка репозитория, проверка совпадения чексуммы и версии образа

3) Сборка образа
```
packer build centos.json
```

## Выявленные проблемы при сборке и загрузке - 
Потребовалось переустановить Packer по официальной [документации](https://developer.hashicorp.com/packer/install?product_intent=packer)

 Необходимо было добавить в конфигурацию собираемого образа параметр в соответствии с [рекомендацией](https://github.com/hashicorp/packer-plugin-virtualbox/issues/104), без этого VMBox не мог достучаться до хоста, что бы прочитать файл кикстартера `vagrant.ks`. Текст ошибки привести не представляется возможным.

 Применение команды `packer fix` для устранения ошибки `iso_checksum_type`

 Загрузка образа в  Vagrant cloud выдает ошибку `Failed to create box fkdaedra/centos-7-5; Vagrant Cloud request failed`, образ появился на сайте, но, как понимаю, доступен для использования только мне. На всякий случай прилагается [ссылка](https://app.vagrantup.com/fkdaedra/boxes/centos-7.7.1908)



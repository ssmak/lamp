# LAMP

A LAMP stack development environment runs on a single container.
Given you a fast starting point with no installation cost.

##### Warning
It is a all-in-one image and target on development usage. It does not suppose to use in production. Be caution, many settings still keep in default, use in production may be in high risk.

## Components :white_check_mark:
| Name | Version | Remark |
| ---- | ------- | ------ |
| Ubuntu | 20.04.3 LTS | The base image |
| Apache | 2.4.41 | mod_fcgid/2.3.9 |
| | | OpenSSL/1.1.1f |
| | | MPM Name: event |
| MySQL | 8.0.26 | |
| PHP | 8.0.10 | PHP-FPM |
| Composer | 2.1.8 | A Dependency Manager for PHP |

## Links and Ports :bangbang:
| Link / Port | Remark |
| ---- | ------ |
| https://127.0.0.1/server-status | Apache server status |
| https://127.0.0.1/server-info | Apache server info. |
| https://127.0.0.1/fpm-status | PHP server status |
| https://127.0.0.1 | Web document root |
| https://127.0.0.1/phpinfo.php | PHP installation detail |
| /home/www | Volume - suppose you mount this point to your local directory | 
| 80, 443 | Http port, with SSL |
| 3306 | MySQL classic port. Default user (root/root) |
| 33060 | MySQL port for X Protocol |

## How to :question:
#### Before running..
Please refer to the folder structure (https://github.com/ssmak/lamp/tree/master/container_volume/www) which is aligned and mounted to the container /home/www. Don't forget to copy the SSL certificata for https.
Finally, there is 3 folders in the /www/default directory.
- /www/default/html
- /www/default/ssl
- /www/default/logs

#### After the folder structure was created..
##### Using Docker run
``` bash
docker run --name lamp -d -v d:/my_projects/lamp/container_volume/www:/home/www -p 80:80 -p 443:443 -p 3306:3306 -p 33060:33060 ssmak/lamp:0.0.1
```
_OR_
##### Using Docker Compose
``` bash
docker-compose up -d
```

__For Windows user__
Please don't forget to add the local directory path to Docker, so it can write.

## :heart: That's all. Enjoy! :heart:

## Buy me a :coffee:?
If you feel it is really help :+1:, please consider to buy me a :coffee:!<br />
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/T6T165VJF)


Thank you so much! :facepunch:
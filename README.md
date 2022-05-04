# aem-dispatcher
Basic Apache2 Dispatcher setup for AEM in Ubuntu

## Ubuntu 

1) add the 4 config files in your conf-available directory
2) add the dispatcher.so file into mods-available directory
3) make a symlink from inside the conf-enabled directory to the httpd.conf file inside conf-available
    
```sh
sudo ln -s /etc/apache2/conf-available/httpd.conf /etc/apache2/conf-enabled/httpd.conf
```

And  check the configuration

```sh
    apachectl configtest
```

It may thrown an error that the logs directory does not exist, in that case, add it and retest if the config is correct.

```sh
sudo mkdir /etc/apache2/logs
```

4) restart apache2 

```sh
    sudo systemctl restart apache2.service
```

5) check the status of apache2
```sh
	sudo systemctl status apache2.service
```

6) check the error log for errors
```sh
	cat /var/log/apache2/error.log
```

7) test if the dispatcher is up for vanilla aem install by visiting http://localhost/content/we-retail/us/en.html

Refer to the tree.txt file to check the setup of files in the correct directory.

## MAC

! Dispatcher is currently only supportde on x86 chips, M1 RISC-based chips are not supported (14/02/2022)

1) replace the default httpd.conf file with the one provided
2) add the dispatcher.so file into modules directory
3) make a symlink from inside the modules directory to the dispatcher.so file inside the sa;e directory
4) add the dispatcher.any and author_dispatcher.any to the conf directory
5) add the httpd-dispatcher.conf file to the extra directory
    
    sudo ln -s /etc/apache2/modules/dispatcher.so /etc/apache2/modules/mod_dispatcher.so

6) restart apache2 
	
	sudo apachectl restart

7) check the status of apache2

	sudo apachectl status

8) check the error log for errors
	
	cat /var/log/apache2/error.log

9) test if the dispatcher is up for vanilla aem install by visiting http://localhost/content/we-retail/us/en.html

Refer to the tree.txt file to check the setup of files in the correct directory.

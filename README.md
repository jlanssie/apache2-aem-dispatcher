# aem-dispatcher
Basic Apache2 Dispatcher setup for AEM in Ubuntu

## Ubuntu 

1) add the 4 config files in your conf-available directory
2) add the dispatcher.so file into mods-available directory
2) make a symlink from inside the conf-enabled directory to the httpd.conf file inside conf-available
    
    sudo ln -s /etc/apache2/conf-available/httpd.conf /etc/apache2/conf-enabled/httpd.conf

3) restart apache2 
	
	sudo systemctl restart apache2.service

4) check the status of apache2

	sudo systemctl status apache2.service

5) check the error log for errors
	
	cat /var/log/apache2/error.log

6) test if the dispatcher is up for vanilla aem install by visiting http://localhost/content/we-retail/us/en.html

## Mac
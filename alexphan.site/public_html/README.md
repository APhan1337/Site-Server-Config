# CSE 135

Alex Phan

A12998302

https://www.alexphan.site <br />
user: grader <br />
password: password

<u>Summary of changes to HTML file in DevTools after compression</u><br />
When I enabled compression on my HTML file, I noticed that it decreased the file size and the time it took to render the page.

<u>Summary of removing 'server' header</u><br />
I ```sudo apt-get install libapache2-mod-security2``` to install the ModSecurity module. I then added
```
<IfModule mod_security2.c>
    SecServerSignature "Supa Serva"
</IfModule>
```
to `/etc/apache2/sites-available/yourdomain.site-le-ssl.conf` file and then restarted the server.

<u>Analytics configuration</u>
I followed this [tutorial](https://artofadventuring.com/install-matomo-piwik-digitalocean/). I ran into an issue where I was getting
an mbstring extension mission. So I checked my PHP configuration, and found a [solution](https://stackoverflow.com/questions/30047169/phpmyadmin-error-the-mbstring-extension-is-missing-please-check-your-php-confi) on stackoverflow. I logged into MySQL with `mysql -u root -p`
and then created a database `CREATE DATABASE matomo;`. And then created a user `CREATE USER 'matomograder'@'localhost' IDENTIFIED BY 'password';`.
I then gave the user proper permissions. I went through the rest of the setup and copy and pasted a JavaScript snipet provided by matomo into my
`index.html`.
# Game Inventory

Welcome to the Web Browser-based Game Inventory repository! A list of games can be found on the website. There are exactly 34 games in total, with games of various genres ranging from  old school retro games, educational games, 8-bit platform games, browser-based games, indie games, GameJam projects, add-ons/maps/hacks/plugins for commercial games, libraries, frameworks, engines, you name it.

### Index

* [Getting Started](#getting-started)
* [Primary Reason](#primary-reason)
* [Software Used](#software-used)
* [Output](#output)
* [Deployment](#deployment)
* [Future Improvisation](#future-improvisation)
* [Support and Contributions](#support-and-contributions)
* [Source Code](#source-code)
* [Helpful Links](#helpful-links)
* [License](#license)

## Getting Started

## Primary Reason

The main advantages of digital distribution over the previously dominant retail distribution of video games include significantly reduced production, deployment, and storage costs. Compared to physically distributed games, digital games cannot be destroyed because they can be redownloaded from the distribution system.

Digital distribution also offers new structural possibilities for the whole video game industry, which, prior to the emergence of digital media as a relevant means of distribution, was usually built around the relationship of the video game developer, who produced the game, and the video game publisher, who financed and organized the distribution and sale. 

## Software Used
HTML \n
CSS
JAVASCRIPT



## Deployment

WordPress is a PHP, MySQL, and JavaScript based project, and uses Node for its JavaScript dependencies. A local development environment is available to quickly get up and running.

### 1. Install the Apache Web Server

There are multiple steps to install and configure Apache.

#### Installing SSH Client

Before installing Apache, you need to install the SSH client on your Linux computer. First, open Terminal by pressing Ctrl + Alt + T and type the following command to check for updates and upgrades:

```
sudo apt update && sudo apt upgrade
```

Then, install the SSH client by entering the command below:

```
sudo apt install openssh-server
```

Once installed, activate the SSH server with the following command:

```
sudo systemctl enable --now ssh
```

#### Installing Apache

The next step is to install the Apache web server. In the Terminal window, type the following command:

```
sudo apt-get install apache2
```

### 2. Install MySQL

MySQL will be the database management system for your web application. To install MySQL, enter the command below in the Terminal window:

```
sudo apt-get install mysql-server
```

### 3. Install PHP

Once completed, check if you have successfully installed the latest PHP version using the command below:

```
sudo apt-get install php
```

### 4. Make a Directory for Your Domain

After successfully installing the LAMP stack, you can set up the virtual host. First, you must create a specific directory for storing your website files.

Use the command cd to move from your active directory to the /var/www directory. Open Terminal and enter the following command:

```
cd /var/www
```

After that, create a directory using the command below:

```
sudo mkdir -p /var/www/domainname.com/
```

Next, change the file ownership and assign necessary permissions inside the /var/www/domainname.com directory using the following commands:

```
sudo chown -R $<your_username>:$<your_username> /var/www/domainname.com
sudo chmod -R 755 /var/www/domainname.com 
```

### 5. Create a Virtual Host File and Activate It

At this stage, we have successfully created a local website directory and a sample web page. The next step is to make the website accessible online. To do that, create a virtual host file inside the Apache default directory:

```
sudo nano /etc/apache2/sites-available/domainname.com.conf
```

Next, add the following lines of code inside the domainname.com.conf file:

```
<VirtualHost *:80>
    ServerAdmin admin@domainname.com
    ServerName domainname.com
    ServerAlias www.domainname.com
    DocumentRoot /var/www/domainname.com
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

After that, enable the virtual host configuration file using the a2ensite command:

```
sudo a2ensite domainname.com
```

Then, disable the default configuration file using the a2dissite command:

```
sudo a2dissite 000-default.conf
```

After successfully performing these actions, restart Apache with the following command:

```
sudo systemctl restart apache2
```

### 6. Test Virtual Host

The final step is to test the virtual host. But first, it is important to perform error testing on the virtual host configuration. Type the command below in the Terminal window:

```
sudo apache2ctl configtest  
```

## Future Improvisation

## Support and Contributions

If you think you have found a bug or have a feature request, use our [issue tracker](https://github.com/Aakash-Lobo/MOS/issues). Before opening a new issue, please search to see if your problem has already been reported.  Try to be as detailed as possible in your issue reports.

If you need help using MonoGame or have other questions we suggest you post on our [community forums]().  Please do not use the GitHub issue tracker for personal support requests.

If you are interested in contributing fixes or features to MonoGame, please read our [contributors guide]() first.

### Subscription

If you'd like to help the project by supporting us financially, consider supporting us via a subscription for the price of a monthly coffee.

Money goes towards hosting, new hardware and if enough people subscribe a dedicated developer.

There are several options on our [Donation Page]().

## Source Code

The full source code is available here from GitHub:

* Clone the source: git clone https://github.com/Aakash-Lobo/MOS.git
* Set up the submodules: git submodule update --init
* Open the solution for your target platform to build the game framework.
* Open the Tools solution for your development platform to build the pipeline and content tools.
* For the prerequisites for building from source, please look at the Requirements file.

## Helpful Links

* The official website is [Scratch](https://aakash-lobo.github.io/MOS/index.html).
* Our [Issue Tracker](https://github.com/Aakash-Lobo/MOS/issues) is on GitHub.
* Use our [Community forums]() for support questions.
* The [Official Documentation]() is on the website.

## License

The GameInventory project is under the [Public License]() except for a few portions of the code.  See the [LICENSE.txt]() file for more details.  Third-party libraries used by GameInventory are under their own licenses.  Please refer to those libraries for details on the license they use.

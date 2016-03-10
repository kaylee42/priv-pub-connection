###priv-pub-connection###

This repo contains the basic code for launching a [Faye server](http://faye.jcoglan.com/) using [private_pub](https://github.com/ryanb/private_pub) in order to create an instant group chat feature in Rails.

It is a partner to the [Romp repo](https://github.com/eaud/BookItList) which contains the main code for this application, and the majority of the instructions for deploying this app. 

In order to move into production, hosting this Faye server separately from the main application is a must! Please read [this blog](http://www.thegreatcodeadventure.com/deploying-private-pub-on-heroku/) for more information.

####How To####
Fork & clone this repo, and then run `bundle install` to install dependencies. 

In order to run this on localhost, use this command: 
```
rackup private_pub.ru -s thin -E production
```
This will run the server on localhost:9292. 

In order to run in production, simply change the server address in `config/private_pub.yml`. Additionally, you will need to create an `application.yml` file and include the following: 
```
PRIVATE_PUB_SECRET: {your secret}
```
We highly recommend using [Figaro](https://github.com/laserlemon/figaro) to do this last step and guard your secrets.  


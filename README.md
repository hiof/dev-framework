# Utvikler rammeverk for hiof.no frontend

## Installer nødvendige verktøy

### Installer Git

https://help.github.com/articles/set-up-git


### Installer RVM

Kjør følgende i terminal/shell:

     curl -L get.rvm.io | bash -s stable



### Ruby 
Sjekk om du har Ruby installert med følgende kommando i terminal / shell

    ruby -v


#### Mac 
Installer Ruby 1.9.3-p194:

    rvm install 1.9.3-p194

#### Windows
http://rubyinstaller.org


### Installer bundler


## Setup av SSH 

(Det er mulig du har gjort dette tidligere)

Følg guide for [generering av SSH nøkler](https://help.github.com/articles/generating-ssh-keys) hos github.



## Setup av prosjekt

Åpne ønsket utviklings mappe på din maskin (f.eks. cd ~/dev/ )

Bruk Git til å clone dette utvikler rammeverket

    git clone git@github.com:hiof/dev-framework.git

Naviger til mappen der du klonet prosjektet i terminal / shell

- Aksepter RVMRC filen




Setup submodule

git submodule add git@github.com:hiof/frontend.git /app/assets
rake db:migrate
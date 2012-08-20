# Utvikler rammeverk for hiof.no

# Installasjon

## Github

Høgskolen i Østfold bruker tjenesten GitHub for versjonshåndtering av kode ved hjelp av Git. For å få tilgang til kildekoden må du opprette en konto på http://github.com. Deretter må du sende ditt github brukernavn til webmaster@hiof.no for å få tilgang til våre prosjekter.


## Installer nødvendige verktøy

### Installer Git

Last ned og installer Git for ditt operativsystem her:
http://git-scm.com/downloads

### Installer RVM (kun mac / linux)

Kjør følgende i terminal/shell:

     curl -L get.rvm.io | bash -s stable

### Ruby 
Sjekk om du har Ruby installert med følgende kommando i terminal / shell

    ruby -v

Eksempel på output:

    kdnMBP:~ kdn$ ruby -v
     ruby 1.8.7 (2012-02-08 patchlevel 358) [universal-darwin12.0]

#### Mac 
Installer Ruby 1.9.3-p194:

    rvm install 1.9.3-p194

### Install rubygems

#### Mac
OSX kommer med RubyGems installert. Man kan eventuelt oppdatere denne til seineste versjon med følgende kommando.

    sudo gem update --system

### Installer bundler
    sudo gem install bundler


## Setup av SSH 

(Det er mulig du har gjort dette tidligere)

Følg guide for [generering av SSH nøkler](https://help.github.com/articles/generating-ssh-keys) hos github.


# Bruk

### Setup av utviklerprosjekt


Åpne ønsket utviklings mappe på din maskin (f.eks. cd ~/dev/ ) i terminal / shell

Bruk Git til å clone dette utvikler rammeverket

    git clone git@github.com:hiof/dev-framework.git

Naviger til mappen der du klonet prosjektet i terminal / shell

- Aksepter RVMRC filen


### Setup submodule

Naviger deg fram til roten av prosjektet (du skal allerede være der hvis du har fulgt guiden) i terminal / shell.

Kjør følgende kommando (krever at du har tilgang til prosjektet. Kontakt webmaster@hiof.no for tilgang)

    git submodule add git@github.com:hiof/frontend.git /app/assets
rake db:migrate

## Installer gems

Kjør følgende kommando i terminal / shell for å installere bakgrundsmoduler for å kunne kjøre prosjektet

    bundle


## Jobb med kode

Frontend koden vil du finne i følgende mapper under /app/assets/

    /coffeescript/
    /sass/

Det har i tilleg blitt satt opp 2 stk bibliotek som er tilgjengelig i følgende mappe (disse blir inkludert når koden genereres):

    /libs/assets/javascripts/


Det er anbefalt å jobbe på en egen lokal branch slik at man alltid pusher til og fra master lokalt. Lag for eksempel en lokal branch som heter *endringer*.

## Generere kode for å pushe det til serveren.
Kjør følgende i terminal for å kompilere frontend kode

    rake assets:precompile

Kode vil da bli generert og lagret i mappen /public/assets/

## Push kode til test

Koble deg til NetEd serveren (smb://neted1.hiof.no/hiof_no) 

1. Gå til følgende mappe i finder /public/assets/
2. Kopier application-[md5-hash].js og application-[md5-hash].css til neted1.hiof.no/hiof_no/assets/
3. Oppdater test-block delen av følgende fil med link til filer du lastet opp i forrige steg neted1.hiof.no/hiof_no/customer/hiof/includes/WEBDESIGN_2012/_css-and-js.inc
4. Du kan nå teste hvilken som helst side med ny oppdatert kode ved å sende get paramteren ?testmode

Eks. http://www.hiof.no/nor/hogskolen-i-ostfold/om-hogskolen?testmode

## Push kode live

Etter at koden har blitt testet 

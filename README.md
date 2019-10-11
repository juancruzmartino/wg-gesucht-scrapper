# WG Gesucht Scrapper


A nodejs script for scrapping and the reservation of rooms or flats in the Wg-gesucht site.


## Instalation

    $ npm install
    $ cp .env.example .env



## Configuration

### Credentials
In order to use the script you will need to apply your credentials and template messages in the generated .env file:

    WG_USER= YOUR-USERNAME
    WG_PASSWORD= YOUR-PASSWORD

### Language
The script detects the language of  the ad (German or English) so you will have to provide the message template id of your Germand and English version.

If you wish to use only one language you can use the same id for both languages.

Log in into your wg-account and go into your [Message templates](https://www.wg-gesucht.de/en/mein-wg-gesucht-message-templates.html)). Create an english and german version of your desired message and copy the template id, it should be on the top of the address:
> [https://www.wg-gesucht.de/en/message-template.html?template_id=YOUR-MESSAGE-ID](https://www.wg-gesucht.de/en/message-template.html?template_id=5138171)

Copy the id to the .env file

    MESSAGE_ENG=YOUR-MESSAGE-ID
    MESSAGE_GER=YOUR-MESSAGE-ID
    
### Filter
You can either use an existing custom saved filter or use the url generated after a search applying the filters you want. Both of them should have a format similar to:

> https://www.wg-gesucht.de/en/wg-zimmer-in-Berlin.8.0.1.0.html?offer_filter=1&noDeact=1&city_id=8&category=0&rent_type=0&rMax=450

Once you have your filter url apply it into the .env file

    FILTER_URL=YOUR FILTER URL

## Usage

Run the script

    $ nodejs app.js

Use a raspberry pi or a free vm in order to have it running 24 hours.

## Features

 - Autodiscovery of new rooms or flats every 5 minutes.
 - Ad Languagedetection
 - Autosend messages to owners every 5 minutes

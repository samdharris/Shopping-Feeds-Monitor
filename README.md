# Shopping Feeds Monitor

The Shopping Feeds Monitor was a re-write of an existing system that I undertook of my own accord during my internship at Evoluted during the summer of 2019. The purpose of this system was to enable Evoluted's marketing team to monitor to track how their ecommerce clients were selling their products.

## Technology
The re-write is a Laravel 5.8 app that encompasses a Vuejs SPA that uses Vue Router for client side navigation, Vuex for state management as well as Vuetify to provide a Material Design UX for the app. The data is pulled from a set of RESTful endpoints served by Laravel. The main meat of the re-write is an Artisan command which runs every night at 4am and gets all of Evoluted's ecommerce clients which are stored in the database and foreach client:

1. Downloads the latest version of the Google Shopping Feed XML file or Feed TSV file
1. Goes through each product comparing the most recently recorded changes with the changes in the downloaded file
1. If it detects a change, the system records the change against the product

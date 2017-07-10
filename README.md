# scrapper-module

## Install module
    $ npm install scrapper-module --save

## Require module
    const scrapper = require('scrapper-module');

## Features

  * Simple web scrapper
  * Get selectors
  * Get attributes
  * Parallel scrapping
  * Works with promises

## API

    .scrape([{'url', {model}, {options}}])
    
###### URL

Needs to be a String. This is the resource you are going to scrape

###### Model

Needs to be an object with the following schema
    
    {
      name: {
        elem: '.jobs-item__name'
      },
      categories: {
        elem: '.menu-bar span'
      }
      image: {
        elem: 'img',
        get: 'src'
      }
    }
    
###### Options

Needs to be an object. At least for now the only option we are supponting is 'limit'

    {
      limit: 10
    }

###### Example
    
    let data = [{
      "url": "https://auth0.com/jobs",
      "model": {
        "name": {
          "elem": ".jobs-item__name"
        },
        "categories": {
          "elem": ".menu-bar span"
        },
        "fullOrPartTime": {
          "elem": ".jobs-item__location span"
        }

      }
    },
    {
      "url": "https://auth0.com/jobs",
      "model": {
        "name": {
          "elem": ".jobs-item__name"
        },
        "categories": {
          "elem": ".menu-bar span"
        },
        "fullOrPartTime": {
          "elem": ".jobs-item__location span"
        }

      }
    }];

    scrapper.scrape(data);

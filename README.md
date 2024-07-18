# ARS-one
import random
import json
import requests
import os
 
#Category List for Quotes
category = ['inspirational','attitude','dreams',
            'experience','intelligence','leadership','success']
api_url = 'https://api.api-ninjas.com/v1/\
        quotes?category={}'.format(category[random.randint(0,6)])
 
#Enter your API Key Here
response = requests.get(api_url, headers=
                   {'X-Api-Key': 'XXXXXXXXXXXXXXXXXX'})
 
if response.status_code == requests.codes.ok:
    quote=response.text
    #Load the response into a json object
    quotes = json.loads(quote)
    q=quotes[0]['quote']
     
    #In case of receiving multiple quotes, 
    # we will pick the first one
    mainQuote=q.split('.')[0]
else:
    print("Error:", response.status_code, response.text)
Object.prototype.forEach = Array.prototype.forEach

Object.defineProperty(Object.prototype, 'length', {
  get: () => Object.keys(this).length,
})



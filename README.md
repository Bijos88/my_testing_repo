import requests

import argparse

BASE_URL = 'https://v2.jokeapi.dev'
END_POINT = 'joke'
parser = argparse.ArgumentParser()

parser.add_argument("category")
parser.add_argument('language')

args = parser.parse_args()



end_point = 'joke'
category = 'Dark'

url= f'{BASE_URL}/{END_POINT}/{args.category}'

parameters = {'lang': args.language}


response = requests.get(url=url, params=parameters )
data = response.json()


if data['error'] is True:
    print('Error happened, check endpoint or category if correct.')
    exit()

try:
    print(data['setup'])
    print(data['delivery'])

except KeyError:
    print(data['joke'])


# Atis_Turkish

Re-annotate of [UD_Turkish_Atis](https://github.com/UniversalDependencies/UD_Turkish-Atis) with slots and intents. This treebank is a translation of the original [ATIS dataset](https://github.com/howl-anderson/ATIS_dataset). Hence Atis Turkish is an intent and entity detection dataset for Turkish. 

Intents and slots are extracted by transfer learning. For the explanation of the work I'll compile a paper soon. Here are the all intent names and slots, same with the original ATIS.

All intent names
```
abbreviation
aircraft
airfare
airline
airport
capacity
city
distance
flight
flight_no
flight_time
ground_fare
ground_service
meal
quantity
restriction
```


All slot names
```
aircraft_code
airline_code
airline_name
airport_code
airport_name
arrive_date.date_relative
arrive_date.day_name
arrive_date.day_number
arrive_date.month_name
arrive_date.today_relative
arrive_end_time.time
arrive_start_time.time
arrive_time.day_number
arrive_time.period_of_day
arrive_time.time
arrive_time.time_relative
city_name
class_type
connect
cost_relative
date_relative
day_name
day_number
depart_date.date_relative
depart_date.day_name
depart_date.day_number
depart_date.month_name
depart_date.today_relative
depart_date.year
depart_day.day_number
depart_end_time.time
depart_start_time.time
depart_time.period_of_day
depart_time.time
depart_time.time_relative
fare_amount
fare_basis_code
flight_mod
flight_number
flight_stop
flight_time
fromloc.airport_code
fromloc.airport_name
fromloc.city_name
fromloc.state_code
fromloc.state_name
meal
meal_code
meal_description
mod
month_name
or
part_date.day_number
period_of_day
restriction_code
return_date.date_relative
return_date.day_name
return_date.day_number
return_date.month_name
return_date.today_relative
return_end_time.time
return_time.period_of_day
return_time.time
round_trip
state_code
state_name
stoploc.airport_name
stoploc.city_name
stoploc.ity_name
stoploc.state_code
today_relative
toloc.airport_code
toloc.airport_name
toloc.city_name
toloc.country_name
toloc.state_code
toloc.state_name
transport_type
```

Dataset is presented both in conll and json formats. Here is an example conll annotation for you:

```
# sent_id = 0001.dev
# text = Pittsburgh'tan Atlanta'ya 25 Nisan'da kalkan ve 6 Mayıs'ta dönen en ucuz uçuşu istiyorum
# intent: flight
1	Pittsburgh'tan	pittsburgh	PROPN	B-fromloc.city_name
2	Atlanta'ya	atlanta	PROPN	B-toloc.city_name
3	25	25	NUM	B-depart_date.day_number
4	Nisan'da	nisan	PROPN	B-depart_date.month_name
5	kalkan	kalk	ADJ	O
6	ve	ve	CCONJ	O
7	6	6	NUM	B-return_end_time.time
8	Mayıs'ta	mayıs	PROPN	B-return_date.month_name
9	dönen	dön	ADJ	O
10	en	en	ADV	B-cost_relative
11	ucuz	ucuz	ADJ	I-cost_relative
12	uçuşu	uç	NOUN	O
13	istiyorum	iste	VERB	O
```

and a json annotation:

```
  {
    "text": "Cleveland'dan Miami'ye uçuşlar",
    "intent": "flight",
    "entities": [
      {
        "start": 0,
        "end": 13,
        "value": "Cleveland'dan",
        "entity": "fromloc.city_name"
      },
      {
        "start": 14,
        "end": 22,
        "value": "Miami'ye",
        "entity": "toloc.city_name"
      }
    ]
  },
```
If you want to find out more about how I compiled this dataset you can visit my Youtube channel and watch the playlist [Veriseti nasıl derlenir?](https://www.youtube.com/playlist?list=PLJTHlIwB8Vco4ONU_mCNOYIcVyFA9QrBr). For finest Turkish NLP, you can our [website for Turkish NLP]() or visit my [personal website](https://www.onlyduygu.com).

This work is supported by Google Developer Experts Program.
Part of Duygu 2023 Fall-Winter collection, "Turkish NLP with Duygu"/ "Duygu'yla Türkçe NLP". All rights reserved.


Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

# Wargaming Game Server Population
This is a small app to query the [Wargaming API](https://developers.wargaming.net) in order to collect, store, and display their world-wide server populations.

## API Access
The API request is sent to all four current regions: NA, EU, RU, and Asia.  While a relatively simple JSON structure, the resulting response for each region that needs to be parsed looks like:

```json
{
    "status": "ok",
    "data": {
        "wotb": [
            {
                "players_online":9999,
                "server":"NA"
            }
        ],
        "wot": [
            {
                "players_online":9999,
                "server":"303"
            }
        ],
        "wows": [
            {
                "players_online":9999,
                "server":"NA"
            }
        ]
    }
}
```

## Console Output
While the program is running, you should see the following:
```
Current Playerbase - Bars represent 10,000 concurrent users
----------------------------------------------------------------------

NA             16118 | ++
RU            260509 | +++++++++++++++++++++++++++
EU             25859 | +++
ASIA           17154 | ++

Waiting (00:35 remaining):  [ #################              ]  58%
```
The program will repoll the API endpoints and update the output every 60s.

## Requirements
There is a requirements.txt available which details necessary libraries not included in standard Python.  Additionally, the program needs to import your API key which should be stored in config.py.  That file can be as simple as:
```python
api_key = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"
```
The necessary key can be generated on the [Wargaming developer portal](https://developers.wargaming.net/applications/).

## Additional Work
 - [ ] Parse and store per server population
 - [ ] Implement argparse for required command line options

## Additional Features
 - [ ] Logging - LogBook
 - [ ] Data Storage - SQLAlchemy / peewee
 - [ ] Data Presentation - pandas + Plotly / matplotlib
 - [ ] Web Access - Flask / Djangob

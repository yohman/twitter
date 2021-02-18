# Twitter Archiver

A python script that archives tweets into a csv file.

## Usage

If running locally:

```
pip install -r requirements.txt
```

Arguments:

- `--times` (default=10): How many times to execute the command to get tweets
- `--rest` (default=60): How many seconds to rest between calls to get tweets
- `--location` (defaul=none): Where you want to get tweets from, like Tokyo, or Paris (uses a nominatum geocoder)
- `--distance` (default=50km): Distance in km from the given location to get tweets from
- `--filename` (default="tweets.csv"): csv filename to save your tweets in

### Simple query

```shell
python twitter.py --q 'covid'
```
### Query with different time intervals

Example run 100 times every 30 seconds:

```shell
python twitter.py --q 'covid' --times 100 --rest 30
```
### Query with location

Example: Tweets from within 100km of Los Angeles

```shell
python twitter.py --q 'covid' --location 'Los Angeles' --distance '100km'
```

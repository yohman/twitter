# Twitter Archiver

A python script that archives tweets into a csv file.

## Usage

### 1. Clone this repo to JupyterHub

UCLA students:

Use this [gitpuller link](https://jupyter.idre.ucla.edu/hub/user-redirect/git-pull?repo=https%3A%2F%2Fgithub.com%2Fyohman%2Ftwitter&urlpath=tree%2Ftwitter%2F&branch=master) to clone this repo into your JupyterHub account.

### 2. Install requirements

![terminal](images/terminal.png)

Once inside your JupyterHub, open a new terminal window, navigate to the twitter folder (`cd twitter`), and enter the following command:

```
pip install -r requirements.txt
```
### 3. Running the twitter.py script

Once the requirements have been installed, you can begin your twitter archive by running the following command:

```console
python twitter.py --q 'covid'
```

There are additional arguments you can pass to refine your search. Here are a list of available arguments:

- `--times` (default=10): How many times to execute the command to get tweets
- `--rest` (default=60): How many seconds to rest between calls to get tweets
- `--location` (defaul=none): Where you want to get tweets from, like Tokyo, or Paris (uses a nominatum geocoder)
- `--distance` (default=50km): Distance in km from the given location to get tweets from
- `--filename` (default="tweets.csv"): csv filename to save your tweets in

#### Query with different time intervals and custom filename

Example: Run 100 times, every 5 minutes, name the file `covid.csv`:

```console
python twitter.py --q 'covid' --times 100 --rest 300 --filename 'covid.csv'
```

#### Query with location

Example: Tweets from within 100km of Los Angeles custom filename

```console
python twitter.py --q 'covid' --location 'Los Angeles' --distance '100km' --filename 'covid_la.csv'
```

### 4. Analyzing tweets in Jupyter Notebook

Open a new Python Jupyter Notebook and import your tweets

```python
import pandas as pd

df = pd.read_csv('tweets.csv')
```


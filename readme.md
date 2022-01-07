Hey, welcome!
Appearently, you have the fun task to create the copytrading app. Congrats!

Let's start from the vision. I want that this piece of code will download statistics and positions of best traders in Binance leaderboard, and allows users to copy their trades automatically. More precisely:
 - Data about positions is downloaded in parallel cycles (so to be faster)
 - An user logs in in the platform, and can select the traders that wants to copy, automatically
 - He inserts the private keys, and the total amount to commit for the strategy
 - An instance of trading.py is opened for him, and based on the data downloaded from the other scripts, he will trade

The current codebase has just a proposal of implementation of this, and a lot is missing. 
Please, take the current codebase only as a reference of which functionalities are needed, and a possible solution method.
Feel free to restart from zero, or start from the current code. But the final version has to be 100% functional. 100%.

Let's sketch some points that the app must/mustn't have:
- Download each day the performances of all the top traders in binance (FROM INTERNAL API, NOT SCRAPING, see complete.chls) and store results in a table
- One script takes care of downloading the positions. In parallel, given that there are a lot of trades and parallelization will reduce the time between updates.
- The messages sent to the different bots are made from a script that reads the database
- Databases must be clean. No entries with no-sense, like non-existent positions, NA or 0. Properly handle exceptions
- All the trading functions must be created. Will use Huobi APIs for simplicity. Market orders are fine.

How to run the app from the server. Improve this as well...
jupyter nbconvert --to script 'Copytrading.ipynb'
python3 Copytrading.py

git reset --hard
git pull

# How to set up
Add your public and private API keys in the keys.py file. 

# Telegram messages
If you would like to get messages via Telegram if your stop loss is hit, follow the link in keys.py

# How it works
There is no user interaction necessary. If you place a stop loss order after buying a coin on Binance, the program will calculate the procentual difference between the buying price and the first stop loss.
This first stop loss is then used as a reference for further stop loss percentages.

# Windows & MacOS
These OSes do not have the problem that Linux based system have. If you run TrailingStop.py alone, it should work.

# Linux
There is a problem where the sockets can be closed or restarted once they have started running.
Unfortunately, the developer of python-binance has not fixed this problem yet.
So to fix this problem, you need to run run.py which will restart the trailing stop loss program every 24 hours.

# Example
- Market buy 1000 DOGE/USDT at 0,295$.
- Place a stop loss at 0,26$.
- Procentual difference is calculated: 13,46%.
- If the price rises, the difference between current close price and stop price will stay 13,46%.
- If the price drops, stop loss price will stay where it is.

# Old Version
The old version is called BinanceAlert and needs to use run.py as well.
The difference between this version and the new one is that it also sends messages based on key levels and technical analysis.
Unfortunately there were some issues and I only needed it for the trailing stop loss function, that is why I made this new version.

To make BinanceAlertV3.py function:\
Change the 'publicKey' and 'privateKey' in Client and altClient on lines 19, 22, 593 and 594 to your Binance API keys.

altClient might not be necessary if you change some settings, but I use it to make sure it won't stop because it is exceeding the max requests.
run.py is necessary if you want to run it on Linux, which is what I am currently doing. 

# BinanceAlert use cases
BinanceAlert provides alerts on the USDT pairs. These alerts are based on multiple factors, such as technical analysis, new listings on Binance and changes in your stop-loss.

Note:
Currently BinanceAlert only support the USDT pairs, adding BTC pairs might be done later.
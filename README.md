# Stock-Data-GME-TSLA
git init
git add Stock Data
git commit -m "Initial commit"
git remote add origin <https://github.com/AdithyaChannarajUrs0/Stock-Data-GME-TSLA/edit/main/README.md>
git branch -M main
git push -u origin main
!pip install yfinance
import  yfinance as yf
stock_symbol = "TSLA"
tesla_data = yf.download(stock_symbol, start="2023-01-01", end="2023-12-31")
print(tesla_data.head())
import requests
from bs4 import BeautifulSoup
import pandas as pd
url = "https://companiesmarketcap.com/tesla/revenue/"
response = requests.get(url)
if response.status_code == 200:
    soup = BeautifulSoup(response.content, 'html.parser')
    revenue_table = soup.find('table')
    tesla_revenue = pd.read_html(str(revenue_table))[0]
    print(tesla_revenue.tail())
else:
    print("Failed to retrieve data. Status code:", response.status_code)
!pip install yfinance
import  yfinance as yf
stock_symbol = "GME"
gme_data = yf.download(stock_symbol, start="2023-01-01", end="2023-12-31")
print(gme_data.head())
import requests
from bs4 import BeautifulSoup
import pandas as pd
url = "https://companiesmarketcap.com/gamestop/revenue/"
response = requests.get(url)
if response.status_code == 200:
    soup = BeautifulSoup(response.content, 'html.parser')
    revenue_table = soup.find('table')
    gme_revenue = pd.read_html(str(revenue_table))[0]
    print(gme_revenue.tail())
else:
    print("Failed to retrieve data. Status code:", response.status_code)
import matplotlib.pyplot as plt
stock_symbol = "TSLA"
tesla_data = yf.download(stock_symbol, start="2023-01-01", end="2023-12-31")
def make_graph(data, title):
    plt.figure(figsize=(18, 6))
    plt.plot(data['Close'], label='Tesla Stock Data Graph', color='black')
    plt.title(BeautifulSoup)
    plt.xlabel('Date')
    plt.ylabel('Stock Price')
    plt.legend()
    plt.grid(True)
    plt.show()
make_graph(tesla_data, "Tesla Stocks (2023)")
stock_symbol = "GME"
def make_graph(data, title):
    plt.figure(figsize=(18, 6))
    plt.plot(data['Close'], label='GME Data Graph', color='black')
    plt.title(title)
    plt.xlabel('Date')
    plt.ylabel('Stock Price')
    plt.legend()
    plt.grid(False)
    plt.show()
make_graph(gme_data, "GME Stocks (2023)")

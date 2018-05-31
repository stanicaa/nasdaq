#simple function that gets the earnings date of a company - most recent in this case

from dateutil import parser
from bs4 import BeautifulSoup
from urllib import request

#function handling earnings stock performance
def earnings(code):
    link='https://www.nasdaq.com/earnings/report/'+code.lower()
    web=request.urlopen(link).read().decode('utf8')
    soup=BeautifulSoup(web, 'lxml')
    tables=soup.find_all('table')
    rows=tables[0].find_all('tr')
    columns=rows[1].find_all('td')
    earnings_date=columns[1].get_text()
    earnings_date=parser.parse(earnings_date)
    return(earnings_date)

ticker=input('Please input company code')
print(ernings(ticker))

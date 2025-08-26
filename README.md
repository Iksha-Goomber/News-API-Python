# News-API-Python
The News API Project is a Python application that fetches and displays the latest news articles from an API, allowing users to stay updated with real-time headlines.
import requests

query = input("What type of news are you interested in today?\n")
api = "d91a8dd9a1984082bf91ef8b827342ee"

url = f"https://newsapi.org/v2/everything?q={query}&from=2025-06-22&sortBy=publishedAt&apiKey={api}"

print(url)
r = requests.get(url)

data = r.json()
articles = data["articles"]

for index, article in enumerate(articles):
    print(index + 1, article["title"])
    print(article["url"])
    print("\n*****************************************************************************************************\n")

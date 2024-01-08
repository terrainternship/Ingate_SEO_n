Скрипт для сбора топ-10 ссылок выдачи Яндекс:
```
def get_yandex_urls(query):
    urls = []
    url = f"https://yandex.ru/search/?text={query}"
    response = requests.get(url)
    soup = BeautifulSoup(response.text, "html.parser")
    links = soup.find_all("a", class_="organic__url")
    for link in links[:10]:
        urls.append(link["href"])
    return urls
```

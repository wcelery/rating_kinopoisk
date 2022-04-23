Scraper for dump your film ratings from kinopoisk.ru.

# Installation

```bash
$ pip install -r requirements.txt
$ scrapy startproject scraper
$ cd scraper
$ scrapy genspider kinopoisk www.kinopoisk.ru
```

# Configure

Setup cookie `ya_sess_id` in `scraper.spiders.KinopoiskSpider.COOKIES`.
You have to specify the page in ./spiders/kinopoisk.py:45, lazy to fix
```python
url = self.PAGES.format(user_id=self.user_id, page_no=<your_number>)
```

# Run

Update by uid from cookies.

```bash
$ scrapy crawl kinopoisk -o ratings.csv -t csv -a user_id=<uid>
```

# Related link

[Article with detail (ru)](https://tyvik.ru/posts/dump-kinopoisk/)

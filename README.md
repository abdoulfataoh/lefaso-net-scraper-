## lefaso-net-scraper

<div align="center">
  <p>
    <a href="https://pypi.org/project/lefaso-net-scraper/"><img src="https://raw.githubusercontent.com/abdoulfataoh/lefaso-net-scraper/master/docs/icon.png" style="width:60px;height:60px;"></a>
  </p>
</div>

<div align="center">
  <p>
    <a href="https://badge.fury.io/py/lefaso-net-scraper"><img src="https://badge.fury.io/py/lefaso-net-scraper.svg" alt="PyPI version"></a>
    <a href="https://pepy.tech/project/lefaso-net-scraper"><img src="https://static.pepy.tech/badge/lefaso-net-scraper"></a>
    <a href="https://github.com/abdoulfataoh/lefaso-net-scraper"><img src="https://github.com/abdoulfataoh/lefaso-net-scraper/actions/workflows/test-action.yaml/badge.svg"></a> <br>
    <a href="https://github.com/abdoulfataoh/lefaso-net-scraper"><img src="https://github.com/abdoulfataoh/lefaso-net-scraper/actions/workflows/publish-action.yaml/badge.svg"></a>
  </p>
</div>

### Description
lefaso-net-scraper is a robust and versatile Python library designed to efficiently extract articles from the popular online news source of of Burkina Faso, [www.lefaso.net](https://www.lefaso.net). This powerful scraping tool allows users to effortlessly collect article content and data from Internet users’ comments on lefaso.net.

### Important
  > Our scraper, like other scrapers, is based on the structure of the target website. Changes to the website's structure can affect the scraper. We use automated workflows to detect these issues frequently, but we cannot catch all of them. Please report any issues you encounter and use the latest version.

### Data Format

<div align="center">

| Field                  | Description            |
|------------------------|------------------------|
| article_topic          | article topic          |
| article_title          | article title          |
| article_published_date | article published date |
| article_origin         | article origin         |
| article_url            | article url            |
| article_content        | article content        |
| article_comments       | article comments       |

</div>

### Installation

- With poetry

```bash
poetry add lefaso-net-scraper
poetry update lefaso-net-scraper  # to update the package
```

- With pip

```bash
pip install --upgrade  lefaso-net-scraper
```

### Usage

  
```python
# coding: utf-8

from lefaso_net_scraper import LefasoNetScraper

section_url = 'https://lefaso.net/spip.php?rubrique473'
scraper = LefasoNetScraper(section_url)
data = scraper.run()
```

- Settings Pagination range

```python
# coding: utf-8

from lefaso_net_scraper import LefasoNetScraper

section_url = 'https://lefaso.net/spip.php?rubrique473'
scraper = LefasoNetScraper(section_url)
scraper.set_pagination_range(start=20, stop=100)
data = scraper.run()
```

- Save data to csv

```python

# coding: utf-8

from lefaso_net_scraper import LefasoNetScraper
import pandas as pd

section_url = 'https://lefaso.net/spip.php?rubrique473'
scraper = LefasoNetScraper(section_url)
data = scraper.run()
df = pd.DataFrame.from_records(data)
df.to_csv('path/to/df.csv')
```

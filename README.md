# ds_final

A simple Data Science Project. Enjoy it and Star it :star:
## Group info:

No. 15

18120184 - Nguyễn Nguyên Khang

18120189 - Trần Đăng Khoa

:dart:
Task | Assigned
------------ | -------------
:white_check_mark: Data Crawler | @Al3927 Nguyen Khang
Data Exploration & Preprocessing | @Al3927 Nguyen Khang
Data Modeling (Train models and review them) | @cstotodile Tran Khoa

## Table of Contents

- [The Question](#the-question)
- [Dataset](#Dataset)
- [How to use](#how-to-use)
  - [Crawler](#Crawler)

## The question

> __How to sell well on shopee.vn?__

Output: `historical_sold` of an item in shopee.vn

## Dataset

We crawl this dataset from shopee.vn

This dataset has 30 features before preprocessing:

![features](https://github.com/cstotodile/ds_final/blob/main/images/features.jpg?raw=true)

The most important feature is: `sell_time`. This feature be calculated by ```item_be_got_time - item_public_time```, describe how long the item has been sold

## How to use

### Crawler

1. Open GetData.ipynb

2. Change the arguments when init APIService:

```python
APIService = APIService(newest, keyword = "thoi trang nam", categoryids = "2829")
```

_newest_: the item which is the first be got (start with 0) (Do not change this)(*)

_keyword_: keyword

_categoryids_: in this specific case (shoppe), some keywords have specifics category, you can go to shopee, search with your keyword, choose the category, and look on the URL bar:
It will show something like this:

https://shopee.vn/search?facet=2829&keyword=thoi%20trang%20nam&noCorrection=true&page=0

The value of param `facet` (2829) is the `categoryids` you need.

(*) You will change the value of this when creating a new instance of the crawler: 
```python 
crawler = DataCrawler(0)
```

3. Change file name: 
```python
crawler.saveFile("ShoppeItem_thoiTrangNam_aoKhoacAoVest.tsv")
```

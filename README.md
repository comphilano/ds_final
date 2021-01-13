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
:white_check_mark: Data Exploration & Preprocessing | @Al3927 Nguyen Khang, @cstotodile Tran Khoa
:white_check_mark: Data Modeling (Train models and review them) | @cstotodile Tran Khoa
README.md | @Al3927 Nguyen Khang

## Table of Contents

- [The Question](#the-question)
- [Dataset](#Dataset)
- [How to use](#how-to-use)
  - [Crawler](#Crawler)
- [Know the code](#Know-the-code)

## The question

> __How to sell well on shopee.vn?__

Output: `historical_sold` of an item in shopee.vn

## Dataset

We crawl this dataset from shopee.vn

![dataShape](/images/dataShape.jpg)

This dataset has 33 features before preprocessing:

![features](https://github.com/cstotodile/ds_final/blob/main/images/features.jpg?raw=true)

The most important feature is: `sell_time`. This feature be calculated by ```item_be_got_time - item_public_time```, describe how long the item has been sold

Feature | Meaning
------------ | -------------
`name` | string, item name
`shop_location` | string, location of the shop sell this item
`item_puplic_time` | int, the number of seconds since midnight, January 1, 1970 (time since 1970) to the time this item be public.
`item_be_got_time` | int, the number of seconds since midnight, January 1, 1970 to the time this item be got.
`sell_time` | int, the time this item be sell on shopee formed by  _time since 1970_, `sell_time = item_be_got_time - item_puplic_time`

## How to use

### Crawler

1. Open GetData.ipynb

2. Change the arguments when init Crawler (creating a new instance of the crawler):

```python
crawler = DataCrawler(newest = 0, keyword = 'thoi trang nam', categoryids = '15139')
```

_newest_: the first item will be got (start with 0)

_keyword_: keyword

_categoryids_: in this specific case (shopee), some keywords have specifics category, you can go to shopee, search with your keyword, choose the category, and look on the URL bar:

It will show something like this:

https://shopee.vn/search?facet=2829&keyword=thoi%20trang%20nam&noCorrection=true&page=0

The value of param `facet` (2829) is the `categoryids` you need.

_Notice that in this project we don't support call multi categoryids._



3. Change file name: 
```python
crawler.saveFile("ShoppeItem_thoiTrangNam_aoKhoacAoVest.tsv")
```

## Know the code

# ds_final

A simple Data Science Project. Enjoy it and Star it :star:
## Group info:

No. 15

18120184 - Nguyễn Nguyên Khang @Al3927

18120189 - Trần Đăng Khoa @cstotodile

:dart:
Task | Assigned
------------ | -------------
:white_check_mark: Data Crawler | @Al3927 Nguyen Khang
:white_check_mark: Data Exploration & Preprocessing | @Al3927 Nguyen Khang, @cstotodile Tran Khoa
:white_check_mark: Data Modeling (Train models and review them) | @Al3927 Nguyen Khang, @cstotodile Tran Khoa
README.md, teamwork.pdf | @Al3927 Nguyen Khang

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

This dataset has 34 features before preprocessing:

![features](https://github.com/cstotodile/ds_final/blob/main/images/features.jpg?raw=true)

The most important feature is: `sell_time`. This feature be calculated by ```item_be_got_time - item_public_time```, describe how long the item has been sold

Feature | Meaning (At the time this item be got)
------------ | -------------
`category_id` | int, the id of the item's category
`name` | string, item name
`shop_location` | string, location of the shop sell this item
`item_puplic_time` | int, the number of seconds since midnight, January 1, 1970 (time since 1970) to the time this item be public.
`item_be_got_time` | int, the number of seconds since midnight, January 1, 1970, to the time this item be got.
`sell_time` | int, the time this item be sell on Shopee formed by  _time since 1970_, `sell_time = item_be_got_time - item_puplic_time`
`shopee_verirfied` | bool, is this shop be verified or not
`discount` | float, the discount of this item
`is_adult` | bool, is this item for adult
`options` | int, How many options this item has
`show_official_shop_label_in_title` | bool, show that if this item will have an official shop label or not
`rating star` | float, star score of this item
`five star`, `four_star`, `three_star`, `three_star`, `two_star`, `one_star` | int, how many five star this item have
`flash_sale` | bool, is this item have a flash sale now
`upcoming_flash_sale` | bool, is this item has an upcoming flash sale
`price_min` | int price min of this item
`price_min_before_discount` | int, price min before discount
`price_max` | int, price max of this item
`price_max_before_discount` | int, price max before discount
`price` | float, price of this item
`price_before_discount` | int, price before discount
About price feature, we have an example: | ~2000 - 5000~ 1000 - 2500: pmin = 100000000, pmax = 250000000, p = 100000000, pminbf = 200000000, pmaxbf = 500000000
`coin_earn_label` | bool, show coin earn label or not
`liked_count` | int, how many liked this item has
`view_count` | int, how many views for this item
`cmt_count` | int, how many comments for this item
`is_preferred_plus_seller` | bool, show if this item has an icon tell this is a preferred plus seller or not
`show_free_shipping` | bool, show if this item has an icon freeship or not 
`images` | int, how many images this item has
`video_info_list` | int, how many videos this item has
`historical_sold` | int, how many items have been sold

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

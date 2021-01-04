# ds_final

## Group info:

No. 15

18120184 - Nguyễn Nguyên Khang

18120189 - Trần Đăng Khoa

Subject | Attachment
------------ | -------------
  - [x] Data Crawler | Nguyen Khang

  - [ ] Preprocessing | Nguyen Khang

  - [ ] Train model and review them | Dang Khoa


## How to use

### Crawler

1. Open GetData.ipynb

2. Change the arguments when init APIService:

```python
APIService = APIService(newest, keyword = "thoi trang nam", categoryids = "2829")
```

newest: the item which is the first be got (start with 0) (Do not change this)(*)

keyword: keyword

categoryids: in this specific case (shoppe), some keywords have specific category, you can go to shoppe, search with your keyword, choose the category, and look on the URL bar:
It will show something like this:

https://shopee.vn/search?facet=2829&keyword=thoi%20trang%20nam&noCorrection=true&page=0

The value of param `<facet>` (2829) is the `<categoryids>` you need.

(*) You will change the value of this when creating a new instance of the crawler: 
```python 
getData = GetData(0) 
```

3. Change file name: 
```python
getData.saveFile("ShoppeItem_thoiTrangNam_aoKhoacAoVest.tsv")
```

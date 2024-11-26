# django 起手式

## 安裝django
* 先去看一下[django版本與適用的python版本](https://docs.djangoproject.com/en/5.1/faq/install/)
* 使用pip安裝
```sh
$ python -m pip install Django
```
* 使用[git](https://github.com/django/django)
```sh
$ git clone https://github.com/django/django.git
```

* 確認安裝是否成功與版本確認
```sh
$ python
>>> import django
>>> print(django.get_version())
5.1
```

## 基本CRUD
### 新增 create
```py
ModelName.objects.create()
```
![](https://i.imgur.com/irOkHAE.png)

若有在models.py當中先keyin好預設值，那麼當直接輸入`objects.create()`時就會依預設值輸入

### 讀取 read
```py
ModelName.objects.all()          # return所有資料 | QuerySet格式
ModelName.objects.get(pk=_)      # return指定單一資料 | Object格式
ModelName.objects.filter(id=_)   # return指定資料 | QuerySet格式
```
![](https://i.imgur.com/sFzrxtW.png)

* `get()`只能取單一資料，若沒有匹配結果或是有多筆結果，都會回傳`MultipleObjectsReturned`錯誤

### 更新 update
```
ModelName.objects.filter().update(key=value)
```
![](https://i.imgur.com/5psAzFa.png)
![](https://i.imgur.com/kraZ3Ho.png)
先指定id，再進行更新

### 刪除 delete
```py
ModelName.objects.filter().delete()
```

![](https://i.imgur.com/XR2Lrel.png)
![](https://i.imgur.com/5FzDTE5.png)

* 先指定id，再進行刪除。
* 注意的是id並不會遞補，之後新增也會持續增加下去。儘管id還是可以指向6，也補不回來。
![](https://i.imgur.com/ZVdPz4A.png)


## 專案建置
### 初始化
### MTV使用
### 路徑設定
### 網頁應用
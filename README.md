# -Hexschool-2024-React-homework-w5

【六角學院】2024 React 直播冬季班 第五週作業-React 進階運用

使用到的套件

```bash
npm i axios bootstrap react-hook-form react-loading
```

<br>

## 加入購物車

[加入購物車 API](<https://hexschool.github.io/ec-courses-api-swaggerDoc/#/%E5%AE%A2%E6%88%B6%E8%B3%BC%E7%89%A9%20-%20%E8%B3%BC%E7%89%A9%E8%BB%8A%20(Cart)/post_v2_api__api_path__cart>)

分成 Modal 以及列表的按鈕

函式可以設計成傳入對應的數字作為新增項目的數量

<br>

## 取得購物車列表

[購物車列表 API](<https://hexschool.github.io/ec-courses-api-swaggerDoc/#/%E5%AE%A2%E6%88%B6%E8%B3%BC%E7%89%A9%20-%20%E8%B3%BC%E7%89%A9%E8%BB%8A%20(Cart)/get_v2_api__api_path__cart>)

要留意回傳的資料結構

res.data.data.carts

#### 當購物車沒有資料時

1. 不顯示列表
2. 清空購物車按鈕要加上 disabled 樣式

<br>

## 刪除購物車項目（[單一](<https://hexschool.github.io/ec-courses-api-swaggerDoc/#/%E5%AE%A2%E6%88%B6%E8%B3%BC%E7%89%A9%20-%20%E8%B3%BC%E7%89%A9%E8%BB%8A%20(Cart)/delete_v2_api__api_path__cart__id_>)、[全部](<https://hexschool.github.io/ec-courses-api-swaggerDoc/#/%E5%AE%A2%E6%88%B6%E8%B3%BC%E7%89%A9%20-%20%E8%B3%BC%E7%89%A9%E8%BB%8A%20(Cart)/delete_v2_api__api_path__carts>)）

Note：API 路徑要傳的是 cart id

<br>

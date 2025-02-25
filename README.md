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

## 調整購物車產品數量

Note：API 路徑要傳的是 cart id，帶的資料傳的是 product id

<br>

## [結帳付款](<https://hexschool.github.io/ec-courses-api-swaggerDoc/#/%E5%AE%A2%E6%88%B6%E8%B3%BC%E7%89%A9%20-%20%E7%B5%90%E5%B8%B3%20(Order)/post_v2_api__api_path__order>)

1. 從 useForm 取出需要的函式、狀態（register、handleSubmit、errors）
2. 透過 register 註冊要綁定的狀態
3. 撰寫錯誤提示、樣式
4. 撰寫表單提交的函式

#### Email 驗證

```jsx
/^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
```

#### 電話格式驗證（市內 + 手機）

```jsx
/^(0[2-8]\d{7}|09\d{8})$/;
```

- 送出訂單後，購物車需要清除原本項目（後端預設會清除，前端只要重新取得購物車即可）

除此之外也可以透過 reset 清空表單

- 購物車無產品時不建議發出結帳請求

為結帳按鈕加上 disabled 樣式

<br>

## 加入 Loading 狀態

[react-loading 套件](https://www.npmjs.com/package/react-loading)

```bash
import ReactLoading from 'react-loading';
```

```bash
<ReactLoading type={'spin'} color={'#000'} height={'1.5rem'} width={'1.5rem'} />
```

有哪些地方可以加上 loading 狀態

全螢幕

- 取得產品列表
- 調整購物車品項，數量 / 刪除
- 清空購物車
- 結帳

<br>

Loading 模板

```jsx
<div
  className="d-flex justify-content-center align-items-center"
  style={{
    position: "fixed",
    inset: 0,
    backgroundColor: "rgba(255,255,255,0.3)",
    zIndex: 999,
  }}
>
  <ReactLoading type="spin" color="black" width="4rem" height="4rem" />
</div>
```

<br>

部分 - 加入購物車

- 單一產品頁 / 產品 Modal
- 產品列表

模板

```jsx
<button
  type="button"
  className="btn btn-primary d-flex align-items-center gap-2"
>
  加入購物車
  <ReactLoading
    type={"spin"}
    color={"#000"}
    height={"1.5rem"}
    width={"1.5rem"}
  />
</button>
```

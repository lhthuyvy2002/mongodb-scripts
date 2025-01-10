
# MongoDB Scripts

## Giới thiệu
Repository này chứa các đoạn mã mẫu để làm việc với MongoDB, bao gồm thêm, tìm kiếm và lọc dữ liệu trong một bộ sưu tập (`collection`). Những đoạn mã này phù hợp cho cả MongoDB Shell và MongoDB Compass, giúp bạn dễ dàng thao tác với cơ sở dữ liệu.

## Nội dung

### 1. Thêm một sản phẩm
Đoạn mã sau đây thêm một sản phẩm mới vào bộ sưu tập `demoDB.products`:

```javascript
db.products.insertOne({
  "productName": "Laptop X",
  "category": "Electronics",
  "price": 1500,
  "stock": 20,
  "isAvailable": true
})
```

### 2. Thêm nhiều sản phẩm
Đoạn mã này thêm nhiều sản phẩm cùng một lúc vào bộ sưu tập `demoDB.products`:

```javascript
db.products.insertMany([
  {
    "productName": "Tablet Y",
    "category": "Electronics",
    "price": 800,
    "stock": 50,
    "isAvailable": true
  },
  {
    "productName": "Smartphone Z",
    "category": "Electronics",
    "price": 100,
    "stock": 50,
    "isAvailable": false
  }
])
```

### 3. Tìm kiếm sản phẩm
#### a. Tìm sản phẩm theo danh mục
Tìm các sản phẩm thuộc danh mục `Electronics`:

```javascript
db.products.find({ "category": "Electronics" })
```

#### b. Lọc sản phẩm theo giá
Tìm các sản phẩm có giá lớn hơn 1000:

```javascript
db.products.find({ "price": { "$gt": 1000 } })
```

## Hướng dẫn sử dụng

1. **Chuẩn bị môi trường:**
   - Cài đặt MongoDB trên hệ thống của bạn (Server và Shell).
   - Khởi động MongoDB Server và tạo cơ sở dữ liệu `demoDB` nếu chưa tồn tại:
     ```javascript
     use demoDB
     ```

2. **Sử dụng MongoDB Shell:**
   - Chạy các lệnh `insertOne` hoặc `insertMany` để thêm dữ liệu vào bộ sưu tập.
   - Dùng lệnh `find` để tìm kiếm dữ liệu.

3. **Sử dụng MongoDB Compass:**
   - Đối với việc thêm sản phẩm:
     - Truy cập vào bộ sưu tập `demoDB.products`.
     - Nhấn nút **Insert Document** và dán nội dung JSON vào cửa sổ bật lên.
   - Đối với việc tìm kiếm sản phẩm:
     - Nhập bộ lọc tìm kiếm (ví dụ: `{ "category": "Electronics" }`) vào ô **Filter** và nhấn Enter.


## Thông tin thêm
- **Tài liệu tham khảo MongoDB**: [https://www.mongodb.com/docs](https://www.mongodb.com/docs)

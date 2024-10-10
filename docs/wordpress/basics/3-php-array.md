---
id: mang-trong-php
title: Mảng trong PHP
sidebar_position: 4
---

# Bài học: Mảng trong PHP

Chào mừng bạn đã trở lại!

Hôm nay, chúng ta sẽ cùng nhau khám phá một chủ đề rất thú vị: "Mảng là gì?"

## Mục lục

1. [Khái niệm Mảng](#khái-niệm-mảng)
2. [Bắt đầu với mã](#bắt-đầu-với-mã)
    - [Bước 1: Mở tệp PHP chỉ mục](#bước-1-mở-tệp-php-chỉ-mục)
    - [Bước 2: Tạo biến đơn giản](#bước-2-tạo-biến-đơn-giản)
    - [Bước 3: Tạo mảng](#bước-3-tạo-mảng)
    - [Bước 4: Truy cập phần tử trong mảng](#bước-4-truy-cập-phần-tử-trong-mảng)
    - [Bước 5: Lặp qua mảng](#bước-5-lặp-qua-mảng)
    - [Bước 6: Tạo danh sách đếm đến 100](#bước-6-tạo-danh-sách-đếm-đến-100)
    - [Bước 7: Sử dụng vòng lặp foreach](#bước-7-sử-dụng-vòng-lặp-foreach)
3. [Bài tập](#bài-tập)
4. [Tổng kết](#tổng-kết)

## Khái niệm Mảng

-   Một mảng là một tập hợp các giá trị.
-   Ví dụ: Một đại lý xe hơi có thể có nhiều màu sắc cho một chiếc xe.

## Bắt đầu với mã

### Bước 1: Mở tệp PHP chỉ mục

-   Mở tệp `index.php` trong thư mục chủ đề của bạn.
-   Xóa tất cả mã thử nghiệm từ bài học trước.

### Bước 2: Tạo biến đơn giản

-   Tạo một biến lưu trữ tên của bạn.

```php
<?php
$name = "Brad";
?>
```

-   Sử dụng biến này trong HTML.

```php
<p>Xin chào, tên tôi là <?php echo $name; ?>.</p>
```

-   Lưu tệp và kiểm tra kết quả.

### Bước 3: Tạo mảng

-   Tạo một biến mảng để lưu trữ nhiều tên.

```php
<?php
$names = array("Brad", "John", "Jane", "Meowsalot");
?>
```

### Bước 4: Truy cập phần tử trong mảng

-   Truy cập và hiển thị phần tử đầu tiên trong mảng.

```php
<p>Xin chào, tên tôi là <?php echo $names[0]; ?>.</p>
```

-   Lưu tệp và kiểm tra kết quả.

### Bước 5: Lặp qua mảng

-   Sử dụng vòng lặp while để lặp qua mảng và hiển thị tất cả tên.

```php
<?php
$count = 0;
while ($count < count($names)) {
    echo "<p>Xin chào, tên tôi là " . $names[$count] . ".</p>";
    $count++;
}
?>
```

-   Lưu tệp và kiểm tra kết quả.

### Bước 6: Tạo danh sách đếm đến 100

-   Sử dụng vòng lặp while để tạo danh sách đếm đến 100.

```php
<?php
$count = 1;
while ($count <= 100) {
    echo "<li>" . $count . "</li>";
    $count++;
}
?>
```

-   Lưu tệp và kiểm tra kết quả.

### Bước 7: Sử dụng vòng lặp foreach

-   Cuối cùng, chúng ta sẽ sử dụng vòng lặp foreach để lặp qua mảng và hiển thị tất cả tên. Đây là cách làm đơn giản và hiệu quả!

```php
<?php
foreach ($names as $name) {
    echo "<p>Xin chào, tên tôi là " . $name . ".</p>";
}
?>
```

-   Lưu tệp và kiểm tra kết quả.

### Tổng kết

-   Bây giờ bạn đã biết cách tạo và sử dụng mảng trong PHP.
-   Trong bài học tiếp theo, chúng ta sẽ tìm hiểu cách sử dụng mảng để hiển thị nội dung động từ WordPress.

Chúc các bạn học vui vẻ và thành công!

## Bài tập

1. **Tạo mảng mới**:

    - Tạo một mảng mới chứa các tên của các thành phố bạn muốn đến thăm.
    - Hiển thị tên của thành phố đầu tiên trong mảng.

2. **Lặp qua mảng với vòng lặp for**:

    - Sử dụng vòng lặp for để lặp qua mảng các thành phố và hiển thị từng tên thành phố.

3. **Tạo mảng kết hợp**:

    - Tạo một mảng kết hợp chứa tên của các thành phố và quốc gia tương ứng.
    - Sử dụng vòng lặp foreach để hiển thị tên thành phố và quốc gia.

4. **Tính tổng các số trong mảng**:
    - Tạo một mảng chứa các số từ 1 đến 10.
    - Sử dụng vòng lặp để tính tổng các số trong mảng và hiển thị kết quả.

Chúc các bạn học vui vẻ và thành công!

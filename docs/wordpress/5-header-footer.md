---
id: header-footer
title: Header và Footer
sidebar_position: 6
---

Chào mừng bạn đã trở lại!

Trong bài học này, chúng ta sẽ học cách thiết lập đầu trang và chân trang toàn cục trong một trang web. Nếu bạn không biết tôi đang đề cập đến điều gì, hãy để tôi chỉ cho bạn.

## Mục lục

1. [Giới thiệu](#giới-thiệu)
2. [Thiết lập đầu trang và chân trang](#thiết-lập-đầu-trang-và-chân-trang)
3. [Sử dụng PHP để tái sử dụng đầu trang và chân trang](#sử-dụng-php-để-tái-sử-dụng-đầu-trang-và-chân-trang)
4. [Sử dụng WordPress để quản lý đầu trang và chân trang](#sử-dụng-wordpress-để-quản-lý-đầu-trang-và-chân-trang)
5. [Bài tập](#bài-tập)
6. [Hướng dẫn cách làm](#hướng-dẫn-cách-làm)
7. [Tổng kết](#tổng-kết)

## 1. Thiết lập đầu trang và chân trang

Trên hầu hết các trang web, bạn sẽ muốn một số loại vùng tiêu đề xuất hiện trên mọi trang của trang web. Điều tương tự với khu vực chân trang. Để thêm nội dung ở đầu và cuối trang, bạn có thể làm như sau:

```html
<!-- Đầu trang -->
<!DOCTYPE html>
<html>
    <head>
        <title>Trang chủ</title>
    </head>
    <body>
        <header>Đây là vùng tiêu đề</header>

        <!-- Nội dung trang -->

        <!-- Chân trang -->
        <footer>Đây là khu vực chân trang</footer>
    </body>
</html>
```

## 2. Sử dụng PHP để tái sử dụng đầu trang và chân trang

Thay vì sao chép mã tiêu đề và chân trang vào nhiều tệp mẫu khác nhau, chúng ta có thể tạo các tệp riêng biệt cho đầu trang và chân trang và sau đó bao gồm chúng trong các tệp khác.

Tạo tệp `header.php` và `footer.php`

```html
<!-- header.php -->
<!DOCTYPE html>
<html>
    <head>
        <title>Trang chủ</title>
    </head>
    <body>
        <header>Đây là vùng tiêu đề</header>
    </body>
</html>
```

```html
<!-- footer.php -->
    <footer>Đây là khu vực chân trang</footer>
</body>
</html>
```

Bao gồm các tệp này trong tệp chính

```php
<!-- index.php -->
<?php include 'header.php'; ?>

<!-- Nội dung trang -->

<?php include 'footer.php'; ?>
```

## 3. Sử dụng WordPress để quản lý đầu trang và chân trang

Trong WordPress, bạn có thể sử dụng các hàm get_header() và get_footer() để bao gồm các tệp đầu trang và chân trang.

Tạo tệp `header.php` và `footer.php` trong thư mục chủ đề của bạn

```html
<!-- header.php -->
<!DOCTYPE html>
<html>
    <head>
        <title>Trang chủ</title>
        <?php wp_head(); ?>
    </head>
    <body>
        <header>Đây là vùng tiêu đề</header>
    </body>
</html>
```

```html
<!-- footer.php -->
    <footer>Đây là khu vực chân trang</footer>
    <?php wp_footer(); ?>
</body>
</html>
```

Bao gồm các tệp này trong tệp chính

```php
<!-- index.php -->
<?php get_header(); ?>

<!-- Nội dung trang -->

<?php get_footer(); ?>
```

## Bài tập

Tạo một tệp `header.php` và `footer.php` trong thư mục chủ đề của bạn.
Bao gồm các tệp này trong tệp `index.php` của bạn bằng cách sử dụng các hàm `get_header()` và `get_footer()`.

## Hướng dẫn cách làm

Tạo tệp `header.php` và `footer.php`:

Mở thư mục chủ đề của bạn.
Tạo tệp `header.php` và thêm mã HTML cho phần đầu trang.
Tạo tệp `footer.php` và thêm mã HTML cho phần chân trang.
Bao gồm các tệp này trong tệp `index.php`:

Mở tệp `index.php` trong thư mục chủ đề của bạn.
Thêm các hàm `get_header()` và `get_footer()` vào các vị trí thích hợp trong tệp `index.php`.
Chúc các bạn thành công!

## Tổng kết

Trong bài học này, chúng ta đã học cách thiết lập đầu trang và chân trang toàn cục cho trang web của mình. Chúng ta đã thấy cách làm điều này bằng cách sử dụng HTML cơ bản, PHP và WordPress. Điều này giúp chúng ta dễ dàng quản lý và cập nhật các phần chung của trang web.

---
id: vong-lap-while-wordpress
title: Vòng lặp "while" trong WordPress
sidebar_position: 5
---

# Vòng lặp "while" trong WordPress

Chào mừng bạn đã trở lại!

Trong bài học này chúng ta sẽ tìm hiểu về vòng lặp nổi tiếng trong WordPress.

## Mục lục

1. [Mục tiêu](#mục-tiêu)
2. [Bước 1: Tạo nhiều bài đăng blog](#bước-1-tạo-nhiều-bài-đăng-blog)
3. [Bước 2: Tạo vòng lặp trong PHP](#bước-2-tạo-vòng-lặp-trong-php)
4. [Bước 3: Tạo liên kết cho tiêu đề bài đăng](#bước-3-tạo-liên-kết-cho-tiêu-đề-bài-đăng)
5. [Bài tập](#bài-tập)
6. [Tổng kết](#tổng-kết)

## Mục tiêu

-   Xuất các bài đăng blog gần đây nhất trên trang chủ của trang web.

## Bước 1: Tạo nhiều bài đăng blog

1. Truy cập bảng điều khiển quản trị WordPress.
2. Từ thanh bên, nhấp vào "Bài viết".
3. Tạo một vài bài đăng giả để có nhiều bài đăng để làm việc:
    - Tiêu đề: "Bài kiểm tra"
    - Nội dung: Một chút văn bản giả hoặc Lorem ipsum
    - Nhấp vào "Xuất bản"
4. Tạo thêm ít nhất một bài đăng giả nữa:
    - Tiêu đề: "Bài đăng thử nghiệm thứ hai"
    - Nội dung: Một chút văn bản giả
    - Nhấp vào "Xuất bản"

## Bước 2: Tạo vòng lặp trong PHP

1. Mở tệp `index.php` trong thư mục chủ đề của bạn.
2. Xóa tất cả mã kiểm tra từ bài học trước.
3. Chuyển sang chế độ PHP và tạo một vòng lặp `while`.

```php
<?php
while ( have_posts() ) {
    the_post();
    ?>
    <h2><?php the_title(); ?></h2>
    <?php the_content(); ?>
    <hr>
    <?php
}
?>
```

-   Lưu tệp và làm mới trang web của bạn để thấy các bài đăng blog được xuất ra.

## Bước 3: Tạo liên kết cho tiêu đề bài đăng

-   Chuyển các tiêu đề thành liên kết.

```php
<?php
while ( have_posts() ) {
    the_post();
    ?>
    <h2><a href="<?php the_permalink(); ?>"><?php the_title(); ?></a></h2>
    <?php the_content(); ?>
    <hr>
    <?php
}
?>
```

-   Lưu tệp và làm mới trang web của bạn để thấy các tiêu đề là các liên kết.

### Bước 4: Tạo tệp single.php

-   Tạo một tệp mới trong thư mục chủ đề của bạn và đặt tên là single.php.
-   Sao chép nội dung từ `index.php` và dán vào `single.php`.
-   Xóa các thẻ <a> bao quanh tiêu đề </a>.

```php
<?php
while ( have_posts() ) {
    the_post();
    ?>
    <h2><?php the_title(); ?></h2>
    <?php the_content(); ?>
    <?php
}
?>
```

-   Lưu tệp và làm mới trang web của bạn để thấy tiêu đề không còn là liên kết khi ở trang chi tiết.

### Bước 5: Tạo tệp page.php

-   Tạo một tệp mới trong thư mục chủ đề của bạn và đặt tên là page.php.
-   Sao chép nội dung từ single.php và dán vào page.php.
-   Thêm một tiêu đề để phân biệt trang và bài đăng.

```php
<?php
while ( have_posts() ) {
    the_post();
    ?>
    <h1>Đây là một trang, không phải một bài đăng</h1>
    <h2><?php the_title(); ?></h2>
    <?php the_content(); ?>
    <?php
}
?>
```

-   Lưu tệp và làm mới trang web của bạn để thấy sự khác biệt khi truy cập trang.

### Kết luận

-   Tùy thuộc vào URL bạn truy cập, WordPress sẽ sử dụng các tệp khác nhau trong thư mục chủ đề của bạn để kiểm soát những gì bạn thấy trên màn hình.
-   Vòng lặp là trung tâm và linh hồn của WordPress và nó là thứ mà chúng tôi sẽ sử dụng lại nhiều lần trong suốt khóa học này.

Trong bài học tiếp theo, chúng ta sẽ học cách tạo một header và footer toàn cục hoặc phổ quát. Hãy tiếp tục học tập và tôi sẽ gặp bạn sau đó.

## Bài tập

1. **Tạo tệp archive.php**:

    - Tạo một tệp mới trong thư mục chủ đề của bạn và đặt tên là `archive.php`.
    - Sao chép nội dung từ `index.php` và dán vào `archive.php`.
    - Thêm một tiêu đề để phân biệt trang lưu trữ và trang chủ.

    ```php

    <?php
    while ( have_posts() ) {
        the_post();
        ?>
        <h1>Đây là trang lưu trữ</h1>
        <h2><?php the_title(); ?></h2>
        <?php the_content(); ?>
        <?php
    }
    ?>

    ```

2. **Tạo tệp category.php**:

    - Tạo một tệp mới trong thư mục chủ đề của bạn và đặt tên là `category.php`.
    - Sao chép nội dung từ `index.php` và dán vào `category.php`.
    - Thêm một tiêu đề để phân biệt trang danh mục và trang chủ.

    ```php
    <?php
    while ( have_posts() ) {
        the_post();
        ?>
        <h1>Đây là trang danh mục</h1>
        <h2><?php the_title(); ?></h2>
        <?php the_content(); ?>
        <?php
    }
    ?>
    ```

3. **Tạo tệp tag.php**:

    - Tạo một tệp mới trong thư mục chủ đề của bạn và đặt tên là `tag.php`.
    - Sao chép nội dung từ `index.php` và dán vào `tag.php`.
    - Thêm một tiêu đề để phân biệt trang thẻ và trang chủ.

    ```php
    <?php
    while ( have_posts() ) {
        the_post();
        ?>
        <h1>Đây là trang thẻ</h1>
        <h2><?php the_title(); ?></h2>
        <?php the_content(); ?>
        <?php
    }
    ?>
    ```

Chúc các bạn học vui vẻ và thành công!

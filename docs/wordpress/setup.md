---
id: setup
title: Cài đặt
sidebar_position: 2
---

# Hướng dẫn tạo theme WordPress từ đầu

Hôm nay, chúng ta sẽ cùng nhau bắt tay vào một hành trình thú vị: tạo ra một theme WordPress của riêng mình. Không cần chần chừ nữa, hãy cùng bắt đầu ngay thôi!

1. [Thiết lập môi trường phát triển](#1-thiết-lập-môi-trường-phát-triển)
2. [Tạo thư mục theme](#2-tạo-thư-mục-theme)
3. [Tạo file `style.css`](#3-tạo-file-stylecss)
4. [Tạo file `index.php`](#4-tạo-file-indexphp)
5. [Kích hoạt theme của bạn](#5-kích-hoạt-theme-của-bạn)
6. [Tạo các file template bổ sung](#6-tạo-các-file-template-bổ-sung)
7. [Thêm file `functions.php`](#7-thêm-file-functionsphp)
8. [Tùy chỉnh và mở rộng](#8-tùy-chỉnh-và-mở-rộng)
9. [Kiểm tra theme của bạn](#9-kiểm-tra-theme-của-bạn)
10. [Bài Tập](#bài-tập)
11. [Tổng kết](#tổng-kết)

## 1. Thiết lập môi trường phát triển

-   Trong trình duyệt web của bạn, hãy truy cập trang chủ của bản sao WordPress trong môi trường nhà phát triển cục bộ của bạn.
-   Truy cập bảng điều khiển quản trị của trang web của bạn bằng cách thêm `/wp-admin` vào cuối tên miền của bạn và đăng nhập.

## 2. Tạo thư mục theme

-   Điều hướng đến `wp-content/themes/` trong thư mục cài đặt WordPress của bạn.
-   Tạo một thư mục mới cho theme của bạn, ví dụ: `webops-agency`.

## 3. Tạo file `style.css`

-   Trong thư mục theme của bạn, tạo một file tên là `style.css`.
-   Thêm thông tin tiêu đề sau vào `style.css`:

```css
/*
Theme Name: Fictional University Theme
Theme URI: http://webopsagency.com
Author: Your Name
Author URI:  http://webopsagency.com
Description: A custom WordPress theme.
Version: 1.0
Text Domain: webops-agency
*/
```

## 4. Tạo file index.php

Tạo một file tên là index.php trong thư mục theme của bạn.
Thêm cấu trúc HTML cơ bản:

```php
<!DOCTYPE html>
<html <?php language_attributes(); ?>>
<head>
    <meta charset="<?php bloginfo('charset'); ?>">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title><?php bloginfo('name'); ?></title>
    <link rel="stylesheet" href="<?php bloginfo('stylesheet_url'); ?>">
    <?php wp_head(); ?>
</head>
<body <?php body_class(); ?>>
    <header>
        <h1><?php bloginfo('name'); ?></h1>
        <p><?php bloginfo('description'); ?></p>
    </header>
    <main>
        <?php
        if ( have_posts() ) :
            while ( have_posts() ) : the_post();
                the_title('<h2>', '</h2>');
                the_content();
            endwhile;
        else :
            echo '<p>No content found</p>';
        endif;
        ?>
    </main>
    <footer>
        <p>&copy; <?php echo date('Y'); ?> <?php bloginfo('name'); ?></p>
    </footer>
    <?php wp_footer(); ?>
</body>
</html>
```

## 5. Kích hoạt theme của bạn

-   Đi đến bảng điều khiển quản trị WordPress.
-   Điều hướng đến `Giao diện > Giao diện`.
-   Tìm theme của bạn và nhấp vào `Kích hoạt`.

## 6. Tạo các file template bổ sung

-   Tạo `header.php`, `footer.php`, và `sidebar.php` cho các template module.
-   Bao gồm chúng trong `index.php` bằng cách sử dụng các hàm `get_header()`, `get_footer()`, và `get_sidebar()`.

## 7. Thêm file Functions

-   Tạo một file `functions.php` trong thư mục theme của bạn.
-   Thêm hỗ trợ theme và enqueue styles/scripts:

```php
<?php
function fictional_university_theme_setup() {
    add_theme_support('title-tag');
    add_theme_support('post-thumbnails');
    register_nav_menus(array(
    'primary' => \_\_('Primary Menu', 'webops-agency'),
    ));
}
add_action('after_setup_theme', 'fictional_university_theme_setup');

function fictional_university_theme_scripts() {
    wp_enqueue_style('main-styles', get_stylesheet_uri());
}
add_action('wp_enqueue_scripts', 'fictional_university_theme_scripts');
?>
```

## 8. Tùy chỉnh và mở rộng

-   Thêm các style tùy chỉnh vào `style.css`.
-   Tạo các template bổ sung như `single.php`, `page.php`, `archive.php`, v.v.
-   Sử dụng các hook và filter của WordPress để mở rộng chức năng.

## 9. Kiểm tra theme của bạn

-   Kiểm tra tính đáp ứng và khả năng tương thích trình duyệt.
-   Xác thực HTML và CSS.
-   Đảm bảo tất cả các tính năng của WordPress hoạt động như mong đợi.

## Bài Tập

### Bài Tập 1: Thêm Một Thông Điệp Chào Mừng

Tạo một thông điệp chào mừng đơn giản hiển thị ở đầu trang chủ của bạn.

**_Hướng Dẫn Cách Làm_**

1. Mở File index.php: Mở file `index.php` trong thư mục theme của bạn.
2. Thêm Thông Điệp Chào Mừng: Thêm đoạn mã sau vào đầu phần `<main>` để hiển thị thông điệp chào mừng.

```php
<main>
    <h2>Chào mừng bạn đến với trang web của chúng tôi!</h2>
    <?php
    if ( have_posts() ) :
        while ( have_posts() ) : the_post();
            the_title('<h2>', '</h2>');
            the_content();
        endwhile;
    else :
        echo '<p>No content found</p>';
    endif;
    ?>
</main>
```

3. Lưu File: Lưu file `index.php` và làm mới trang web của bạn để xem thông điệp chào mừng.

### Bài Tập 2: Thêm Một Menu Điều Hướng

Tạo một menu điều hướng đơn giản hiển thị ở đầu trang.

**_Hướng Dẫn Cách Làm_**

Mở file `header.php` trong thư mục theme của bạn.
Thêm Menu Điều Hướng: Thêm đoạn mã sau vào file `header.php` để hiển thị menu điều hướng.

## Tổng kết

Chúc mừng bạn! Bạn đã hoàn thành việc tạo một theme WordPress cơ bản từ đầu. Bây giờ bạn đã có một nền tảng vững chắc để tiếp tục tùy chỉnh và mở rộng theme của mình. Hãy tiếp tục khám phá và sáng tạo với WordPress nhé!

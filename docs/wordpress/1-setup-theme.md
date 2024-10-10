---
id: cai-dat-theme
title: Cài đặt theme
sidebar_position: 2
---

# Hướng dẫn tạo một theme WordPress từ đầu

Hôm nay, chúng ta sẽ cùng nhau bắt tay vào một hành trình thú vị: tạo ra một theme WordPress của riêng mình. Không cần chần chừ nữa, hãy cùng bắt đầu ngay thôi!

1. [Mục tiêu](#mục-tiêu)
2. [Thiết lập môi trường phát triển](#1-thiết-lập-môi-trường-phát-triển)
3. [Tạo theme cơ bản](#2-tạo-theme-cơ-bản)
    - [Tạo thư mục theme](#tạo-thư-mục-theme)
    - [Tạo file `style.css`](#tạo-file-stylecss)
    - [Tạo file `index.php`](#tạo-file-indexphp)
4. [Bài tập](#bài-tập)
5. [Tổng kết](#tổng-kết)

## 1. Thiết lập môi trường phát triển

-   Trong trình duyệt web của bạn, hãy truy cập trang chủ của bản sao WordPress trong môi trường nhà phát triển cục bộ của bạn.
-   Truy cập bảng điều khiển quản trị của trang web của bạn bằng cách thêm `/wp-admin` vào cuối tên miền của bạn và đăng nhập.

## 2. Tạo theme cơ bản

### Bước 1: Tạo thư mục theme

-   Điều hướng đến `wp-content/themes/` trong thư mục cài đặt WordPress của bạn.
-   Tạo một thư mục mới cho theme của bạn, ví dụ: `fictional-university-theme`.

### Bước 2: Tạo file `style.css`

Trong quá trình tạo một theme WordPress, file `style.css` đóng vai trò rất quan trọng. Đây là nơi bạn sẽ định nghĩa các kiểu dáng (CSS) cho theme của mình. Ngoài ra, file này cũng chứa thông tin tiêu đề của theme, giúp WordPress nhận diện và hiển thị thông tin về theme trong bảng điều khiển quản trị.

-   Trong thư mục theme của bạn (ví dụ: `wp-content/themes/webopsagency`), tạo một file mới tên là `style.css`.
-   Thêm thông tin tiêu đề sau vào `style.css`. Đây là thông tin tiêu đề của theme, giúp WordPress nhận diện và hiển thị thông tin về theme.

```css
/*
Theme Name: Fictional University Theme
Theme URI: http://example.com/fictional-university-theme
Author: Your Name
Author URI: http://example.com
Description: A custom WordPress theme.
Version: 1.0
License: GNU General Public License v2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html
Text Domain: fictional-university-theme
*/
```

:::tip Giải thích các dòng trong thông tin:

-   Theme Name: Tên của theme. Đây là tên sẽ hiển thị trong bảng điều khiển quản trị WordPress.
-   Theme URI: Đường dẫn URL đến trang web của theme. Đây có thể là trang web chính thức của theme hoặc trang giới thiệu.
-   Author: Tên tác giả của theme. Đây là tên của bạn hoặc nhóm phát triển theme.
-   Author URI: Đường dẫn URL đến trang web của tác giả. Đây có thể là trang web cá nhân hoặc trang web của nhóm phát triển.
-   Description: Mô tả ngắn gọn về theme. Đây là mô tả sẽ hiển thị trong bảng điều khiển quản trị WordPress.
-   Version: Phiên bản của theme. Đây là số phiên bản của theme, giúp bạn quản lý các bản cập nhật.
-   License: Giấy phép của theme. Đây là loại giấy phép mà theme được phát hành dưới đó.
-   License URI: Đường dẫn URL đến văn bản giấy phép. Đây là đường dẫn đến văn bản chi tiết của giấy phép.
-   Text Domain: Miền văn bản của theme. Đây là một định danh duy nhất cho theme, giúp WordPress quản lý các bản dịch.

:::

### Bước 3: Tạo file `index.php`

-   Tạo một file tên là `index.php` trong thư mục theme của bạn.
-   Thêm cấu trúc HTML cơ bản:

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

## 3. Kích hoạt theme của bạn

-   Đi đến bảng điều khiển quản trị WordPress.
-   Điều hướng đến `Giao diện > Giao diện`.
-   Tìm theme của bạn và nhấp vào `Kích hoạt`.

## 4. Tạo các file template bổ sung

-   Tạo `header.php`, `footer.php`, và `sidebar.php` cho các template module.
-   Bao gồm chúng trong `index.php` bằng cách sử dụng các hàm `get_header()`, `get_footer()`, và `get_sidebar()`.

## 5. Thêm file Functions

Trong WordPress, bạn có thể thêm các tính năng hỗ trợ cho theme của mình và tải các tệp style và script cần thiết bằng cách sử dụng file `functions.php`. Dưới đây là cách thực hiện:

1. **Thêm hỗ trợ cho theme**: Bạn có thể thêm các tính năng hỗ trợ như tiêu đề trang, hình ảnh đại diện, và menu điều hướng.

2. **Tải các tệp style và script**: Bạn có thể sử dụng hàm `wp_enqueue_style` và `wp_enqueue_script` để tải các tệp CSS và JavaScript cần thiết cho theme của bạn.

Ví dụ:

```php
<?php
// Thêm hỗ trợ cho theme
function fictional_university_theme_setup() {
    add_theme_support('title-tag'); // Hỗ trợ tiêu đề trang
    add_theme_support('post-thumbnails'); // Hỗ trợ hình ảnh đại diện
    register_nav_menus(array(
        'primary' => __('Primary Menu', 'fictional-university-theme'), // Đăng ký menu điều hướng chính
    ));
}
add_action('after_setup_theme', 'fictional_university_theme_setup');

// Tải các tệp style và script
function fictional_university_theme_scripts() {
    wp_enqueue_style('main-styles', get_stylesheet_uri()); // Tải tệp style chính
}
add_action('wp_enqueue_scripts', 'fictional_university_theme_scripts');
?>
```

## 6. Tùy chỉnh và mở rộng

-   Thêm các style tùy chỉnh vào `style.css`.
-   Tạo các template bổ sung như `single.php`, `page.php`, `archive.php`, v.v.
-   Sử dụng các hook và filter của WordPress để mở rộng chức năng.

## 7. Kiểm tra theme của bạn

-   Kiểm tra tính đáp ứng và khả năng tương thích trình duyệt.
-   Xác thực HTML và CSS.
-   Đảm bảo tất cả các tính năng của WordPress hoạt động như mong đợi.

## Bài Tập

### Bài Tập 1: Thêm Một Thông Điệp Chào Mừng

Tạo một thông điệp chào mừng đơn giản hiển thị ở đầu trang chủ của bạn.

**_Hướng Dẫn Cách Làm_**

1. Mở File `index.php`: Mở file `index.php` trong thư mục theme của bạn.
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

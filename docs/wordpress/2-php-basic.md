---
id: php-co-ban
title: Ôn tập PHP Cơ Bản
sidebar_position: 3
---

# Hướng dẫn tạo và sử dụng hàm trong PHP

Chào mừng bạn đã trở lại!

Trong bài học này, chúng ta sẽ trả lời câu hỏi hàm là gì?

Thay vì cố gắng giải thích hàm là gì, hãy để tôi cho bạn thấy một cách trực quan hàm là gì.

1. [Giới thiệu về hàm](#giới-thiệu-về-hàm)
2. [Bước 1: Tạo hàm đầu tiên](#bước-1-tạo-hàm-đầu-tiên)
3. [Bước 2: Gọi hàm](#bước-2-gọi-hàm)
4. [Bước 3: Sử dụng hàm nhiều lần](#bước-3-sử-dụng-hàm-nhiều-lần)
5. [Bước 4: Thay đổi nội dung hàm](#bước-4-thay-đổi-nội-dung-hàm)
6. [Bước 5: Tạo hàm với tham số](#bước-5-tạo-hàm-với-tham-số)
7. [Bài tập](#bài-tập)
8. [Tổng kết](#tổng-kết)

## 1: Mở tệp PHP chỉ mục

-   Mở trình soạn thảo văn bản của bạn và mở tệp `index.php` nằm trong thư mục chủ đề của bạn.

## 2: Viết mã PHP

-   Xóa dòng văn bản mẫu và nhập vào chế độ PHP bằng cách sử dụng `<?php và ?>`. Đây là cách chúng ta bắt đầu viết mã PHP.

```php
<?php
// Bạn có thể tự do viết mã PHP ở giữa hai thẻ này.
?>

```

## 3: Thực hiện phép toán đơn giản

-   Thử lặp lại một bài toán đơn giản để làm quen với PHP. Hãy bắt đầu với phép cộng cơ bản.

```php
<?php
echo 2 + 2;
?>

```

-   Lưu tệp và làm mới trang web của bạn để thấy kết quả "4". Thật tuyệt vời phải không nào?

## 4: Tạo hàm đầu tiên

-   Xóa dòng mã trên và tạo một hàm đầu tiên của riêng bạn. Hãy cùng tạo ra một hàm đơn giản.

```php

<?php
function my_first_function() {
    echo 2 + 2;
}
?>

```

-   Lưu tệp và làm mới trang web của bạn. Bạn sẽ không thấy gì cả vì đây chỉ là định nghĩa hàm. Đừng lo, chúng ta sẽ gọi nó ngay bây giờ!

## 5: Gọi hàm

-   Để thực sự chạy hàm, bạn cần gọi nó. Hãy thêm dòng mã sau vào cuối tệp của bạn.

```php
<?php
function my_first_function() {
    echo 2 + 2;
}

my_first_function();
?>

```

-   Lưu tệp và làm mới trang web của bạn. Bùm! Bạn sẽ thấy kết quả "4" xuất hiện trên màn hình. Chúng ta đã thành công!

## 6: Sử dụng hàm nhiều lần

-   Bạn có thể gọi hàm nhiều lần.

```php
<?php
function my_first_function() {
    echo 2 + 2;
}

my_first_function();
my_first_function();
?>
```

-   Lưu tệp và làm mới trang web của bạn để thấy kết quả "44".

## 7: Thay đổi nội dung hàm

-   Thay vì echo phép toán, hãy echo một chuỗi văn bản.

```php
<?php
function my_first_function() {
    echo "<p>Xin chào, đây là hàm đầu tiên của tôi</p>";
}

my_first_function();
my_first_function();
?>

```

-   Lưu tệp và làm mới trang web của bạn để thấy kết quả.

## 8: Tạo hàm với tham số

-   Tạo một hàm mới với tham số.

```php
<?php
function greeting($name, $color) {
    echo "<p>Xin chào, tên tôi là $name và màu yêu thích của tôi là $color.</p>";
}

greeting("John", "xanh lam");
greeting("Jane", "xanh lá cây");
?>
```

-   Lưu tệp và làm mới trang web của bạn để thấy kết quả.

## 9: Sử dụng hàm WordPress

-   Sử dụng các hàm có sẵn của WordPress để lấy thông tin trang web.

```php

<!DOCTYPE html>
<html <?php language_attributes(); ?>>
<head>
    <meta charset="<?php bloginfo('charset'); ?>">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title><?php bloginfo('name'); ?></title>
    <link rel="stylesheet" href="<?php bloginfo('stylesheet_url'); ?>" />
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

-   Lưu tệp và làm mới trang web của bạn để thấy kết quả.

## Bài tập

1. Tạo một hàm mới có tên là `multiply` nhận hai tham số và trả về tích của chúng.
2. Tạo một hàm mới có tên là `greet` nhận một tham số là tên và trả về một chuỗi chào mừng.
3. Tạo một hàm mới có tên là `calculate_area` nhận hai tham số là chiều dài và chiều rộng, và trả về diện tích của hình chữ nhật.

### Hướng dẫn cách làm

1. **Tạo hàm `multiply`**:

    - Mở tệp `index.php`.
    - Tạo hàm `multiply` nhận hai tham số và trả về tích của chúng.

    ```php
    <?php
    function multiply($a, $b) {
        return $a * $b;
    }

    echo multiply(3, 4); // Kết quả: 12
    ?>
    ```

2. **Tạo hàm `greet`**:

    - Mở tệp `index.php`.
    - Tạo hàm `greet` nhận một tham số là tên và trả về một chuỗi chào mừng.

    ```php
    <?php
    function greet($name) {
        return "Xin chào, " . $name . "!";
    }

    echo greet("John"); // Kết quả: Xin chào, John!
    ?>
    ```

3. **Tạo hàm `calculate_area`**:

    - Mở tệp `index.php`.
    - Tạo hàm `calculate_area` nhận hai tham số là chiều dài và chiều rộng, và trả về diện tích của hình chữ nhật.

    ```php
    <?php
    function calculate_area($length, $width) {
        return $length * $width;
    }

    echo calculate_area(5, 10); // Kết quả: 50
    ?>
    ```

Chúc các bạn thành công!

## Tổng kết

Chúc mừng bạn! Bạn đã biết cách tạo và sử dụng hàm trong PHP. Hãy tiếp tục khám phá và sáng tạo với PHP nhé!

Trong bài học tiếp theo, chúng ta sẽ cùng nhau tìm hiểu về mảng trong PHP. Hãy sẵn sàng cho những điều thú vị tiếp theo!

Chúc bạn có một ngày tuyệt vời và đầy sáng tạo! 🎉

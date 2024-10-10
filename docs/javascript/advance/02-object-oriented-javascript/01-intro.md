---
id: lam-viec-voi-cac-doi-tuong-javascript-thuan-tuy
title: Làm việc với các đối tượng JavaScript thuần túy
sidebar_position: 1
---

# Sử Dụng Live Server Trong VS Code

## Giới Thiệu Về Bài Giảng

Chào mừng các bạn đến với bài giảng về cách sử dụng Live Server trong `Visual Studio Code (VS Code)`! Tôi là Đạt, và tôi sẽ là người hướng dẫn các bạn trong hành trình khám phá cách thiết lập môi trường lập trình hiệu quả với `Live Server`. Mục tiêu của bài giảng này là giúp bạn nắm vững cách sử dụng Live Server để phát triển và kiểm tra mã JavaScript một cách nhanh chóng và tiện lợi.

## Mục Lục

1. [Giới Thiệu Về Môi Trường Lập Trình](#giới-thiệu-về-môi-trường-lập-trình)
2. [Cài Đặt Live Server](#cài-đặt-live-server)
3. [Sử Dụng Live Server](#sử-dụng-live-server)
    - [Tạo File HTML và JavaScript](#tạo-file-html-và-javascript)
    - [Mở File Với Live Server](#mở-file-với-live-server)
    - [Kiểm Tra Kết Quả Trong Trình Duyệt](#kiểm-tra-kết-quả-trong-trình-duyệt)
4. [Tổng Kết](#tổng-kết)
5. [Bài Tập Thực Hành](#bài-tập-thực-hành)

## Giới Thiệu Về Môi Trường Lập Trình

Trong khóa học này, tôi sử dụng VS Code, một trình soạn thảo mã nguồn miễn phí và mạnh mẽ. Bạn có thể sử dụng bất kỳ trình soạn thảo nào mà bạn cảm thấy thoải mái, nhưng tôi khuyến khích sử dụng VS Code vì tính năng `Live Server` rất tiện lợi.

### Cài Đặt Theme

Tôi sử dụng theme `"Material Theme, Pale Knight, High Contrast"` trong VS Code. Bạn có thể cài đặt theme này bằng cách vào phần Extensions và tìm kiếm `"Material Theme"`.

### Live Server

Một tính năng quan trọng mà tôi sử dụng là Live Server, một extension cho phép bạn mở file HTML với một server trực tiếp, giúp tự động tải lại trang khi bạn lưu thay đổi.

## Cài Đặt Live Server

Để cài đặt Live Server, bạn làm theo các bước sau:

1. Mở VS Code.
2. Vào phần Extensions (biểu tượng hình vuông ở thanh bên trái).
3. Tìm kiếm "Live Server".
4. Nhấn vào nút "Install" để cài đặt.

## Sử Dụng Live Server

### Tạo File HTML và JavaScript

Đầu tiên, bạn cần tạo một file HTML và một file JavaScript. Ví dụ:

```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>Live Server Demo</title>
    </head>
    <body>
        <script src="app.js"></script>
    </body>
</html>
```

```javascript
// app.js
console.log("Hello, world!");
```

### Mở File Với Live Server

Để mở file với Live Server, bạn làm theo các bước sau:

1. Nhấp chuột phải vào file index.html.
2. Chọn "Open with Live Server".
3. Trình duyệt sẽ tự động mở và hiển thị nội dung của file HTML.

Hoặc bạn có thể sử dụng Command Palette (Cmd+Shift+P trên Mac hoặc Ctrl+Shift+P trên Windows/Linux) và gõ "Open with Live Server".

### Kiểm Tra Kết Quả Trong Trình Duyệt

Khi bạn mở file với Live Server, trình duyệt sẽ tự động mở và hiển thị nội dung của file HTML. Mỗi khi bạn lưu thay đổi trong file HTML hoặc JavaScript, trang web sẽ tự động tải lại để hiển thị thay đổi mới nhất.

Ví dụ, nếu bạn thay đổi mã JavaScript thành:

```javascript
// app.js
console.log("1 + 1 =", 1 + 1);
```

Trình duyệt sẽ tự động tải lại và hiển thị kết quả mới trong console.

## Tổng Kết

Live Server là một công cụ mạnh mẽ và tiện lợi giúp bạn phát triển và kiểm tra mã JavaScript một cách nhanh chóng. Bằng cách sử dụng Live Server, bạn có thể tiết kiệm thời gian và tăng hiệu quả làm việc.

## Bài Tập Thực Hành

### Bài Tập

1. Tạo một file HTML và một file JavaScript.
2. Sử dụng Live Server để mở file HTML.
3. Thêm một đoạn mã JavaScript để hiển thị một thông báo trong console.
4. Thay đổi đoạn mã JavaScript và kiểm tra kết quả trong trình duyệt.

### Hướng Dẫn Cách Làm

Tạo File HTML và JavaScript:

# Hướng dẫn cài đặt

## Yêu cầu:

- Git, PHP 7.4, MySQL, Composer, Nodejs

## Cài đặt

Bật terminal và trỏ vào thư mục cần tải, sau đó chạy lệnh `git clone` để tải source code về:

```bash
git clone https://github.com/phuong-w/injected-eshop.git injected-eshop
```

_**injected-eshop** là tên thư mục sẽ chứa các file và thư mục của source code_

Sau khi tải về xong, trỏ vào thư mục source code:

```bash
cd injected-eshop
```

Sử dụng **composer** và **npm** để chạy 2lệnh sau để tải các thư viện PHP và Javascript:

```bash
composer install --optimize-autoloader --no-dev
npm install
```

Quá trình tải thư viện có thể mất tới 1p. Sau khi chạy xong thì quá trình cài đặt đã xong 50%.

## Thiết lập

Mở ứng dụng quản lý database của bạn, tạo schema tên `injected_eshop` vào `database/e-shop.sql` lấy file này import vào schema.

Sao chép tệp `.env.example` và đổi tên thành `.env`. Cấu hình thông tin cơ bản trong tệp `.env`

Cấu hình database:

```bash
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=injected_eshop
DB_USERNAME=root
DB_PASSWORD=
```
Sau đó chạy lệnh sau để tạo `key` cho ứng dụng:

```bash
php artisan key:generate
```

Tới bước này, có vẻ bạn thắc mắc là tại sao không có file sql để import vào database? Bạn không cần phải import gì cả, chỉ cần chạy lệnh sau để nó tự tạo dữ liệu ra cho bạn:

```bash
php artisan migrate --seed
```

Bây giờ trang web của bạn đã hoạt động, nhưng vẫn trang có các tệp `css`, `js`, và `images` cho trang web. Để tạo chạy lệnh sau:

```
npm run production
```

Và thế là xong, quá trình cài đặt và thiết lập đã hoàn tất. Bây giờ bạn đã có thể sử dụng trang web được.

Tài khoản và mật khẩu mặc định là: 
- Tài khoản admin: **admin@gmail.com** / **1111**
- Tài khoản user: **user@gmail.com** / **1111**

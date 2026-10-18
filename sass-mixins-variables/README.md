# Thực hành SASS Variables & Mixins

Dự án chuyển các quy tắc CSS lặp lại thành biến, mixins và các partial SCSS để dễ tái sử dụng, bảo trì.

## Cấu trúc thư mục

```text
sass-mixins-variables/
├── index.html
├── package.json
├── scss/
│   ├── main.scss
│   ├── abstracts/
│   │   ├── _variables.scss
│   │   └── _mixins.scss
│   ├── base/
│   │   └── _typography.scss
│   └── components/
│       ├── _buttons.scss
│       └── _cards.scss
└── css/
    └── styles.css
```

## Chạy thử

Cần cài Node.js và npm trước. Tại terminal trong thư mục dự án, chạy:

```bash
npm install
npm run build
```

Để Sass tự biên dịch khi SCSS thay đổi:

```bash
npm run watch
```

Sau đó mở `index.html` bằng trình duyệt.

## Vai trò các file

- `abstracts/_variables.scss`: giá trị dùng chung như màu sắc, kích thước chữ, padding và box-shadow.
- `abstracts/_mixins.scss`: `button-style($bg-color)` nhận màu làm tham số và `box-style` gom các thuộc tính thẻ.
- `base/_typography.scss`: kiểu chữ chung cho body, h1, h2 và đoạn văn.
- `components/_buttons.scss`: áp dụng mixin cho nút.
- `components/_cards.scss`: áp dụng mixin cho thẻ; có ví dụ nesting với `&:hover` và `h3`.
- `main.scss`: tập hợp các module thông qua cú pháp Sass hiện đại `@use`.
- `css/styles.css`: CSS đầu ra để xem trang ngay, không cần cài Sass trước.

## Lưu ý

Dùng `@use` thay cho `@import` vì `@import` của Sass đã bị đánh dấu lỗi thời. Dự án demo dùng màu đỏ và các giá trị tương tự đề bài; có thêm bố cục và trạng thái hover để dễ quan sát hiệu quả của mixin. CSS đầu ra được cung cấp sẵn; chạy `npm run build` để tạo lại CSS từ SCSS trên máy của bạn.

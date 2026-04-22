Phần 1: Phân tích
1. Hibernate là một ORM, nó cần biết loại cơ sở dữ liệu đang sử dụng (MySQL, PostgreSQL, Oracle…) để:
    Sinh câu lệnh SQL đúng chuẩn của từng hệ quản trị
    Ánh xạ kiểu dữ liệu Java sang kiểu dữ liệu trong database
    Xử lý các cú pháp đặc thù như LIMIT, JOIN, AUTO_INCREMENT,...

- Thuộc tính hibernate.dialect chính là nơi khai báo thông tin này.
- Nếu không cấu hình:
    Hibernate không biết phải tạo SQL theo chuẩn nào
    Không thể generate câu lệnh phù hợp
    Dẫn đến lỗi: Hibernate Dialect must be explicitly set

2. Thuộc tính đó là: hibernate.hbm2ddl.auto
- Chức năng:
    Dựa vào các class có annotation @Entity
    Tự động tạo bảng tương ứng trong database

- Các giá trị thường dùng:
    create: Xóa bảng cũ và tạo lại từ đầu
    update: Cập nhật bảng theo entity (thêm cột nếu thiếu)
    validate: Kiểm tra mapping, không thay đổi DB
    none: Không tác động gì

Trong bài này, giá trị phù hợp là: update

Khi đó Hibernate sẽ tự tạo các bảng như:
    medicines
    prescriptions
dựa trên các class Java tương ứng.
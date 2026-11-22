# Hướng dẫn đóng góp

Cảm ơn bạn quan tâm tới dự án! Quy trình đóng góp:

1. **Fork** repo và tạo nhánh mới: `git checkout -b feature/ten-tinh-nang`.
2. Cài môi trường: `pip install -r requirements.txt`.
3. Viết code theo chuẩn PEP 8, có docstring tiếng Việt hoặc tiếng Anh.
4. Chạy lại toàn bộ pipeline để chắc chắn không lỗi:
   ```bash
   python src/analysis.py && python src/build_report.py
   ```
5. Commit với thông điệp rõ ràng (ví dụ `feat: thêm mô hình Random Forest`).
6. Tạo **Pull Request** mô tả thay đổi, kèm hình/kết quả nếu có.

## Quy tắc về dữ liệu
- Không commit dữ liệu chứa thông tin cá nhân nhạy cảm.
- Dữ liệu mới phải ghi rõ nguồn và giấy phép trong `data/README.md`.

## Báo lỗi
Mở **Issue** với: mô tả lỗi, các bước tái hiện, kết quả mong đợi, phiên bản Python/thư viện.

Khi đóng góp, bạn đồng ý rằng phần đóng góp được phát hành theo giấy phép MIT của dự án.

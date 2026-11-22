# student-performance-ml

**Phân tích và dự đoán kết quả học tập của học sinh bằng học máy.** Dự án thực hành môn *Năng lực số nâng cao*, Đại học Cần Thơ.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## Giới thiệu
Phát hiện sớm học sinh có nguy cơ không đạt giúp giáo viên can thiệp kịp thời. Dự án dùng dữ liệu công khai **UCI Student Performance** để trả lời ba câu hỏi:

1. Những yếu tố nào quyết định học sinh **Đạt / Chưa đạt**? Dùng cây quyết định.
2. Có thể chia người học thành các **nhóm hành vi** nào? Dùng K-Means.
3. Có thể **dự đoán điểm cuối kỳ** chính xác đến đâu? Dùng hồi quy tuyến tính.

## Kết quả chính
| Mô hình | Chỉ số |
|---|---|
| Cây quyết định (độ sâu 3) | Accuracy = 88,2%; đặc trưng quan trọng nhất: điểm kỳ 1 (G1) |
| K-Means (k = 3) | Cụm rủi ro có tỷ lệ đạt 45%, cụm tốt có tỷ lệ đạt 95% |
| Hồi quy tuyến tính | R² = 0,883; MAE = 0,75 điểm |

![Cây quyết định](results/figures/tree.png)

## Nội dung theo Bài thực hành 4
| Yêu cầu | Nằm ở đâu |
|---|---|
| **YC2 – Poster khoa học A0**: tóm tắt bài báo *Predicting Student Dropout and Academic Success* của V. Realinho, J. Machado, L. Baptista, M. V. Martins (Data, 2022, doi:10.3390/data7110146) | [`docs/poster/`](docs/poster/) – mã LaTeX, [PDF xem trước](docs/poster/poster-xem-truoc.pdf), script vẽ lại biểu đồ từ dữ liệu gốc |
| **YC3 – Video nhóm** (cùng nội dung với poster) | [Video MP4](docs/video/video-yc3-realinho2022.mp4), [bản Canva](https://www.canva.com/d/TNEV8yy5zFYSoUf), [kịch bản](docs/video/kich-ban-video.md) và [phụ đề](docs/video/phu-de.srt) |
| **YC4 – Bản quyền nội dung số**: repo có README, cấu trúc thư mục, LICENSE (MIT), CONTRIBUTING.md, CITATION.cff | Thư mục gốc của repo |
| **YC4 – Báo cáo so sánh 3 giấy phép** GPL (GNU Bash), MIT (React), Apache 2.0 (TensorFlow) | [`docs/license-report/`](docs/license-report/) – mã LaTeX (Overleaf) và [PDF](docs/license-report/bao-cao-so-sanh-giay-phep.pdf) |
| **YC5 – Đọc CSV → sinh báo cáo PDF** (cá nhân) | [`src/csv_to_pdf.py`](src/csv_to_pdf.py) → [`results/csv_report.pdf`](results/csv_report.pdf) |
| **YC5 – Tự động tạo slide từ file văn bản** (cá nhân) | [`src/md_to_pptx.py`](src/md_to_pptx.py) + [`docs/slides.md`](docs/slides.md) → [`results/slides.pptx`](results/slides.pptx) |
| **YC5 – Mini-project AI + Python** (nhóm): dữ liệu thực tế, làm sạch, trực quan hóa, mô hình, báo cáo PDF, dashboard | [`src/analysis.py`](src/analysis.py), [`src/build_report.py`](src/build_report.py) → [`results/bao-cao-phan-tich.pdf`](results/bao-cao-phan-tich.pdf); dashboard [`app/dashboard.py`](app/dashboard.py) |

## Cấu trúc thư mục
```
data/        dữ liệu gốc (raw) và đã xử lý (processed) – xem data/README.md
src/         mã nguồn
  analysis.py      làm sạch, trực quan hóa, huấn luyện mô hình
  build_report.py  sinh báo cáo PDF từ kết quả
  csv_to_pdf.py    CSV bất kỳ -> báo cáo PDF
  md_to_pptx.py    file .md/.txt -> slide .pptx
  pdfkit_vn.py     tiện ích PDF tiếng Việt
app/         dashboard Streamlit
docs/        nội dung thuyết trình (slides.md), báo cáo so sánh giấy phép (license-report/)
results/     hình, metrics.json, báo cáo PDF, slide
```

## Cách chạy
```bash
pip install -r requirements.txt
python src/analysis.py                      # tạo hình + metrics
python src/build_report.py                  # báo cáo PDF
python src/csv_to_pdf.py data/raw/student-mat.csv --sep ";" --target G3
python src/md_to_pptx.py docs/slides.md     # slide thuyết trình
streamlit run app/dashboard.py              # dashboard tương tác
```

## Dữ liệu và đạo đức
- Nguồn: Cortez, P. (2008). *Student Performance* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5TG7T. Giấy phép **CC BY 4.0**.
- Dữ liệu đã được ẩn danh từ nguồn, không chứa thông tin định danh cá nhân.

## Giấy phép
Mã nguồn phát hành theo giấy phép **MIT** (xem [LICENSE](LICENSE)). Dữ liệu giữ giấy phép CC BY 4.0 của tác giả gốc.

## Trích dẫn
Xem [CITATION.cff](CITATION.cff). GitHub sẽ tự hiện nút **"Cite this repository"**.

## Đóng góp
Xem [CONTRIBUTING.md](CONTRIBUTING.md).

# Ứng dụng phân loại hoa Iris

Ứng dụng web Streamlit dự đoán loài hoa Iris bằng thuật toán Gaussian Naive Bayes. Người dùng nhập bốn số đo của hoa và xem loài dự đoán, xác suất của từng loài, ảnh minh họa và vị trí mẫu trên biểu đồ.

**Repository:** [KietNH-ai/AIL_IRIS_Classification](https://github.com/KietNH-ai/AIL_IRIS_Classification)  
**Yêu cầu:** Python 3.10 trở lên.

## Tính năng

- Huấn luyện Gaussian Naive Bayes trên toàn bộ 150 mẫu Iris để dự đoán.
- Đánh giá độ chính xác riêng bằng tập kiểm tra chiếm 20%, có phân tầng và `random_state=42`.
- Nhập chiều dài, chiều rộng đài hoa và cánh hoa bằng thanh trượt; chỉ dự đoán sau khi bấm **Dự đoán ngay**.
- Hiển thị kết quả, xác suất của Setosa, Versicolor và Virginica cùng ảnh minh họa tương ứng.
- Xem bảng dữ liệu Iris và biểu đồ phân bố Petal Length/Petal Width có đánh dấu mẫu vừa nhập.

## Chạy trên máy tính Windows

Mở PowerShell tại thư mục muốn lưu dự án và chạy:

```powershell
git clone https://github.com/KietNH-ai/AIL_IRIS_Classification.git
cd AIL_IRIS_Classification
py -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m streamlit run app.py
```

Khi Streamlit khởi động, mở địa chỉ được in trong cửa sổ lệnh, thường là <http://localhost:8501>.

## Kết quả đánh giá và kiểm tra

Accuracy tham chiếu là **96.67%** trên tập kiểm tra 20%. Sau khi đánh giá, ứng dụng huấn luyện mô hình dùng để dự đoán trên toàn bộ dữ liệu Iris. Báo cáo có bốn trường hợp đầu vào, kết quả và nhận xét trường hợp gần ranh giới giữa hai loài tại [`bao_cao_kiem_thu.md`](bao_cao_kiem_thu.md).

Notebook trình bày các bước nạp dữ liệu, đánh giá mô hình, kiểm tra bốn trường hợp và chạy ứng dụng trong Google Colab: [Mở notebook trên Colab](https://colab.research.google.com/github/KietNH-ai/AIL_IRIS_Classification/blob/main/iris_streamlit_demo.ipynb).

Để lưu ảnh giao diện cho báo cáo, chạy ứng dụng, nhập lần lượt các bộ số đo trong báo cáo, bấm **Dự đoán ngay** và lưu ảnh vào `screenshots/` theo tên đã ghi trong báo cáo.

## Cấu trúc dự án

- `app.py`: giao diện Streamlit, đánh giá và huấn luyện mô hình, dự đoán và biểu đồ.
- `iris_streamlit_demo.ipynb`: notebook tiếng Việt cho Jupyter/Google Colab.
- `bao_cao_kiem_thu.md`: kết quả đánh giá, các trường hợp kiểm tra và hướng dẫn chụp ảnh.
- `requirements.txt`: các thư viện Python cần cài.
- `assets/`: ảnh minh họa ba loài hoa.
- `screenshots/`: nơi lưu ảnh giao diện kiểm thử.

## Triển khai lên Streamlit Community Cloud

Sau khi repository có mã nguồn, đăng nhập tại [share.streamlit.io](https://share.streamlit.io), chọn **Create app**, rồi cấu hình:

- Repository: `KietNH-ai/AIL_IRIS_Classification`
- Branch: `main`
- Main file path: `app.py`

Chọn **Deploy** để triển khai ứng dụng. Streamlit Community Cloud sẽ cài các thư viện khai báo trong `requirements.txt`.


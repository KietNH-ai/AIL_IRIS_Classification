# Demo Phân Loại Hoa Iris Dataset

Ứng dụng Streamlit phân loại hoa Iris bằng Gaussian Naive Bayes. Dự án gồm mã nguồn, hướng dẫn chạy và ảnh minh họa cần thiết.

## Mã nguồn dự án

Mã nguồn được lưu tại [KietNH-ai/AIL_IRIS_Classification](https://github.com/KietNH-ai/AIL_IRIS_Classification). Repository hiện chưa có bản triển khai trực tuyến.

## Chạy trên máy tính

Yêu cầu Python 3.10 trở lên. Giải nén thư mục, mở PowerShell tại thư mục dự án và chạy:

```powershell
py -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m streamlit run app.py
```

Streamlit sẽ hiện một địa chỉ cục bộ, thường là `http://localhost:8501`; mở địa chỉ đó trên trình duyệt.

## Chức năng

- Gaussian Naive Bayes được huấn luyện trên toàn bộ 150 mẫu Iris.
- Accuracy được đánh giá riêng trên tập test 20%, `random_state=42`, `stratify=y`.
- Bốn thanh trượt nhập đặc trưng; kết quả chỉ xuất hiện sau khi bấm **Dự đoán ngay**.
- Hiển thị loài được dự đoán, xác suất của ba loài và ảnh minh họa tương ứng.
- Có bảng dữ liệu Iris và biểu đồ vị trí điểm nhập mới trên phân bố cánh hoa.

## Kiểm thử

Các đầu vào mẫu, kết quả, xác suất và nhận xét ca ranh giới được ghi trong [`bao_cao_kiem_thu.md`](bao_cao_kiem_thu.md). Notebook [`iris_streamlit_demo.ipynb`](iris_streamlit_demo.ipynb) có các bước nạp dữ liệu, đánh giá, huấn luyện toàn bộ dữ liệu và kiểm tra bốn trường hợp theo đề.

Để chụp ảnh giao diện đính kèm báo cáo, chạy ứng dụng theo hướng dẫn bên trên, chọn bộ giá trị trong bảng của báo cáo, bấm **Dự đoán ngay** rồi chụp màn hình vùng gồm thông số và kết quả.

## Cấu trúc

- `app.py`: ứng dụng Streamlit, đánh giá và huấn luyện mô hình.
- `iris_streamlit_demo.ipynb`: notebook code tiếng Việt để chạy trên Colab/Jupyter.
- `bao_cao_kiem_thu.md`: kết quả kiểm thử và nhận xét.
- `requirements.txt`: thư viện cần cài.
- `assets/`: ảnh minh họa Setosa, Versicolor và Virginica.
- `screenshots/`: ảnh chụp giao diện kiểm thử để đính kèm báo cáo.

## Triển khai lên Streamlit Community Cloud

Sau khi mã nguồn đã được đẩy lên GitHub, đăng nhập tại [share.streamlit.io](https://share.streamlit.io), chọn repository `KietNH-ai/AIL_IRIS_Classification`, branch `main`, file `app.py`, rồi chọn **Deploy**.

## Nguồn

- GitHub repository: https://github.com/KietNH-ai/AIL_IRIS_Classification
- Notebook trên GitHub: https://colab.research.google.com/github/KietNH-ai/AIL_IRIS_Classification/blob/main/iris_streamlit_demo.ipynb

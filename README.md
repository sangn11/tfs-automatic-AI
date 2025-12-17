# 🚦 APPLICATION TO AUTOMATICALLY DETECTE AND TRANSLATE TRAFFIC SIGNS FROM PHOTOS AND VIDEOS IN REAL TIME - Dự án Phát hiện Biển báo Giao thông theo thời gian thực - KHÓA LUẬN TỐT NGHIỆP
## 💡 Giới thiệu Bài toán (Problem Statement)

### Tên Dự án: ỨNG DỤNG TỰ ĐỘNG PHÁT HIỆN  VÀ DỊCH BIỂN BÁO GIAO THÔNG TỪ ẢNH , VIDEO THEO THỜI GIAN THỰC
Mục tiêu của dự án này là phát triển một ứng dụng web có khả năng phân tích hình ảnh hoặc luồng video (webcam) để **nhận diện chính xác vị trí và loại biển báo giao thông** theo thời gian thực (hoặc gần thời gian thực).

* **Tính cần thiết:** Giúp tạo ra các ứng dụng hỗ trợ lái xe an toàn (ADAS) hoặc giám sát giao thông tự động.
* **Giải pháp:** Sử dụng mô hình Machine Learning đã được huấn luyện, tối ưu hóa sang định dạng **ONNX** để có thể chạy hiệu suất cao trực tiếp trên trình duyệt web, tận dụng sức mạnh tính toán của máy khách (client-side).

---

## ⚙️ Lý do xây dựng dự án

* **Phục vụ cho:** **KHÓA LUẬN TỐT NGHIỆP**
* **Thời gian:** [HK1 2024-2025, 12/2025]
* **GVHD:** [ThS. Võ Quang Hoàng Khang]

---


## 👤 Người Thực hiện

| Vai trò | Tên | Liên hệ |
| :--- | :--- | :--- |
| **Sinh viên thực hiện** | **[Nguyễn Phú Sang 21023391 - Đào Văn Nhật 21117081]** | [Email cá nhân: sangn.csdev@gmail.com] |
| **Đơn vị/Trường** | [IUH - Trường Đại học Công nghiệp Tp.HCM] | [Địa điểm: 12 Nguyễn Văn Bảo] |

---

## 🔬 Quy trình Mô hình (Model Workflow)

Phần này mô tả cách mô hình tự huấn luyện được tích hợp vào ứng dụng:

1.  **Huấn luyện Mô hình Gốc:**
    * **Dữ liệu:** [Bộ dữ liệu bạn sử dụng: Dữ liệu tự thu thập trên các tuyến đường có hình ảnh biển báo giao thông ở khu vực Thành phố Hồ Chí Minh và được gán nhãn trên Roboflow (link dataset: 'https://app.roboflow.com/sngairesearchvn/tfs-classed-tyk24/17').]
    * **Kiến trúc:** [Kiến trúc chính của mô hình: Thực hiện train mô hình YOLOv8n, YOLOv9s, YOLO11n. So sánh kết quả hiệu suất mô hình và quyết định chọn mô hình YOLO11n làm   mô hình chính của đề tài vì cho hiệu suất tốt nhất và độ chính xác mô hình tốt.]
    * **Môi trường:** [Công cụ huấn luyện, công nghệ sử dụng: Google Colab, PyTorch/TensorFlow,...]

2.  **Chuyển đổi Định dạng:**
    * Mô hình đã huấn luyện được xuất (export) sang định dạng **ONNX** (Open Neural Network Exchange).
    * File **`convertOnnx.ipynb`** viết lại chi tiết quá trình chuyển đổi và tối ưu hóa mô hình.
    * *Mô hình đã chuyển đổi được lưu tại:* **`public/model/[Tên file mô hình].onnx`** (hoặc thư mục tương ứng).

3.  **Thực thi trên Web:**
    * Ứng dụng Front-end sử dụng thư viện **ONNX Runtime Web** để tải và thực thi mô hình ONNX này trực tiếp bằng JavaScript, mang lại tốc độ xử lý nhanh mà không cần máy chủ (server).

---

## 🛠️ Công nghệ Sử dụng (Tech Stack)

| Lĩnh vực | Công nghệ | Mục đích |
| :--- | :--- | :--- |
| **Model** | **Mô hình Tự Huấn luyện** | Cung cấp khả năng nhận diện biển báo đặc thù. |
| **Thực thi AI** | ONNX Runtime Web | Chạy mô hình ONNX trên trình duyệt. |
| **Front-end** | Vite, [Tên Framework: React/Vue/Svelte] | Xây dựng giao diện người dùng. |
| **Quản lý gói** | Node.js, Yarn (hoặc npm) | Quản lý các thư viện. |



## 📅 Tình trạng Dự án (Project Status)

* **Trạng thái hiện tại:** **[Đang phát triển]** và **[Đã triển khai thử nghiệm]**
* **Các tính năng đã hoàn thành:** [Nhận diện cơ bản từ ảnh, video, webcam theo thời gian thực.]
* **Các tính năng dự kiến:** [Phát triển tính năng nhận diện kí hiệu quang học (OCR), Thông báo bằng giọng nói (TTS)]

---

## 📑 Cấu trúc Thư mục Chính

| Tên File/Thư mục | Mô tả |
| :--- | :--- |
| `node_modules/` | Chứa thư viện của note.js. |
| `src/` | Chứa tất cả mã nguồn chính của ứng dụng Front-end. |
| `public/` | Chứa tài sản tĩnh và mô hình ONNX đã chuyển đổi. |
| `dataset/` | Chứa dữ liệu để huấn luyện mô hình. |
| `result_train/` | Chứa kết quả quá trình mô hình được huấn luyện. |
| `TFS_AIAuto` | Notebook chứa code Python để tiền xử lý dữ liệu và huấn luyện mô hình. |
| `convertOnnx.ipynb` | Notebook chứa code Python để chuyển đổi mô hình YOLO11n sang định dạng ONNX. |
| `package.json` | Khai báo các gói phụ thuộc và các lệnh chạy. |
| `vite.config.js` | Cấu hình cho công cụ đóng gói Vite. |
| `README.md` | Tài liệu thông tin về dự án này. |

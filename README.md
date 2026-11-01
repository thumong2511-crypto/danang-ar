# Đà Nẵng sống động — tranh AR (Image Tracking)

Website: https://thumong2511-crypto.github.io/danang-ar/

## Trạng thái
- Bản demo hiện tại ưu tiên **tranh Cầu Rồng Đà Nẵng**, hiển thị một mô hình 3D **cách điệu** có hiệu ứng lửa (không phải mô hình kiến trúc chính xác).
- Dữ liệu `targets.mind` đã có trong repo nhưng **chưa được xác thực với ảnh gốc**, do ảnh chưa được lưu tại đây.
- Sơn Trà / chùa Linh Ứng **chưa được kích hoạt**. Cần bổ sung ảnh chính thức, tạo lại `targets.mind` chứa cả hai ảnh và thêm mô hình riêng.
- Chưa xác nhận AR chạy thành công trên điện thoại thật.

## Thử nghiệm Cầu Rồng
1. Mở link website HTTPS **trên điện thoại** bằng Chrome/Safari.
2. Cho phép website truy cập camera.
3. Hiển thị **chính ảnh đã sử dụng để tạo `targets.mind`** trên màn hình máy tính hoặc in ra giấy. Không dùng ảnh thay thế hoặc ảnh bị cắt/có QR che phủ.
4. Hướng camera điện thoại vào toàn bộ ảnh và giữ yên, đủ sáng.
5. Khi nhận diện thành công, website thông báo “Đã nhận diện Cầu Rồng!” và mô hình nổi trên ảnh.

Nếu trang không nhận diện: dùng MindAR Image Target Compiler để tạo lại `targets.mind` chỉ từ **ảnh Cầu Rồng gốc** (targetIndex: 0), rồi tải file mới đè lên `targets.mind` ở gốc repository.

MindAR Compiler: https://hiukim.github.io/mind-ar-js-doc/tools/compile/

## Kiểm tra lỗi
- Trên GitHub, vào **Actions** → “pages build and deployment” để xem trạng thái xuất bản.
- Vào **Settings → Pages** và đảm bảo **Deploy from a branch / main / (root)**.
- Nếu lỗi 404 dù Actions xanh, kiểm tra URL chính xác ở Settings → Pages; thử tải lại trang không dùng cache. Lưu ý kết quả triển khai thành công không đảm bảo camera AR hoạt động.
- Camera đòi HTTPS và quyền truy cập. Trình duyệt tích hợp trong ứng dụng nhắn tin có thể hạn chế camera/WebGL.
- Nếu camera mở nhưng không có AR, ưu tiên xác minh ảnh nguồn khớp `targets.mind`.

## Bổ sung Sơn Trà
1. Chọn ảnh rõ nét, nhìn từ Mỹ Khê về bán đảo Sơn Trà và chùa Linh Ứng.
2. Biên dịch cùng ảnh Cầu Rồng: **Cầu Rồng trước (index 0)**, **Sơn Trà sau (index 1)**.
3. Bổ sung model/hiệu ứng vào một `a-entity mindar-image-target="targetIndex: 1"` trong `index.html`.
4. Thử trên hai ảnh bằng điện thoại. Chỉ tạo QR dẫn tới URL website sau khi chạy ổn định.

## Lưu ý bản quyền
Chỉ đưa lên repository công khai ảnh và mô hình bạn được phép sử dụng. Có thể giữ ảnh gốc trên máy và chỉ đăng `targets.mind` nếu giấy phép không cho phép công khai ảnh.

## Công nghệ
A-Frame 1.6.0, MindAR 1.2.5; triển khai tĩnh qua GitHub Pages.

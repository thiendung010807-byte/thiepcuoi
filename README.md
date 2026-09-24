# Wedding Invitation

- `index.html`: trang mở bao thư.
- `invitation.html`: trang nội dung sau khi mở thư.
- Album tự chuyển nhanh hơn (~2,7 giây), hỗ trợ vuốt trái/phải và chạm ảnh đang ở giữa để xem toàn màn hình.
- Bên dưới album có phần `THÔNG TIN TIỆC CƯỚI`, lịch tháng 01/2026 và nút tải lịch `.ics`.

Mở `index.html` để chạy từ đầu.

## RSVP
Nút "XÁC NHẬN THAM DỰ" mở form RSVP mobile-first. Bản hiện tại lưu phản hồi gần nhất vào localStorage trên thiết bị để test giao diện. Khi có endpoint Google Apps Script / Supabase / API riêng, có thể nối phần submit trong `invitation.js` để thu phản hồi tập trung.

## Album lightbox
Khi ảnh được mở toàn màn hình, autoplay của album tạm dừng hoàn toàn. Autoplay chỉ chạy lại sau khi đóng lightbox. Ảnh trong lightbox được mở lớn gần sát kích thước màn hình và vẫn hỗ trợ vuốt trái/phải thủ công.


## Mục mới
- Thêm phần địa điểm tiệc cưới với bản đồ nhúng và nút mở Google Maps / chỉ đường.
- Thêm phần lịch trình ngày cưới dạng timeline.
- Thêm phần sổ lưu bút, cho phép gửi lời chúc và lưu tạm trên localStorage để demo giao diện.

## Đồng bộ tên và quà mừng
Toàn bộ tên cô dâu/chú rể và thông tin quà mừng được gom vào `wedding-config.js`.
Chỉ cần sửa các giá trị trong file đó, phần tên trên thiệp, gợi ý lời chúc, tiêu đề lịch và hộp quà sẽ cập nhật theo.

Để thêm QR chuyển khoản thật của chú rể:
1. Chép ảnh QR vào thư mục `assets/`, ví dụ `assets/qr-chu-re.png`.
2. Trong `wedding-config.js`, đặt `bankQrImage: "assets/qr-chu-re.png"`.
3. Điền `bankName`, `bankAccount`, `bankAccountName`.

## Sổ lưu bút
Khung lời chúc hiển thị khoảng 5-6 lời chúc và có thanh cuộn riêng. Nút đũa thần mở 5 gợi ý ngẫu nhiên từ hơn 20 mẫu; nút `Tạo thêm` tạo nhóm gợi ý mới. Gợi ý có tên cô dâu/chú rể lấy trực tiếp từ `wedding-config.js`.


## Cập nhật giao diện 24/09
- Khóa cuộn ngang toàn trang, bao gồm cả trang mở thư và trang nội dung.
- Hộp quà mừng dùng ảnh bao lì xì hoa đỏ thật (`assets/gift-envelope.png`) và lắc/lơ lửng nhẹ.
- Lightbox album mở ảnh lớn gần toàn màn hình, có bộ đếm, nút trước/sau và thanh thumbnail ở dưới; autoplay vẫn dừng khi lightbox mở.

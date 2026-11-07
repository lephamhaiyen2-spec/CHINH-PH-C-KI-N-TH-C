# CHINH PHỤC KIẾN THỨC — Đại Hải Trình

Game đua thuyền trắc nghiệm 4 đội, giao diện responsive cho màn hình lớn, máy tính bảng và điện thoại.

## Chạy game
- Mở trực tiếp [index.html](./index.html) bằng trình duyệt.
- Hoặc bật GitHub Pages: **Settings → Pages → Deploy from a branch → main → /(root) → Save**. Sau khi GitHub triển khai, game sẽ có địa chỉ Pages trong phần Settings → Pages.

## Luật chơi
- 4 đội thi, mỗi đội cần trả lời đúng 5 câu để hoàn thành đường đua.
- Mỗi câu có 15 giây.
- Đúng: +100 điểm, thuyền tiến lên và lượt chuyển sang đội tiếp theo.
- Sai hoặc hết giờ: không cộng điểm, đội đó giữ lượt và nhận câu hỏi khác.
- Khi một đội đạt 5 câu đúng, hiệu ứng chiến thắng và pháo hoa xuất hiện.

## Giáo viên
- Nút ⚙ mở bảng điều khiển.
- Chỉnh tên đội, màu sắc, âm lượng, bật/tắt hiệu ứng âm thanh.
- Tải ảnh nền tùy chọn.
- Nhập Excel: A câu hỏi, B–E đáp án A–D, F đáp án đúng (A/B/C/D hoặc 1/2/3/4), G giải thích; bỏ qua dòng tiêu đề.
- Có thể sửa câu hỏi thủ công theo định dạng: `Câu hỏi | Đáp án A | Đáp án B | Đáp án C | Đáp án D | Đáp án đúng | Giải thích`.
- Nhấn **LƯU & XÁC NHẬN** trước khi bắt đầu.

## Lưu ý về đồng bộ
Bản hiện tại là game trình chiếu/điều khiển trên một trình duyệt. Cấu hình, ngân hàng câu hỏi và điểm được lưu bằng localStorage trên thiết bị đó. Chưa có phòng chơi QR, tài khoản học sinh hoặc đồng bộ thời gian thực giữa nhiều điện thoại. Muốn chạy mô hình mỗi học sinh dùng điện thoại riêng, cần bổ sung backend realtime (Firebase/Supabase), mã phòng và phân quyền giáo viên/học sinh.

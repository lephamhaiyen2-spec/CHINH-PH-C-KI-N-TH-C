# CHINH PHỤC KIẾN THỨC — Hải trình tri thức (Live)

Game trắc nghiệm đua thuyền đa đội, responsive cho điện thoại và máy tính. Có mã QR vào phòng, đội linh vật, bảng điểm trực tuyến, đồng hồ đếm ngược, nhập Excel và hiệu ứng chiến thắng.

## Mở game
1. Bật GitHub Pages: **Settings → Pages → Deploy from a branch → main → /(root) → Save**.
2. Mở URL GitHub Pages của repository.
3. Giáo viên chọn **⚙ GIÁO VIÊN** để cấu hình.

## Bật chơi trực tuyến (bắt buộc)
Game sử dụng Supabase Realtime Broadcast để truyền trạng thái phòng, người tham gia, lượt trả lời và điểm số giữa các thiết bị.

1. Tạo project tại https://supabase.com/.
2. Trong project, vào **Project Settings → API** và sao chép **Project URL** cùng **anon/public (publishable) key**.
3. Trong trang game, giáo viên dán hai giá trị này vào phần **Kết nối trực tuyến**.
4. Chỉ dùng anon/public key trong game. Tuyệt đối không dùng service_role key.
5. Giáo viên lưu cấu hình để tạo phòng và QR. QR mang theo Project URL, public key và danh sách đội để học sinh không phải cấu hình từng máy.
6. Học sinh quét QR, nhập tên, chọn đội và vào phòng. Giáo viên xem danh sách trực tuyến, nhấn **Xác nhận danh sách & sẵn sàng**, sau đó bắt đầu.

Realtime Broadcast hoạt động qua Supabase Realtime; cần bảo đảm dịch vụ Realtime của project đang hoạt động và thiết bị có Internet.

## Luật chơi
- Không giới hạn số đội trong giao diện; số cột thuyền tự dàn theo số đội (tối đa 8 cột mỗi hàng).
- Giáo viên cấu hình thời gian mỗi câu, điểm mỗi câu đúng và số câu đúng để hoàn thành.
- Đúng: cộng điểm, tiến một chặng và chuyển lượt sang đội kế tiếp.
- Sai hoặc hết giờ: không cộng điểm, đội hiện tại giữ lượt và nhận câu hỏi mới.
- Đội đầu tiên đạt số câu đúng mục tiêu sẽ thắng.

## File Excel mẫu
Nhấn **Tải file Excel mẫu** trong bảng giáo viên. Cấu trúc cột: A số thứ tự câu, B câu hỏi, C–F đáp án A–D, G đáp án đúng (A/B/C/D). Dòng đầu là tiêu đề.

## Lưu ý triển khai
- Phiên bản này dùng Realtime Broadcast, không cần tạo bảng cơ sở dữ liệu để truyền ván chơi.
- Phòng đang chạy phụ thuộc vào trang trình duyệt giáo viên còn mở và kết nối mạng; tải lại/đóng trang giáo viên sẽ làm mất trạng thái phòng đang chạy.
- Cấu hình URL/key được lưu trên trình duyệt giáo viên. QR chứa public key để học sinh kết nối; không đưa khóa bí mật vào URL.
- Nếu cần lưu lịch sử trận đấu, tự phục hồi sau khi giáo viên mất kết nối, khóa phòng, chống giả mạo điểm hoặc quản lý tài khoản, cần bổ sung backend có xác thực và cơ sở dữ liệu.

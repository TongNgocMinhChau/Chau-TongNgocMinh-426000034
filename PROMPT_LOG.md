# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

- **Họ và tên:** Tống Ngọc Minh Châu
- **MSSV:** 426000034 
- **Tên đề tài Website:** Portfolio cá nhân sinh viên CNTT - Đại học Lạc Hồng
- **Công cụ AI đã sử dụng:** GitHub Copilot trong VS Code


## 1. Yêu cầu ban đầu (System/Initial Prompt)

> Tạo website portfolio cá nhân bằng HTML5 và CSS cho sinh viên Công nghệ Thông tin tại Đại học Lạc Hồng. Website có phần giới thiệu, kỹ năng, góc học tập và liên hệ; sử dụng các thẻ HTML ngữ nghĩa, CSS Variables cho màu sắc và font, bố cục Flexbox/Grid, hiển thị tốt trên máy tính và điện thoại. Bổ sung các hiệu ứng CSS phù hợp để trang sinh động nhưng vẫn dễ đọc, dễ sử dụng.

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)

### Lần 1: Rà soát Semantic HTML & CSS Variables
- **Prompt đã dùng:** “Kiểm tra cấu trúc web hợp lệ, sử dụng đúng các thẻ ngữ nghĩa; không lạm dụng thẻ `div`; khai báo và vận dụng hiệu quả CSS Variables cho color/font; layout cân đối, sử dụng tốt Flexbox/Grid.”
- **Kết quả AI tạo ra:** Rà soát thấy trang có `header`, `nav`, `main`, `section`, `footer`; các biến CSS cho màu và font; layout dùng Grid/Flexbox và có breakpoint responsive.
- **Nhận xét & Tinh chỉnh của SV:** Nhiều `div` đang làm nhiệm vụ nhóm nội dung cho Grid/Flex nên vẫn hợp lý. Có thể cân nhắc dùng `article` cho các card nội dung độc lập. Phát hiện biến `--mint-light: #E8FF3` không phải mã hex hợp lệ; cần sửa nếu biến này được sử dụng.

### Lần 2: Tích hợp Animate.css & AOS
- **Prompt đã dùng:** “Tích hợp thành công Animate.css và AOS.css đúng cách. Hiệu ứng chuyển động mượt mà, không lạm dụng gây rối mắt.”
- **Kết quả AI tạo ra:** Kiểm tra thấy Animate.css được nạp qua CDN và dùng các class `animate__...`; AOS CSS/JS được nạp, gọi `AOS.init()` và kích hoạt bằng `data-aos`.
- **Nhận xét & Tinh chỉnh của SV:** Cần cân nhắc bỏ hiệu ứng `animate__infinite` ở nút chính và bổ sung hỗ trợ `prefers-reduced-motion` để hạn chế chuyển động lặp liên tục.

### Lần 3: Phối màu card “Về bản thân”
- **Prompt đã dùng:** Đổi màu phù hợp cho ba card; khi hover, mỗi card có bóng nhẹ theo màu riêng; nền section liền màu, không tạo cảm giác bị cắt ngang.
- **Kết quả AI tạo ra:** Ba card có nền pastel tím, xanh mint và cam nhạt; icon, viền hover và bóng đổ dùng màu nhấn tương ứng. Nền phần giới thiệu và kỹ năng được đồng bộ.
- **Nhận xét & Tinh chỉnh của SV:** Yêu cầu thêm viền ngoài khi hover cùng màu với từng card; hiệu ứng được bổ sung.

### Lần 4: Làm nổi bật tiêu đề section
- **Prompt đã dùng:** Đổi màu các tiêu đề “Về bản thân”, “Tiến độ học tập kỹ năng” và “Góc học tập & Thử nghiệm CSS” sao cho nổi bật, phù hợp với trang.
- **Kết quả AI tạo ra:** Các tiêu đề dùng màu tím đậm, đồng bộ với màu nhấn hiện có.
- **Nhận xét & Tinh chỉnh của SV:** Dùng chung quy tắc `.section-title` để giữ giao diện nhất quán.

### Lần 5: Tối ưu giao diện điện thoại và iPad
- **Prompt đã dùng:** Điều chỉnh website để có thể xem giao diện điện thoại hoặc iPad bằng chế độ thiết bị trong DevTools (F12).
- **Kết quả AI tạo ra:** Thêm breakpoint tablet/mobile; hero chuyển sang một cột, lưới card thu gọn, navigation được phép xuống dòng, khoảng cách và typing được điều chỉnh cho màn hình nhỏ.
- **Nhận xét & Tinh chỉnh của SV:** Kiểm tra thực tế bằng Device Toolbar trong DevTools; lưu ý các card lật dựa trên hover có thể chưa thuận tiện trên màn hình cảm ứng.

### Lần 6: Tự động đổi màu nền
- **Prompt đã dùng:** “Đổi background trắng thành tự động chuyển màu ngẫu nhiên.”
- **Kết quả AI tạo ra:** JavaScript chọn ngẫu nhiên một màu pastel trong danh sách, đặt vào CSS Variable `--bg-light` và đổi màu mỗi 6 giây; nền chuyển mượt.
- **Nhận xét & Tinh chỉnh của SV:** Giữ card và footer có nền riêng để nội dung dễ đọc; đã kiểm tra màu nền thay đổi sau một chu kỳ.

### Lần 7: Rà soát chất lượng theo tiêu chí
- **Prompt đã dùng:** Kiểm tra cấu trúc semantic, mức dùng `div`, CSS Variables, layout, UI/UX, Animate.css/AOS và mức độ chuyển động.
- **Kết quả AI tạo ra:** Xác nhận phần lớn tiêu chí đã có; ghi nhận các điểm cần cân nhắc như mã màu không hợp lệ, hiệu ứng lặp vô hạn, hỗ trợ giảm chuyển động và khả năng tương tác card trên thiết bị cảm ứng.
- **Nhận xét & Tinh chỉnh của SV:** Đây là bước rà soát, chưa phải xác nhận rằng mọi điểm tồn đọng đã được sửa. Cần kiểm tra lại các liên kết mạng xã hội trước khi bàn giao; trong phiên bản HTML được xem gần nhất, các liên kết này đang để `href="#"`.

### Lần 8: Gỡ hiệu ứng được JavaScript kích hoạt
- **Prompt đã dùng:** “Hãy bỏ hết các hiệu ứng của JavaScript.”
- **Kết quả AI tạo ra:** Gỡ thư viện AOS, các thuộc tính `data-aos`, lệnh khởi tạo AOS và script tự đổi màu nền. Không còn script JavaScript trong trang.
- **Nhận xét & Tinh chỉnh của SV:** Giữ các animation thuần CSS như Animate.css, typing, thanh tiến độ và hover; các hiệu ứng này không cần JavaScript để chạy.

## 3. Tổng kết

AI hỗ trợ rà soát cấu trúc, gợi ý CSS responsive và triển khai các tinh chỉnh giao diện theo từng yêu cầu nhỏ. Các hiệu ứng hiện được giữ lại đều chạy bằng CSS; sinh viên cần đối chiếu kết quả với mã nguồn thực tế, kiểm tra lại các giá trị CSS, liên kết, khả năng dùng trên thiết bị cảm ứng và mức độ phù hợp của hiệu ứng trước khi hoàn thiện website.

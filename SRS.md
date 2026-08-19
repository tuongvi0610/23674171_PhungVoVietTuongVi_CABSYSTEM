Bước 1: đọc và phân tích yêu cầu: hiểuu về bussiness contesxt và bussiness problem
trả lời câu hỏi: 
a) Khách hàng muốn giải quyết vấn đề gì?
Công ty ABC đang đối mặt với sự quá tải và kém hiệu quả trong khâu vận hành. Ban lãnh đạo muốn giải quyết 4 "nỗi đau" chính:
- Điểm nghẽn trong khâu phân công: Loại bỏ việc tổng đài viên phải phân công tài xế thủ công, chuyển sang điều phối tự động dựa trên thuật toán.
- Trải nghiệm khách hàng bị đứt gãy: Xóa bỏ tình trạng khách hàng "mù thông tin" sau khi đặt xe bằng cách cung cấp khả năng theo dõi vị trí và trạng thái chuyến đi theo thời gian thực.
- Rủi ro và thiếu đồng bộ trong thanh toán: Số hóa và tập trung hóa quy trình thanh toán thay vì quản lý phân tán, giảm thiểu rủi ro khi thu tiền mặt và tích hợp an toàn với đối tác bên thứ ba.
- Nút thắt trong kiến trúc công nghệ: Đập bỏ nền tảng cũ thiếu linh hoạt để xây dựng kiến trúc mới giúp hệ thống không bị sập toàn bộ khi một tính năng (như thông báo hay thanh toán) gặp lỗi.
  
b) Vì sao k thể đáp ứng, ai sử dụng ht này
- Hệ thống hiện tại (gồm tổng đài và app đơn giản) đã chạm đến "giới hạn trần" của sự phát triển do:
  + Năng lực xử lý thấp: Dùng sức người để phân công tài xế chỉ hiệu quả với quy mô nhỏ. Khi số lượng cuốc xe tăng vọt vào giờ cao điểm, tổng đài sẽ quá tải, dẫn đến mất khách.
  + Thiếu khả năng tương tác dữ liệu hai chiều: Ứng dụng hiện tại giống một kênh ghi nhận yêu cầu một chiều. Nó không thu thập được vị trí GPS liên tục của tài xế để tính toán ETA (thời gian dự kiến đến) hay tối ưu hóa thuật toán tìm tài xế gần nhất.
  + Kiến trúc nguyên khối cứng nhắc: Việc mở rộng bị kìm hãm. Bộ phận vận hành không thể dễ dàng thêm phương thức thanh toán mới hay kênh thông báo mới vì can thiệp vào code cũ có nguy cơ làm hỏng các tính năng đang chạy ổn định.
- Hệ thống phục vụ một mô hình kinh doanh kết nối đa chiều, với 3 nhóm người dùng chính:
  + Khách hàng: Người có nhu cầu di chuyển, cần sự tiện lợi, minh bạch về giá cả và lộ trình.
  + Tài xế: Người cung cấp dịch vụ vận tải, cần hệ thống nhận chuyến ổn định, tính toán cước phí chính xác và thu nhập rõ ràng.
  + Nhân viên vận hành & Ban giám đốc: Người kiểm soát hệ thống, hỗ trợ giải quyết sự cố (lỗi chuyến, thanh toán thất bại), quản lý rủi ro và sử dụng các báo cáo dữ liệu (doanh thu, tỷ lệ hủy) để ra quyết định chiến lược.
    
c)  Giá trị sau khi tạo ra
Việc triển khai thành công CAB System mới sẽ mang lại những giá trị cốt lõi:
- Hiệu quả vận hành: Tự động hóa hoàn toàn quy trình "Matching" (ghép cuốc), tiết kiệm chi phí nhân sự tổng đài và tối ưu hóa thời gian chạy xe trống của tài xế.
- Nâng tầm trải nghiệm người dùng: Trải nghiệm mượt mà từ lúc đặt xe, theo dõi lộ trình đến thanh toán không tiền mặt sẽ làm tăng tỷ lệ giữ chân khách hàng.
- Nền tảng của sự tăng trưởng: Doanh nghiệp sở hữu một hệ thống lõi vững chắc, dễ dàng triển khai thêm các mô hình kinh doanh mới trong tương lai (như giao hàng, đi chung xe, đa dạng cổng thanh toán) mà không phải đập đi xây lại.
- Quản trị dựa trên dữ liệu: Mọi điểm chạm đều được số hóa, giúp ban lãnh đạo có các dashboard báo cáo trực quan về hiệu suất thực tế của mô hình kinh doanh.
  
Bước 2: xác định stakeholder, lập bảng cột 1 những stakeholder, cột 2 vai trò, vẽ ma trận stakeholder cho biết mức độ ảnh hưởng của các vai trò trong hệ thống

| Stakeholder | Vai trò |
| :--- | :--- |
| **Ban giám đốc** | Đưa ra tầm nhìn chiến lược, quyết định phạm vi yêu cầu, phê duyệt ngân sách và nghiệm thu dự án. |
| **Khách hàng** | Người dùng cuối sử dụng ứng dụng để đăng ký, đặt xe, theo dõi lộ trình, thanh toán và đánh giá dịch vụ. |
| **Tài xế** | Đối tác trực tiếp thực hiện chuyến đi, sử dụng hệ thống để nhận cuốc, định vị GPS và cập nhật trạng thái hành trình. |
| **Nhân viên vận hành** | Quản trị viên của hệ thống, thực hiện quản lý tài khoản, hỗ trợ xử lý sự cố chuyến đi/thanh toán và theo dõi báo cáo hoạt động. |
| **Đối tác bên thứ 3** | Cung cấp các dịch vụ hạ tầng tích hợp bên ngoài như nền tảng bản đồ (Maps), cổng thanh toán điện tử và dịch vụ gửi thông báo. |
| **Đội ngũ phát triển** | Thu thập yêu cầu, phân tích, thiết kế, lập trình và kiểm thử hệ thống để đảm bảo tiến độ 7 tuần. |

### Ma trận Stakeholder (Power - Interest Matrix)

| | Quan tâm THẤP (Low Interest) | Quan tâm CAO (High Interest) |
| :--- | :--- | :--- |
| **Quyền lực CAO** <br>| **GIỮ HÀI LÒNG** <br><br> • Đối tác bên thứ 3 (Thanh toán, SMS, Maps) | **QUẢN LÝ CHẶT CHẼ** <br><br> • Ban giám đốc <br> • Đội ngũ phát triển dự án |
| **Quyền lực THẤP** <br>| **THEO DÕI** <br><br> | **THƯỜNG XUYÊN THÔNG TIN** <br><br> • Khách hàng<br> • Tài xế <br> • Nhân viên vận hành |

Bước 3: Business Goals

Dự án xây dựng nền tảng CAB System hướng tới việc giải quyết các hạn chế của hệ thống cũ và đạt được các mục tiêu kinh doanh cốt lõi sau:

**1. Mục tiêu Vận hành & Hiệu suất (Operational Goals)**
* **Tự động hóa hoàn toàn luồng điều phối:** Loại bỏ quy trình phân công tài xế thủ công, sử dụng thuật toán ghép cuốc (matching) tự động dựa trên vị trí và trạng thái để phục vụ số lượng lớn khách hàng cùng lúc.
* **Quản trị tập trung và ra quyết định dựa trên dữ liệu:** Cung cấp công cụ quản lý toàn diện cho nhân viên vận hành và hệ thống báo cáo (doanh thu, tỷ lệ hoàn thành/hủy chuyến, hiệu suất tài xế) cho Ban lãnh đạo.

**2. Mục tiêu Trải nghiệm Người dùng (Experience Goals)**
* **Đối với Khách hàng:** Nâng cao sự hài lòng thông qua trải nghiệm liền mạch: minh bạch giá cước, theo dõi vị trí xe theo thời gian thực (real-time tracking) và thanh toán đa phương thức an toàn.
* **Đối với Tài xế:** Tối ưu hóa thời gian chờ và chạy xe trống nhờ hệ thống nhận chuyến thông minh, nhanh chóng, giúp nâng cao năng suất và thu nhập.

**3. Mục tiêu Chiến lược & Công nghệ (Strategic & Technical Goals)**
* **Khả năng mở rộng dài hạn (Scalability & Flexibility):** Xây dựng kiến trúc hệ thống linh hoạt, các module hoạt động độc lập (đặt xe, thanh toán, thông báo). Cho phép dễ dàng mở rộng, bổ sung dịch vụ mới hoặc đối tác mới trong tương lai mà không cần xây dựng lại toàn bộ ứng dụng.
* **Đảm bảo tính ổn định cao (High Availability):** Hệ thống chịu tải tốt trong các khung giờ cao điểm; lỗi cục bộ ở một chức năng không làm gián đoạn toàn bộ hoạt động đặt xe.
* **Đáp ứng Time-to-market:** Triển khai thành công nền tảng với các tính năng cốt lõi (MVP) đúng thời hạn cam kết là **7 tuần**.




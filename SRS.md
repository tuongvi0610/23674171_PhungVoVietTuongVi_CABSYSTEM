**Bước 1: đọc và phân tích yêu cầu: hiểuu về bussiness context và bussiness problem** 
### a) Khách hàng muốn giải quyết vấn đề gì?
Công ty ABC đang đối mặt với sự quá tải và kém hiệu quả trong khâu vận hành. Ban lãnh đạo muốn giải quyết 4 "nỗi đau" chính:
- Điểm nghẽn trong khâu phân công: Loại bỏ việc tổng đài viên phải phân công tài xế thủ công, chuyển sang điều phối tự động dựa trên thuật toán.
- Trải nghiệm khách hàng bị đứt gãy: Xóa bỏ tình trạng khách hàng "mù thông tin" sau khi đặt xe bằng cách cung cấp khả năng theo dõi vị trí và trạng thái chuyến đi theo thời gian thực.
- Rủi ro và thiếu đồng bộ trong thanh toán: Số hóa và tập trung hóa quy trình thanh toán thay vì quản lý phân tán, giảm thiểu rủi ro khi thu tiền mặt và tích hợp an toàn với đối tác bên thứ ba.
- Nút thắt trong kiến trúc công nghệ: Đập bỏ nền tảng cũ thiếu linh hoạt để xây dựng kiến trúc mới giúp hệ thống không bị sập toàn bộ khi một tính năng (như thông báo hay thanh toán) gặp lỗi.
  
### b) Vì sao k thể đáp ứng, ai sử dụng hệ thống này
- Hệ thống hiện tại (gồm tổng đài và app đơn giản) đã chạm đến "giới hạn trần" của sự phát triển do:
  + Năng lực xử lý thấp: Dùng sức người để phân công tài xế chỉ hiệu quả với quy mô nhỏ. Khi số lượng cuốc xe tăng vọt vào giờ cao điểm, tổng đài sẽ quá tải, dẫn đến mất khách.
  + Thiếu khả năng tương tác dữ liệu hai chiều: Ứng dụng hiện tại giống một kênh ghi nhận yêu cầu một chiều. Nó không thu thập được vị trí GPS liên tục của tài xế để tính toán ETA (thời gian dự kiến đến) hay tối ưu hóa thuật toán tìm tài xế gần nhất.
  + Kiến trúc nguyên khối cứng nhắc: Việc mở rộng bị kìm hãm. Bộ phận vận hành không thể dễ dàng thêm phương thức thanh toán mới hay kênh thông báo mới vì can thiệp vào code cũ có nguy cơ làm hỏng các tính năng đang chạy ổn định.
- Hệ thống phục vụ một mô hình kinh doanh kết nối đa chiều, với 3 nhóm người dùng chính:
  + Khách hàng: Người có nhu cầu di chuyển, cần sự tiện lợi, minh bạch về giá cả và lộ trình.
  + Tài xế: Người cung cấp dịch vụ vận tải, cần hệ thống nhận chuyến ổn định, tính toán cước phí chính xác và thu nhập rõ ràng.
  + Nhân viên vận hành & Ban giám đốc: Người kiểm soát hệ thống, hỗ trợ giải quyết sự cố (lỗi chuyến, thanh toán thất bại), quản lý rủi ro và sử dụng các báo cáo dữ liệu (doanh thu, tỷ lệ hủy) để ra quyết định chiến lược.
    
### c)  Giá trị sau khi tạo ra
Việc triển khai thành công CAB System mới sẽ mang lại những giá trị cốt lõi:
- Hiệu quả vận hành: Tự động hóa hoàn toàn quy trình "Matching" (ghép cuốc), tiết kiệm chi phí nhân sự tổng đài và tối ưu hóa thời gian chạy xe trống của tài xế.
- Nâng tầm trải nghiệm người dùng: Trải nghiệm mượt mà từ lúc đặt xe, theo dõi lộ trình đến thanh toán không tiền mặt sẽ làm tăng tỷ lệ giữ chân khách hàng.
- Nền tảng của sự tăng trưởng: Doanh nghiệp sở hữu một hệ thống lõi vững chắc, dễ dàng triển khai thêm các mô hình kinh doanh mới trong tương lai (như giao hàng, đi chung xe, đa dạng cổng thanh toán) mà không phải đập đi xây lại.
- Quản trị dựa trên dữ liệu: Mọi điểm chạm đều được số hóa, giúp ban lãnh đạo có các dashboard báo cáo trực quan về hiệu suất thực tế của mô hình kinh doanh.
  
**Bước 2: xác định stakeholder, lập bảng cột 1 những stakeholder, cột 2 vai trò, vẽ ma trận stakeholder cho biết mức độ ảnh hưởng của các vai trò trong hệ thống**

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

**Bước 3: Business Goals**

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

**Bước 4: Xác định phạm vi (Scope)**
### Phạm vi dự án (Project Scope)

Với thời gian triển khai giới hạn trong **7 tuần**, dự án sẽ tập trung vào việc xây dựng Nền tảng cốt lõi (Core Platform) đảm bảo luồng đặt xe tự động hóa khép kín.

#### 1. Trong phạm vi dự án 

**1.1. Ứng dụng dành cho Khách hàng**
*   **Quản lý tài khoản:** Đăng ký, đăng nhập (xác thực), quản lý thông tin cá nhân.
*   **Chức năng Đặt xe:** Nhập điểm đón/đến, chọn loại dịch vụ (loại xe), xem cước phí dự kiến và tạo yêu cầu.
*   **Theo dõi & Tương tác:** Theo dõi trạng thái chuyến đi theo thời gian thực (đang tìm tài xế, tài xế đã nhận, thời gian dự kiến đến - ETA, đang di chuyển).
*   **Thanh toán & Hậu mãi:** Hỗ trợ thanh toán tiền mặt và tích hợp API thanh toán điện tử; xem lịch sử chuyến đi; đánh giá tài xế.

**1.2. Ứng dụng dành cho Tài xế**
*   **Quản lý trạng thái:** Đăng nhập, cập nhật hồ sơ/phương tiện, bật/tắt trạng thái "Sẵn sàng nhận chuyến".
*   **Xử lý chuyến đi:** Nhận thông báo cuốc xe mới, Chấp nhận/Từ chối chuyến.
*   **Cập nhật hành trình:** Thao tác cập nhật các mốc thời gian: Đã đến điểm đón -> Đã đón khách -> Đang di chuyển -> Hoàn thành.
*   **Định vị:** Gửi vị trí GPS liên tục về hệ thống để phục vụ điều phối.

**1.3. Cổng quản trị vận hành**
*   **Quản lý danh mục:** Quản lý thông tin Khách hàng, Tài xế và Phương tiện (hỗ trợ tạo tài khoản cho tài xế).
*   **Giám sát thời gian thực:** Theo dõi các chuyến đi đang diễn ra và vị trí tài xế.
*   **Hỗ trợ nghiệp vụ:** Xử lý các chuyến đi bị lỗi, tra cứu lịch sử giao dịch.
*   **Báo cáo & Phân quyền:** Phân quyền truy cập; Cung cấp báo cáo cơ bản (tổng chuyến, doanh thu, tỷ lệ hủy, hiệu suất tài xế).

**1.4. Hệ thống cốt lõi**
*   **Thuật toán điều phối:** Tự động tìm và đề xuất tài xế gần nhất/phù hợp nhất. Có cơ chế vòng lặp (chuyển tài xế khác nếu bị từ chối/timeout).
*   **Hệ thống thông báo:** Bắn thông báo theo các sự kiện của chuyến đi.
*   **Tính cước & Giao dịch:** Tự động tính tiền dựa trên loại xe/khoảng cách; xử lý logic khi giao dịch thanh toán thất bại.
*   **Bảo mật:** Lưu vết (Audit log) các thao tác quan trọng.

---

#### 2. Ngoài phạm vi dự án

Đây là các tính năng/yêu cầu **KHÔNG** được phát triển trong giai đoạn 7 tuần này, nhưng kiến trúc hệ thống vẫn phải được thiết kế để sẵn sàng tích hợp sau này:
*   **Lưu trữ dữ liệu thanh toán nhạy cảm:** Hệ thống KHÔNG lưu trữ thông tin thẻ tín dụng/tài khoản ngân hàng của khách hàng (giao phó hoàn toàn cho cổng thanh toán bên thứ 3).
*   **Mô hình dịch vụ mới:** Chưa phát triển các nghiệp vụ ghép chuyến, giao hàng hay thuê xe theo giờ.
*   **Đa dạng hóa nhà cung cấp:** Trong 7 tuần chỉ tích hợp 1 đối tác thanh toán và 1 kênh thông báo chính. Việc thêm nhiều nhà cung cấp khác được dời sang các giai đoạn sau.
*   **Quy trình thủ công cũ:** Loại bỏ hoàn toàn tính năng tổng đài viên tự tay phân công tài xế như hệ thống cũ.
  
**Bước 5: Business Requirement**

### 1. Yêu cầu Chức năng cấp cao (High-level Functional Requirements)
Hệ thống được chia thành 4 phân hệ (Modules) chính để đáp ứng luồng nghiệp vụ:

*   **Phân hệ Khách hàng (Rider Module):** Quản lý hồ sơ, chọn điểm đi/đến (sử dụng bản đồ), hiển thị giá cước dự kiến, gửi yêu cầu đặt chuyến, theo dõi tài xế (thời gian thực), thanh toán và đánh giá.
*   **Phân hệ Tài xế (Driver Module):** Bật/tắt trạng thái hoạt động, nhận thông báo cuốc xe mới, chấp nhận/từ chối, cập nhật trạng thái chuyến đi (Đã đến điểm đón -> Đã đón khách -> Hoàn thành), theo dõi thu nhập.
*   **Phân hệ Điều phối cốt lõi (Core Dispatch & Engine):** Thuật toán tìm kiếm tài xế gần nhất, quản lý vòng lặp (fallback) khi tài xế từ chối, tính toán cước phí tự động, gửi thông báo đa kênh.
*   **Phân hệ Quản trị (Admin Module):** Giao diện quản lý toàn bộ User (Khách hàng/Tài xế), quản lý xe, giám sát chuyến đi đang diễn ra (Real-time monitoring), xử lý khiếu nại/lỗi chuyến và hệ thống báo cáo (Dashboard).

---

### 2. Danh sách Quy tắc Nghiệp vụ (Business Rules)
Đây là các quy tắc logic cốt lõi mà hệ thống phải tuân thủ nghiêm ngặt trong quá trình vận hành.

| Mã BR | Tên quy tắc | Mô tả chi tiết |
| :--- | :--- | :--- |
| **BR-01** | **Điều kiện nhận chuyến** | Tài xế chỉ nhận được yêu cầu đặt xe khi trạng thái tài khoản là "Active" và trạng thái làm việc đang bật "Sẵn sàng". |
| **BR-02** | **Logic Điều phối (Matching)** | Hệ thống ưu tiên phát cuốc cho tài xế có vị trí địa lý gần điểm đón nhất. Nếu sau `[X]` giây (Cần chốt với Khách hàng) tài xế không phản hồi hoặc bấm từ chối, hệ thống tự động phát cuốc cho tài xế gần thứ 2. |
| **BR-03** | **Xử lý Không tìm thấy tài xế** | Nếu sau khi quét toàn bộ bán kính quy định mà không có tài xế nhận chuyến, hệ thống phải tự động hủy yêu cầu và gửi thông báo xin lỗi khách hàng. Khách hàng không phải thao tác tạo lại từ đầu nếu muốn thử lại. |
| **BR-04** | **Bảo mật dữ liệu thanh toán** | Hệ thống CAB **tuyệt đối không** lưu trữ thông tin thẻ tín dụng/CVV/Tài khoản ngân hàng của khách. Mọi dữ liệu thanh toán nhạy cảm phải được xử lý qua token của Cổng thanh toán (Payment Gateway). |
| **BR-05** | **Xử lý thanh toán thất bại** | Nếu giao dịch điện tử lỗi, hệ thống phải thông báo ngay cho khách hàng và cung cấp nút "Thanh toán lại" hoặc cho phép chuyển đổi sang hình thức "Tiền mặt". Chuyến đi vẫn được tính là hoàn thành. |

---

### 3. Yêu cầu Phi chức năng (Non-Functional Requirements - NFR)

| Nhóm yêu cầu | Mã NFR | Mô tả yêu cầu |
| :--- | :--- | :--- |
| **Kiến trúc & Khả năng mở rộng** | NFR-01 | Xây dựng kiến trúc module linh hoạt (Microservices/Modular Monolith) để các thành phần: Đặt xe, Thanh toán, Thông báo hoạt động độc lập. |
| | NFR-02 | Hệ thống phải có khả năng mở rộng (Scale-out) từng phần (ví dụ: chỉ tăng tài nguyên cho server thanh toán) mà không ảnh hưởng toàn hệ thống. |
| **Độ sẵn sàng (Availability)** | NFR-03 | Hệ thống không được sập toàn bộ khi một bên thứ 3 (như API Gửi tin nhắn) gặp sự cố. Phải có cơ chế xử lý lỗi cục bộ. |
| **Bảo mật & Kiểm toán** | NFR-04 | Mọi thao tác quản trị từ Admin, thay đổi số dư, hủy chuyến đều phải được hệ thống lưu vết (Audit Log) để phục vụ tra soát. |
| | NFR-05 | 100% người dùng (Khách hàng & Tài xế) phải được xác thực (Authentication) trước khi sử dụng các tính năng đặt chuyến/nhận chuyến. |

---

### 4. Ràng buộc và Phụ thuộc 
*   **Thời gian:** Dự án phải hoàn thành xây dựng và triển khai phiên bản đầu tiên (MVP) khép kín luồng đặt xe trong đúng **7 tuần**. Không gia hạn.
*   **Phụ thuộc bên thứ 3:** Tính năng định vị phụ thuộc vào độ chính xác của Map API (vd: Google Maps/Mapbox). Tính năng thanh toán phụ thuộc vào uptime của Đối tác thanh toán.

**Bước 6: Business Process**
### Sơ đồ Quy trình Nghiệp vụ (Business Process Flow)

```mermaid
flowchart TD
    %% Làn 1: KHÁCH HÀNG
    subgraph Lan_Khach_Hang [KHÁCH HÀNG]
        R1([Nhập điểm đi/đến])
        R2([Xác nhận Đặt xe])
        R3([Theo dõi tài xế trên bản đồ])
        R4([Thực hiện Thanh toán])
        R5([Đánh giá chất lượng])
    end

    %% Làn 2: HỆ THỐNG CAB
    subgraph Lan_He_Thong [HỆ THỐNG CAB]
        S1[Tính và hiển thị cước dự kiến]
        S2{Quét tìm tài xế gần nhất}
        S3[Cập nhật trạng thái: Đã có tài xế]
        S4[Gửi thông báo lộ trình/ETA]
        S5[Tính cước cuối và gọi API thanh toán]
        S6[Lưu lịch sử và hoàn tất chuyến]
    end

    %% Làn 3: TÀI XẾ
    subgraph Lan_Tai_Xe [TÀI XẾ]
        D1{Xác nhận nhận chuyến?}
        D2[Cập nhật: Đang đến điểm đón]
        D3[Cập nhật: Đã đón khách]
        D4[Cập nhật: Hoàn thành chuyến]
    end

    %% Luồng liên kết các bước
    R1 --> S1
    S1 --> R2
    R2 --> S2
    
    S2 -->|Gửi yêu cầu| D1
    
    %% Vòng lặp nếu từ chối hoặc quá giờ
    D1 -->|Từ chối / Hết giờ| S2
    
    %% Luồng tiếp tục khi đồng ý
    D1 -->|Đồng ý| S3
    S3 --> S4
    S4 --> R3
    S3 --> D2
    
    D2 --> D3
    D3 --> D4
    
    D4 --> S5
    S5 --> R4
    R4 --> S6
    S6 --> R5
```
**Bước 7: Phân rã yêu cầu chức năng**
## PHÂN RÃ YÊU CẦU CHỨC NĂNG (Functional Decomposition)

Hệ thống CAB System được phân rã thành 4 phân hệ chính: Khách hàng, Tài xế, Quản trị viên và Lõi hệ thống (Backend Engine).

### Bảng Phân rã Chức năng chi tiết

| Phân hệ (Module) | Nhóm chức năng (Feature) | Mã UC | Chức năng chi tiết (Sub-function) | Ưu tiên |
| :--- | :--- | :--- | :--- | :---: |
| **1. ỨNG DỤNG KHÁCH HÀNG** | **1.1. Quản lý tài khoản** | F-RID-01 | Đăng ký & Đăng nhập (SĐT / Email) | Cao |
| | | F-RID-02 | Cập nhật thông tin cá nhân (Tên, Hình ảnh) | Trung bình |
| | **1.2. Đặt chuyến** | F-RID-03 | Nhập/Chọn điểm đón và điểm đến trên bản đồ | Cao |
| | | F-RID-04 | Lựa chọn loại dịch vụ (Xe máy, Ô tô 4 chỗ, 7 chỗ) | Cao |
| | | F-RID-05 | Hiển thị cước phí dự kiến và xác nhận đặt xe | Cao |
| | **1.3. Theo dõi hành trình** | F-RID-06 | Xem trạng thái tìm kiếm và thông tin tài xế nhận cuốc | Cao |
| | | F-RID-07 | Theo dõi vị trí tài xế theo thời gian thực (Real-time GPS) | Cao |
| | | F-RID-08 | Hủy yêu cầu đặt xe (khi chưa có tài xế hoặc tài xế chưa đến) | Cao |
| | **1.4. Thanh toán & Hậu mãi** | F-RID-09 | Lựa chọn phương thức thanh toán (Tiền mặt / Điện tử) | Cao |
| | | F-RID-10 | Chấm điểm (Rating) và nhận xét tài xế sau chuyến đi | Trung bình |
| | | F-RID-11 | Xem lịch sử chuyến đi và chi tiết thanh toán | Thấp |
| | | | | |
| **2. ỨNG DỤNG TÀI XẾ** | **2.1. Quản lý tài khoản & Xe** | F-DRI-01 | Đăng nhập tài khoản (do Admin cấp hoặc tự đăng ký) | Cao |
| | | F-DRI-02 | Cập nhật thông tin phương tiện (Biển số, Loại xe) | Trung bình |
| | **2.2. Trạng thái hoạt động** | F-DRI-03 | Bật / Tắt trạng thái "Sẵn sàng nhận chuyến" (Online/Offline) | Cao |
| | **2.3. Xử lý chuyến đi** | F-DRI-04 | Nhận thông báo yêu cầu cuốc xe mới (Hiển thị điểm đón/đến) | Cao |
| | | F-DRI-05 | Chấp nhận hoặc Từ chối yêu cầu chuyến đi | Cao |
| | **2.4. Cập nhật hành trình** | F-DRI-06 | Cập nhật trạng thái: "Đã đến điểm đón" | Cao |
| | | F-DRI-07 | Cập nhật trạng thái: "Đã đón khách" (Bắt đầu di chuyển) | Cao |
| | | F-DRI-08 | Cập nhật trạng thái: "Hoàn thành chuyến" | Cao |
| | | | | |
| **3. CỔNG QUẢN TRỊ** | **3.1. Quản lý người dùng** | F-ADM-01 | Quản lý danh sách Khách hàng (Xem, Khóa tài khoản) | Trung bình |
| | | F-ADM-02 | Quản lý danh sách Tài xế & Phương tiện (Duyệt hồ sơ mới) | Cao |
| | **3.2. Giám sát & Hỗ trợ** | F-ADM-03 | Xem bản đồ trực tuyến các chuyến đi đang diễn ra | Trung bình |
| | | F-ADM-04 | Hỗ trợ hủy chuyến khẩn cấp hoặc xử lý lỗi cuốc xe | Cao |
| | | F-ADM-05 | Phân quyền nhân viên quản trị (Role-Based Access) | Trung bình |
| | **3.3. Báo cáo thống kê** | F-ADM-06 | Xem báo cáo tổng chuyến đi, tỷ lệ hoàn thành/hủy chuyến | Trung bình |
| | | F-ADM-07 | Xem báo cáo doanh thu theo ngày/tuần/tháng | Trung bình |
| | | | | |
| **4. LÕI HỆ THỐNG (Core Engine)** | **4.1. Thuật toán Điều phối** | F-COR-01 | Quét & Đề xuất tài xế phù hợp gần nhất dựa trên GPS | Cao |
| | | F-COR-02 | Tự động chuyển cuốc (Fallback) nếu tài xế từ chối/hết giờ | Cao |
| | **4.2. Xử lý logic** | F-COR-03 | Thuật toán tính cước phí (Dựa trên khoảng cách + Loại xe) | Cao |
| | | F-COR-04 | Tích hợp cổng thanh toán bên thứ 3 (Payment Gateway API) | Cao |
| | | F-COR-05 | Hệ thống gửi thông báo đa kênh (Push Notification / SMS) | Cao |

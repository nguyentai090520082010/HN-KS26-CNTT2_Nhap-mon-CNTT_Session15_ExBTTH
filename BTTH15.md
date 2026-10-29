# PHẦN 1 – THIẾT LẬP HYBRID WORKFLOW

1. **Sự cố mất file Slide:** **Không xảy ra.** Do tính năng Auto Sync lưu dữ liệu thời gian thực (Real-time) lên Cloud, bản mới nhất dưới máy local đã tự động tải lên cloud ngay khi chỉnh sửa.
2. **3 bước cài đặt Auto Sync:**
   - **B1:** Cài đặt Cloud Client (Google Drive / OneDrive) trên laptop.
   - **B2:** Đăng nhập và chọn thư mục làm việc `SmartCampus_Project` để đồng bộ.
   - **B3:** Thiết lập chế độ đồng bộ **Stream files** (hoặc *Keep on this device*) và kiểm tra dấu tích xanh.
3. **Thao tác khôi phục file bị xóa nhầm:**
   - Vào Cloud Web $\rightarrow$ Mở file $\rightarrow$ **File** $\rightarrow$ **Version History** $\rightarrow$ Chọn phiên bản 10 phút trước $\rightarrow$ Nhấn **Restore this version**.
4. **2 sai lầm & cách xử lý:**
   - *Sai lầm:* Đồng bộ `node_modules` (hàng vạn file rác/tạm) và file phim 4K (tốn bộ nhớ chung).
   - *Khắc phục:* Thêm `node_modules` vào `.gitignore` / Exclude list; xóa phim 4K khỏi thư mục chung.

---

# PHẦN 2 – PHÂN QUYỀN CHIA SẺ AN TOÀN

### 1. Bảng phân quyền chi tiết

| Tên File | Mức quyền | Phạm vi chia sẻ | Giải thích ngắn |
| :--- | :--- | :--- | :--- |
| **BaoCao_CuoiKy_SmartCampus.docx** | **Viewer** | **Restricted** (Chỉ mail GV) | Giảng viên đọc/đánh giá, tránh vô tình sửa đè nội dung. |
| **Slide_BaoCao.pptx** | **Editor** | **Restricted** (5 bạn) | 5 thành viên cùng chỉnh sửa trực tiếp gấp trong 2 ngày. |
| **GopY_BanNhap.docx** | **Commenter** | **Restricted** (Chỉ mail anh khóa trên) | Cho phép anh khóa trên để lại ghi chú góp ý mà không hỏng file gốc. |
| **ThongTin_CaNhan_NhomVien.xlsx** | **Editor/Viewer** | **Restricted** (5 bạn) | Bảo vệ thông tin nhạy cảm (CCCD, SĐT), tuyệt đối không mở ra ngoài. |

### 2. Quy tắc Cờ Đỏ Bảo mật & File thông tin cá nhân
- **Quy tắc:** Tuyệt đối không nới lỏng quyền chia sẻ tài liệu chứa dữ liệu cá nhân nhạy cảm (PII).
- **Lý do không dùng `Anyone with link + Editor`:** Bất kỳ ai có link (do lộ/bot quét) đều có thể truy cập, tải về hoặc xóa sạch CCCD/SĐT, gây nguy cơ đánh cắp thông tin và lừa đảo.

### 3. Cài đặt Settings cho Slide_BaoCao.pptx
- **Tắt:** *"Editors can change permissions and share"* (Ngăn Editor tự mời thêm người).
- **Tắt:** *"Viewers and commenters can see the option to download, print, and copy"* (Hạn chế tải/sao chép).

---

# PHẦN 3 – TỔ CHỨC GIAO TIẾP NHÓM CHUẨN DOANH NGHIỆP

1. **3 vấn đề giao tiếp trong Zalo:**
   - **No-Hello:** Hỏi không rõ nội dung (`có ai rảnh không`) gây tốn thời gian.
   - **Spam @all giờ khuya:** Tag cả nhóm lúc 23:47 gây ảnh hưởng nghỉ ngơi.
   - **Tin nhắn rác/Không phân luồng:** Gửi ảnh mèo, chat phiếm vào kênh làm việc chung.
2. **2 Channel đề xuất:**
   - `#announcement` (Chỉ đăng thông báo/deadline chính thức).
   - `#random` / `#off-topic` (Giao lưu, trò chuyện phiếm, gửi ảnh).
3. **Viết lại tin nhắn của Lan (Bất đồng bộ):**
   > *"Chào nhóm, mình đang bị lỗi căn chỉnh biểu đồ slide 5 file `Slide_BaoCao.pptx`. Bạn nào rảnh hỗ trợ sửa giúp mình trước 16h hôm nay nhé!"*
4. **Viết lại tin nhắn Trưởng nhóm (Hẹn giờ 8h sáng):**
   > *"Chào cả nhóm, để kịp tiến độ báo cáo, nhờ **@Nam** cập nhật sơ đồ Use Case và **@Hoa** điền bảng khảo sát trước 12:00 trưa nay nhé!"*

---

# PHẦN 4 – THÔNG BÁO TỔNG HỢP (#THONG-BAO)

```markdown
📢 [THÔNG BÁO] CHUẨN HÓA KHÔNG GIAN LÀM VIỆC & TIẾN ĐỘ DỰ ÁN SMARTCAMPUS

Chào cả nhóm, 

Mình đã chuẩn hóa không gian làm việc của nhóm để kịp deadline báo cáo:

1. 🔄 **Bật Auto Sync:** Đã kích hoạt đồng bộ tự động cho thư mục dự án. Mọi người thao tác dưới local, file sẽ tự lưu và backup Version History trên Cloud (không đưa `node_modules` và phim cá nhân vào thư mục này).
2. 🔒 **Phân quyền an toàn:** File báo cáo gửi Thầy đã chốt quyền **Viewer / Restricted**. File thông tin cá nhân đã khóa chặt theo Quy tắc Cờ Đỏ Bảo mật.
3. ⏳ **Phân công khẩn cấp:**
   - **@Nam**: Hoàn thiện sơ đồ kiến trúc trong `Slide_BaoCao.pptx` trước 14:00.
   - **@Hoa**: Kiểm tra và để lại nhận xét trong `GopY_BanNhap.docx` trước 17:00.

Mọi người thả tim ❤️ để xác nhận đã đọc nhé. Cùng cố gắng hoàn thành tốt đồ án! 🚀
```
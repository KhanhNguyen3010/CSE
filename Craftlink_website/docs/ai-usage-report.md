# Báo Cáo Sử Dụng AI – CraftLink

> **Dự án:** CraftLink – Sàn sản phẩm sáng tạo tùy biến  
> **Học phần:** Phát triển ứng dụng web cơ bản – CSE122  
> **Ngày lập / Cập nhật:** 25/10/2026 (Phiên bản hợp nhất toàn diện 4 Vai trò)  

---

## 1. Công cụ AI đã sử dụng

| # | Công cụ AI | Phiên bản / Môi trường | Mục đích sử dụng |
|:---:|---|---|---|
| 1 | **Google Gemini (AI Studio)** | Gemini 3.8 Flash / Pro | Hỗ trợ phác thảo layout HTML/CSS ban đầu, nội dung di sản thủ công và tạo mock data ban đầu |
| 2 | **Antigravity IDE (Google)** | Agentic AI Assistant (Claude 4.6 Sonnet / 4.6 Opus Thinking) | Hỗ trợ phân tích mã nguồn, gỡ lỗi logic phức tạp (CSS cascade, responsive drawer, modal lifecycle), tái cấu trúc header đa vai trò, viết bộ chuyển vai trò `role-switcher.js` và sinh tài liệu kỹ thuật |
| 3 | **Tailwind CSS Engine** | v3.x (CDN & Compiled CSS) | Hệ thống utility classes phục vụ xây dựng giao diện responsive nhanh chóng |

---

## 2. Các câu lệnh prompt chính

### 2.1. Phân hệ Dùng chung & Khách hàng (Buyer - SV1)

| # | Prompt tóm tắt | Kết quả đạt được | Tệp áp dụng |
|:---:|---|---|---|
| P-01 | "Tạo trang chủ cho website thủ công mỹ nghệ Việt Nam với hero section, danh mục sản phẩm, chỉ số tác động xã hội, sử dụng Tailwind CSS" | Khung HTML/CSS hoàn chỉnh trang chủ | `index.html` |
| P-02 | "Tạo trang đăng nhập hợp nhất 4 vai trò với 1-Click quick login, nhận diện email thông minh và responsive drawer" | Cổng đăng nhập tập trung | `pages/login.html` |
| P-03 | "Tạo trang marketplace với sidebar filter (dân tộc, vùng miền, chất liệu, giá), grid sản phẩm, pagination" | Giao diện và logic lọc sàn khám phá | `pages/buyer-marketplace.html` |
| P-04 | "Tạo form tạo brief tùy biến với validation, AI Brief Builder mô phỏng, modal thành công và lưu LocalStorage" | Form đặt chế tác riêng biệt | `pages/buyer-custom-brief.html` |
| P-05 | "Tạo trang đơn hàng tùy biến với filter theo trạng thái, card đơn hàng, timeline tiến trình" | Quản lý tiến trình đơn đặt hàng | `pages/buyer-orders.html` |
| P-06 | "Tạo trang chi tiết sản phẩm với gallery ảnh, tab mô tả/review/câu chuyện, bộ đếm số lượng" | Chi tiết tác phẩm di sản | `pages/product.html` |
| P-07 | "Tạo trang impact/about us với số liệu tác động, bản đồ nghệ nhân, timeline, testimonials" | Trang truyền thông tác động xã hội | `pages/impact.html` |
| P-08 | "Tạo trang giỏ hàng với danh sách sản phẩm, tăng/giảm số lượng, xóa, tính tổng hóa đơn" | Quản lý giỏ hàng mua sắm | `pages/buyer-cart.html` |

### 2.2. Phân hệ Nghệ nhân / Người bán (Maker - SV2)

| # | Prompt tóm tắt | Kết quả đạt được | Tệp áp dụng |
|:---:|---|---|---|
| P-09 | "Xây dựng Bảng điều khiển người sáng tạo (Maker Dashboard) với biểu đồ doanh số, chỉ số brief mới và trạng thái xưởng" | Giao diện Dashboard Nghệ nhân | `seller/dashboard.html` |
| P-10 | "Xây dựng hộp thư Brief Inbox nhận dữ liệu từ LocalStorage của Buyer, phân loại tab trạng thái và xem chi tiết brief trong modal" | Hệ thống tiếp nhận Brief của khách | `seller/brief-inbox.html` |
| P-11 | "Xây dựng trình soạn thảo Đề xuất chế tác (Proposal Editor) kèm tính năng AI Revision Summarizer tóm tắt yêu cầu sửa đổi của khách" | Trình soạn thảo báo giá & proposal | `seller/proposal-editor.html` |
| P-12 | "Tạo giao diện quản lý danh mục sản phẩm, form đăng bán tác phẩm mới có kiểm duyệt nguồn gốc làng nghề" | Quản lý kho hàng & đăng bán | `seller/products.html`, `seller/product-form.html` |

### 2.3. Phân hệ Kiểm duyệt & Quản trị (Moderator & Admin - SV3)

| # | Prompt tóm tắt | Kết quả đạt được | Tệp áp dụng |
|:---:|---|---|---|
| P-13 | "Xây dựng trang kiểm duyệt di sản: duyệt listing, quản lý bộ từ khóa cấm quét tự động và trung tâm xử lý kháng án từ nghệ nhân" | Phân hệ kiểm duyệt di sản | `admin/pages/moderation.html` |
| P-14 | "Xây dựng Bảng điều khiển Quản trị viên (Platform Admin Dashboard) với chỉ số KPI sàn, nhật ký audit log cấp cao và override dispute" | Bảng điều khiển trung tâm Admin | `admin/pages/dashboard.html` |
| P-15 | "Xây dựng màn hình quản lý danh mục di sản theo vùng miền (Taxonomy) và quản lý người dùng phân quyền 4 vai trò" | Quản trị danh mục & tài khoản | `admin/pages/content.html`, `admin/pages/users.html` |

### 2.4. Hợp nhất hệ thống & Trải nghiệm đa vai trò (Cross-Role Ecosystem)

| # | Prompt tóm tắt | Kết quả đạt được | Tệp áp dụng |
|:---:|---|---|---|
| P-16 | "Tạo widget chuyển vai trò nhanh (Switch Persona) hỗ trợ chuyển tức thì giữa Buyer, Maker, Moderator và Admin ở mọi trang" | Hệ thống Switch Persona toàn sàn | `assets/js/role-switcher.js` |
| P-17 | "Thay thế toàn bộ giao diện Header của Admin và Moderator bằng ngôn ngữ thiết kế kính mờ cao cấp của Buyer, giữ nguyên nội dung tab" | Header đồng bộ chuẩn hóa | `admin/pages/*.html`, `admin/index.html` |
| P-18 | "Đồng bộ hóa luồng đăng xuất: mọi vai trò khi bấm logout đều điều hướng về đúng trang login chung tập trung" | Đăng xuất thông minh đa cấp thư mục | `admin/js/common/sidebar.js`, `seller/seller.js` |

---

## 3. Phần AI sinh ra vs. Phần sinh viên chỉnh sửa

### 3.1. Giao diện HTML & CSS

| Thành phần | AI sinh ra | Sinh viên chỉnh sửa & tối ưu |
|---|---|---|
| **Cấu trúc HTML** | Sinh khung layout các section cơ bản | Sinh viên chuẩn hóa HTML semantic (`<nav>`, `<header>`, `<main>`, `<article>`, `<aside>`), gắn các thuộc tính `aria-label`, sắp xếp lại hierarchy thẻ |
| **Hệ thống CSS Design System** | Gợi ý màu sắc và token ban đầu | Sinh viên biên tập [colors.css](file:///Users/khanhteu/Downloads/Workspace/BTL/Craftlink-web/Craftlink_website/assets/css/colors.css) và [base.css](file:///Users/khanhteu/Downloads/Workspace/BTL/Craftlink-web/Craftlink_website/assets/css/base.css) với gam màu thổ cẩm đặc thù (Chàm, Thổ hoàng, Đất nung), tinh chỉnh tỷ lệ bo góc và độ tương phản |
| **Responsive Mobile / Tablet** | AI sinh responsive cơ bản | Sinh viên sửa lại toàn bộ thanh điều hướng thành **Mobile Drawer** trượt từ cạnh phải, điều chỉnh bảng dài thành dạng cuộn hoặc Card hiển thị mượt mà trên màn hình nhỏ từ 320px |
| **Header Admin & Moderator** | Header Admin ban đầu thô sơ, dạng bảng dẹt | Sinh viên viết lại toàn bộ Header của Admin/Mod kế thừa giao diện kính mờ mờ ảo `backdrop-blur-lg` của Buyer, avatar tròn xoe sang trọng và menu dropdown tiện lợi |

### 3.2. JavaScript & Tương tác DOM

| Thành phần | AI sinh ra | Sinh viên chỉnh sửa & tối ưu |
|---|---|---|
| **Bộ lọc sàn khám phá** (`thocam.js`) | Hàm lọc đơn giản theo 1 trường | Sinh viên viết thuật toán lọc đa tiêu chí (dân tộc AND chất liệu AND vùng miền AND khoảng giá) kèm sắp xếp và phân trang |
| **Hộp thư Brief liên vai trò** | Gợi ý template giao diện | Sinh viên viết cơ chế đọc/ghi `localStorage` (`craftlink_briefs`), kết nối trực tiếp yêu cầu từ Buyer sang hộp thư của Maker |
| **Bộ chuyển vai trò** (`role-switcher.js`) | Mã khung modal chuyển vai | Sinh viên hoàn thiện giao diện floating pill, đồng bộ trạng thái vai trò `craftlink_current_role`, tích hợp phím tắt trên Header toàn sàn |
| **Xử lý đăng xuất thông minh** | Hàm `location.href` cố định | Sinh viên nâng cấp hàm `logoutDemo()` tự động nhận diện độ sâu URL (`pages/` vs `admin/pages/`) để không bao giờ bị lỗi 404 |
| **Điều khiển Modal an toàn** (`modal.js`) | Khai báo hàm đóng mở thông thường | Sinh viên bổ sung lắng nghe phím `Escape` và sự kiện click ra ngoài vùng nền mờ (backdrop) để đảm bảo không bị kẹt màn hình |

---

## 4. Các lỗi kỹ thuật phức tạp đã gặp và cách xử lý

| # | Tình huống lỗi gặp phải | Nguyên nhân gốc rễ (Root Cause) | Cách sinh viên phát hiện và khắc phục |
|:---:|---|---|---|
| 1 | **Modal popup tự động bật lên trên trang Admin/Mod và không thể đóng** | Class `.modal-hidden { display: none }` trong file CSS bị class `.flex` của Tailwind CDN ghi đè do thứ tự ưu tiên cascade sau khi CDN tiêm style vào `<head>`. | Sinh viên kiểm tra DevTools, bổ sung `.modal-hidden { display: none !important; }` và cập nhật sự kiện đóng an toàn trong `modal.js`. |
| 2 | **Thanh menu điều hướng trên Header bị biến mất toàn bộ trên Desktop** | Class `.hidden { display: none !important; }` vô tình áp đặt `!important` lên utility `.hidden`, triệt tiêu class responsive `hidden lg:flex` của Tailwind. | Sinh viên phát hiện ngay lập tức, gỡ bỏ `!important` khỏi `.hidden`, chỉ giữ lại phạm vi hẹp cho `.modal-hidden`. Phục hồi thanh menu hiển thị 100%. |
| 3 | **Đăng xuất bị lỗi đường dẫn 404** | Cấu trúc thư mục đa cấp: `admin/index.html` (cách trang login 1 cấp `../`) khác với `admin/pages/dashboard.html` (cách 2 cấp `../../`). | Sinh viên viết lại hàm `logoutDemo()` trong `sidebar.js` kiểm tra `window.location.pathname.includes('/pages/')` để tính toán chính xác đích đến. |
| 4 | **Nội dung văn hóa bị sai lệch** | AI sinh tên làng nghề và kỹ thuật dệt không chuẩn xác với văn hóa Tây Bắc. | Sinh viên đối chiếu tư liệu Craft Link thực tế, chuẩn hóa lại tên gọi (thổ cẩm H'Mông, dệt dè Zèng Tà Ôi, nhuộm chàm cổ truyền). |

---

## 5. Phương pháp kiểm chứng & Đảm bảo chất lượng

1. **Kiểm tra trực quan đa thiết bị (Responsive Testing):**
   * Sử dụng Chrome DevTools mô phỏng: Mobile (iPhone SE 375px, Pixel 7 412px), Tablet (iPad Air 820px) và Desktop (1440px).
   * Kiểm tra độ phóng to trình duyệt 200% (`Ctrl/Cmd + +`) không làm vỡ bố cục hoặc mất chữ.
2. **Kiểm tra luồng người dùng khép kín (End-to-End Walkthrough):**
   * Đăng nhập $\rightarrow$ Đặt Brief tại Buyer $\rightarrow$ Nhận Brief tại Maker $\rightarrow$ Duyệt di sản tại Moderator $\rightarrow$ Giám sát tại Admin $\rightarrow$ Đăng xuất.
3. **Kiểm tra tương thích trình duyệt (Cross-Browser):**
   * Chạy thử nghiệm trên Google Chrome, Mozilla Firefox, Microsoft Edge và Apple Safari trên macOS.
4. **Kiểm tra tính nhất quán Design System:**
   * Đối chiếu mã màu, font chữ Playfair Display / Plus Jakarta Sans trên toàn bộ các trang.

---

## 6. Bài học kinh nghiệm rút ra

1. **AI là trợ lý gia tăng năng suất, không thay thế tư duy phản biện:** AI giúp dựng khung giao diện nhanh gấp nhiều lần, nhưng việc hiểu rõ kiến trúc CSS Specificity, DOM Tree và vòng đời sự kiện là bắt buộc để xử lý các lỗi xung đột giao diện.
2. **Tầm quan trọng của Thiết kế có hệ thống (Design System):** Khi tích hợp nhiều phân hệ (Buyer, Maker, Admin) từ các thành viên khác nhau, việc thống nhất token màu sắc và cấu trúc Header là chìa khóa để sản phẩm đồng nhất như một thể thống nhất.
3. **Kỹ năng làm việc nhóm và phân luồng Git:** Phân chia rõ ràng trách nhiệm từng thành viên (SV1, SV2, SV3) theo các nhánh tính năng trước khi hợp nhất vào `main`.

---

## 7. Bảng phân định Tính năng Mock vs. API thật

| Tính năng | Phân loại | Cơ chế hiện thực |
|---|:---:|---|
| **Cổng đăng nhập tập trung** | Mock Client-Side | Nhận diện vai trò qua email và nút bấm 1-Click, phân luồng trực tiếp không cần backend |
| **Sàn khám phá di sản** | Mock API & Local | Dữ liệu `data.js` kết hợp thuật toán lọc đa tiêu chí thời gian thực |
| **Đặt hàng tùy biến (Custom Brief)** | Mock State Storage | Lưu trữ trực tiếp trong `localStorage` (`craftlink_briefs`) |
| **Hộp thư Brief của Nghệ nhân** | Mock State Sync | Đọc dữ liệu từ `localStorage` để đồng bộ đơn hàng giữa Buyer và Maker |
| **Mô phỏng AI (Brief Builder & Revision)** | Mock AI Engine | Xử lý JavaScript DOM, phân tích từ khóa và mô phỏng phản hồi sau độ trễ `setTimeout` |
| **Kiểm duyệt & Kháng án** | Mock In-Memory | Lưu trữ trạng thái trong bộ nhớ JavaScript và phản hồi Toast tức thì |

---

## 8. Tuyên bố trung thực của nhóm sinh viên

> Nhóm thực hiện BTL-11 cam kết toàn bộ thông tin khai báo trong báo cáo này phản ánh trung thực 100% quá trình học tập và phát triển sản phẩm. Công cụ AI được áp dụng có trách nhiệm, có sự kiểm chứng và làm chủ hoàn toàn mã nguồn của tất cả các thành viên trong nhóm.

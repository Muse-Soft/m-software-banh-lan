# DESIGN.md — Landing page xưởng xe đạp thủ công Bánh Lăn (MSR-46)

> Tài liệu thiết kế chốt cho sprint TEC-346. Dev (task Dev của sprint) dựng đúng tài liệu này, không tự thêm màu, font hay khối ngoài danh sách. QA đối chiếu bản dựng với tài liệu này, kèm kiểm tra đa dạng theo OPERATIONS.md mục 16.5.

## 0. Khác biệt so với các project gần nhất (bắt buộc theo mục 16.5 — đã đọc thật ngày 2026-10-25)

Thứ tự project mới nhất lấy từ /api/office, DESIGN.md đọc trực tiếp qua raw.githubusercontent.com ngày 2026-10-25:

1. **Sớm Mai** (m-software-som-mai, TEC-340) — archetype: **A8 Tạp chí nhiều cột**; cặp font: **Lora + Be Vietnam Pro**; nhiệt màu: **sáng-ấm** (nền #F3EDE3, nhấn đồng #9A6A2F); điểm nhấn: "thang rang 5 nấc".
2. **Đất Lành** (m-software-dat-lanh, TEC-333) — archetype: **A1 Editorial dọc**; cặp font: **Cormorant Garamond + Be Vietnam Pro**; nhiệt màu: **trung tính trầm** (nền #E7E1D6, nhấn xanh men #2E6B62); điểm nhấn: "vệt men chảy".
3. **Gác Sách** (m-software-gac-sach, TEC-326) — archetype: **A4 Bento-masonry**; cặp font: **EB Garamond + Be Vietnam Pro**; nhiệt màu: **sáng-ấm** (nền #FBF6EE, nhấn đỏ gạch #A63D2F); điểm nhấn: "gáy sách làm vạch chia khối".

Lựa chọn cho Bánh Lăn (đối chiếu trực tiếp với 3 project trên):

- **Archetype: A6 Thanh bên cố định** — KHÁC A8 của project liền trước (Sớm Mai) và KHÁC A1 của project liền trước nữa (Đất Lành), thỏa luật "không dùng lại archetype của 2 project liền trước"; cũng khác A4 của Gác Sách. Cách A6 thể hiện ở: thanh bên trái cố định suốt trang trên desktop (xem mục "Bố cục"), nội dung chính cuộn bên phải — không phải lưới nhiều cột kiểu tạp chí (A8), không phải một cột dọc dẫn nhịp bằng ảnh (A1), không phải lưới ô lệch cỡ (A4).
- **Cặp font: Fraunces + Be Vietnam Pro** — KHÁC nguyên cặp Lora + Be Vietnam Pro của project liền trước (Sớm Mai): font tiêu đề đổi sang Fraunces (serif hiển thị, nét đậm, có cảm giác cơ khí công nghiệp, hỗ trợ tiếng Việt). Be Vietnam Pro giữ vai trò font nội dung như nhiều project trước, nhưng cặp font tổng thể đã khác vì font tiêu đề đã đổi.
- **Nhiệt màu: sáng-ấm** — chuỗi nhiệt gần nhất: Bánh Lăn (sáng-ấm) → Sớm Mai (sáng-ấm) → Đất Lành (trung tính trầm): chỉ 2 project sáng-ấm liên tiếp ở cuối chuỗi, KHÔNG tạo thành 3 project liên tiếp cùng nhiệt màu vì Đất Lành ở giữa đã đổi sang trung tính trầm. Nhiệt sáng-ấm của Bánh Lăn thiên về xưởng cơ khí (nền xám giấy ấm, nhấn đỏ gạch gỉ, điểm vàng đèn xưởng), khác tông kem cà phê của Sớm Mai.
- **Điểm nhấn riêng** (xem mục "Điểm nhấn đặc sắc"): "vạch hàn + tem cỡ khung" — không project nào gần đây có.

## Tổng quan

- Sản phẩm: landing page 1 trang, visual-first, cho xưởng đóng xe đạp thủ công Bánh Lăn — mỗi chiếc xe được đo khung theo vóc dáng người lái, hàn tay và lắp ráp tại xưởng.
- Archetype: **A6 Thanh bên cố định** — thanh bên trái cố định chứa logo, menu neo tới các khối và nút đặt lịch; vùng nội dung bên phải cuộn độc lập.
- Phong cách tham chiếu: **tạp chí xe đạp thủ công kiểu xưởng cơ khí công nghiệp** — ảnh thép, gỗ, da dưới ánh đèn xưởng vàng; bố cục kỹ thuật, có số đo khung như bản vẽ xưởng.
- Ngôn ngữ: tiếng Việt, hỗ trợ dấu đầy đủ (cả Fraunces và Be Vietnam Pro đều hỗ trợ tiếng Việt).

## Bảng màu (mã hex + vai trò)

| Mã hex | Vai trò |
|---|---|
| `#ECEAE4` | Nền chính toàn trang — xám giấy ấm, sáng |
| `#D8D2C4` | Nền khối phụ (thẻ mẫu xe, khối quy trình) và đường chia nhạt |
| `#1C2420` | Chữ chính + nền thanh bên cố định (chữ trên thanh bên dùng `#ECEAE4`) |
| `#5A655E` | Chữ phụ (mô tả ngắn, chú thích, ghi chú giá mẫu) |
| `#C2452D` | Nhấn chính — đỏ gạch gỉ: nút bấm, giá mẫu, vạch hàn, tem cỡ khung |
| `#D9A441` | Nhấn phụ — vàng đèn xưởng: chỉ điểm xuyết nhỏ (icon, dấu sao nếu có), không làm nền khối lớn |

## Font chữ

- Font tiêu đề: **Fraunces** (serif hiển thị, nét đậm, hỗ trợ tiếng Việt) — hero 64px desktop / 40px mobile, tiêu đề khối 40px desktop / 28px mobile, tên mẫu xe 28px, chữ trong thanh bên 18px đậm.
- Font nội dung: **Be Vietnam Pro** — nội dung 17px, dòng cao 1.7; chú thích 14px; nút bấm 16px đậm; nhãn tem cỡ khung 13px đậm, chữ hoa.
- Không dùng thêm font thứ ba.

## Điểm nhấn đặc sắc: "vạch hàn + tem cỡ khung"

Nhìn thấy được, lặp lại xuyên suốt trang, không project gần đây nào có:

- **Vạch hàn**: đường chia giữa các khối không phải đường thẳng trơn mà là vạch đứt đoạn mô phỏng mối hàn — chấm tròn đường kính 4px, cách nhau 8px, màu `#C2452D`, dày 3px, dài bằng 120px, đặt phía trên mỗi tiêu đề khối.
- **Tem cỡ khung**: mỗi tiêu đề khối và mỗi thẻ mẫu xe có một tem hình chữ nhật viền 2px màu `#C2452D`, nền `#ECEAE4`, chữ Fraunces 13px đậm ghi cỡ khung mẫu (ví dụ "KHUNG 54 CM" cho xe phố, "KHUNG 56 CM" cho xe touring, "ĐO THEO NGƯỜI LÁI" cho xe đặt riêng).

## Bố cục (archetype A6)

- Desktop (rộng ≥ 1024px): thanh bên trái cố định, rộng 280px, nền `#1C2420`, chứa logo "Bánh Lăn", menu neo (Bộ sưu tập / Quy trình / Câu chuyện / Đặt lịch) và nút "Đặt lịch tư vấn" màu `#C2452D`; vùng nội dung bên phải chiếm phần còn lại, lề nội dung tối đa 1200px, khoảng cách giữa các khối 96px.
- Tablet/mobile (rộng < 1024px): thanh bên biến thành thanh ngang gọn ở đầu trang (logo + nút đặt lịch), nội dung xếp một cột; khoảng cách khối 64px (tablet) / 48px (mobile); hero 40px tiêu đề.
- Thứ tự khối trong vùng nội dung: (1) Hero → (2) Bộ sưu tập → (3) Quy trình → (4) Câu chuyện xưởng → (5) Đặt lịch.

## Các khối và quy tắc hình ảnh

Tông ảnh chung cho toàn trang (§16.3): ảnh mẫu đồng tông xưởng cơ khí ấm — khung thép, gỗ, da, ánh đèn xưởng vàng; ảnh lấy từ Unsplash, ghi rõ là ảnh mẫu trong comment kết quả của Dev. Không dùng ảnh tông lạnh, ảnh studio trắng.

| Khối | Nội dung | Tỉ lệ khung ảnh |
|---|---|---|
| 1. Hero | Ảnh lớn toàn màn hình chiếc xe thành phẩm trong xưởng; tiêu đề "Bánh Lăn — Xe đạp đóng tay theo số đo của bạn"; nút "Đặt lịch tư vấn" và "Xem bộ sưu tập" | Ảnh 16:9, cao 100vh, phủ tối 30% để chữ đọc được |
| 2. Bộ sưu tập | 3 thẻ mẫu xe, mỗi thẻ: ảnh lớn, tên mẫu, mô tả 1–2 câu, giá mẫu, tem cỡ khung. Xe phố 18.500.000đ — xe touring 24.900.000đ — xe đặt riêng từ 32.000.000đ | Ảnh thẻ 4:3, lưới 3 cột desktop / 1 cột mobile |
| 3. Quy trình | 4 bước đánh số 01–04: (01) Đo số đo — (02) Hàn khung — (03) Sơn và lắp ráp — (04) Chạy thử và bàn giao; mỗi bước 1 câu mô tả + ảnh xưởng | Ảnh mỗi bước 3:2, lưới 2 cột desktop / 1 cột mobile |
| 4. Câu chuyện xưởng | Ảnh người thợ + ảnh toàn cảnh xưởng; đoạn văn ngắn về triết lý đóng tay, không sản xuất hàng loạt | Ảnh chân dung thợ 4:5, ảnh xưởng 16:9 |
| 5. Đặt lịch | Form: họ tên, số điện thoại, mẫu xe quan tâm (chọn 1 trong 3 mẫu), ngày muốn tư vấn, ghi chú | Không ảnh; form 1 cột, rộng tối đa 640px |

## Quy tắc dữ liệu thật / mẫu (bắt buộc cho Dev)

- Giá trên trang **luôn là giá mẫu**: mỗi giá phải kèm chữ "Giá mẫu" ngay cạnh (ví dụ "18.500.000đ — Giá mẫu"), footer ghi rõ "Tất cả giá trên trang là giá mẫu".
- Địa chỉ, điện thoại, giờ mở cửa và người phụ trách để placeholder **`[CẦN BỔ SUNG]`**, tuyệt đối không bịa số liệu thật.
- Form đặt lịch tư vấn/đặt xe **CHỈ giao diện**: submit dùng preventDefault và hiện thông báo mẫu ("Đây là bản giao diện mẫu — yêu cầu chưa được gửi đi thật"); không có thuộc tính action, không fetch, không mailto:, không tel:.
- Toàn bộ ảnh là ảnh mẫu (Unsplash), footer ghi rõ điều này.

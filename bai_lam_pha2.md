# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 09
- **Họ tên:**PHẠM GIA ANH TUÂN
- **Lớp:**CNTT 2
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):**

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt chỗ workshop ra JSON

**KET QUA AI**

```text
[
  {"ma_lop": "NANTAY", "ngay_hoc": "2026-12-13", "nguoi_lon": 2, "tre_em": 1, "ca_hoc": "chieu", "ghi_chu": null},
  {"ma_lop": "BANXOAY", "ngay_hoc": "2027-01-10", "nguoi_lon": 3, "tre_em": 0, "ca_hoc": null, "ghi_chu": null},
  {"ma_lop": "VEGOM", "ngay_hoc": null, "nguoi_lon": 4, "tre_em": 0, "ca_hoc": "sang", "ghi_chu": "1 bạn đi xe lăn"}
]
```

**Link trò chuyện:** https://claude.ai/share/0251e0c6-5545-4e6b-9d60-b8aa77b8c591

## 4.3. Báo giá bằng Chain-of-Thought
**KET QUA AI**

```text
Bước 1: Nhận yêu cầu báo giá

Kính chào Quý khách, cảm ơn Quý khách đã quan tâm đến lớp gốm của chúng tôi. Dưới đây là bảng báo giá chi tiết.

Bước 2: Xác nhận thông tin khách hàng yêu cầu

Lớp học: BANXOAY (Làm gốm bàn xoay, 3 giờ), đơn giá 550.000 đồng/người lớn
Người lớn: 5 người
Trẻ em 6–12 tuổi: 2 bé (8 tuổi và 12 tuổi), tính 70% giá người lớn
Trẻ dưới 6 tuổi đi kèm: 1 bé (4 tuổi), không làm sản phẩm, miễn phí
Sản phẩm cần nung và giao: 4 sản phẩm

Bước 3: Tính toán từng bước

Tiền người lớn: 5 × 550.000 = 2.750.000 đồng
Tiền trẻ em: 2 × (550.000 × 70%) = 2 × 385.000 = 770.000 đồng
(Bé 4 tuổi miễn phí: 0 đồng)
Tiền học (trước giảm giá): 2.750.000 + 770.000 = 3.520.000 đồng
Giảm giá nhóm: Nhóm có 5 người lớn nên đủ điều kiện giảm 5% trên tiền học.
Số tiền giảm: 3.520.000 × 5% = 176.000 đồng
Tiền học sau giảm: 3.520.000 − 176.000 = 3.344.000 đồng
Phí nung và giao (không giảm giá): 4 × 80.000 = 320.000 đồng
Tổng tiền: 3.344.000 + 320.000 = 3.664.000 đồng

Bảng tổng hợp

Hạng mục	Thành tiền (đồng)
Tiền người lớn	2.750.000
Tiền trẻ em	770.000
Tiền học trước giảm	3.520.000
Giảm giá nhóm (5%)	−176.000
Tiền học sau giảm	3.344.000
Phí nung và giao	320.000
Tổng tiền	3.664.000

Xin chân thành cảm ơn Quý khách. Chúng tôi rất mong được đón tiếp cả nhóm tại lớp học và chúc Quý khách có những trải nghiệm làm gốm thật thú vị.

[RESULT:3664000đồng]
```

**Link trò chuyện:**
https://claude.ai/share/55678e77-9850-49d9-babb-081b644533c9

### b) Kiểm tra kết quả AI

(Ghi kết luận AI đúng hay sai; nếu sai, ghi bước sai đầu tiên và kết quả đúng của bước đó – xoá dòng này)

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{"loai_su_co": "hong_san_pham", "so_khach": 3, "so_san_pham_bi_hong": 5, "tom_tat": "Gia đình 3 người học nặn gốm ngày 01/11/2026, nhận 5 sản phẩm bị nứt vỡ, đề nghị xưởng giải quyết."}
```

**Link trò chuyện:**
https://claude.ai/share/6a8c6f90-9bab-4f85-be32-545f4640a90d



## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
Kết quả chấm bài
Tiêu chí	Điểm	Minh chứng	Đề xuất sửa
1. Đúng thông tin (50% = 5đ)	0/5	Lỗi 1 (giá): "Lớp vẽ gốm bên em 200k thôi nè". Lý do sai: giá chuẩn là 250.000 đồng/người lớn, nhân viên báo thấp hơn 50.000 đồng. Lỗi 2 (chính sách đổi lịch): "Chị đổi trước 1 ngày thì free nha chị". Lý do sai: đổi trước 1 ngày (khoảng 24 giờ) thuộc mức từ 12 đến dưới 48 giờ, phải trả phí 30.000 đồng/người, không phải miễn phí. Cả hai nội dung cốt lõi đều sai nên không có điểm.	Sửa lỗi 1: "Dạ, giá lớp VEGOM là 250.000 đồng/người lớn ạ." Sửa lỗi 2: "Nếu chị đổi lịch trước giờ học 1 ngày (từ 12 đến dưới 48 giờ), phí đổi lịch là 30.000 đồng/người ạ. Đổi trước từ 48 giờ trở lên thì miễn phí, còn dưới 12 giờ thì không thể đổi lịch được ạ."
2. Đầy đủ (30% = 3đ)	1/3	Có trả lời cả hai câu hỏi (giá và đổi lịch) nhưng nội dung sai. Thiếu hẳn phần mời khách cung cấp ngày học, ca học, số người để đặt chỗ: "Có gì chị nhắn em nha!" chỉ là câu kết chung chung. Thiếu thông tin về các mốc phí khác của chính sách đổi lịch.	Sửa lỗi: "Chị vui lòng cho em xin ngày học, ca học và số người tham gia để em hỗ trợ đặt chỗ cho chị nhé ạ."
3. Giọng điệu (20% = 2đ)	0.5/2	Lỗi 1: "Hi chị ơi!". Lý do: lời chào suồng sã, thiếu chuyên nghiệp. Lỗi 2: "200k thôi nè, vui lắm luôn". Lý do: dùng từ ngữ thân mật, viết tắt, thiếu trang trọng. Lỗi 3: "free nha chị". Lý do: dùng từ lóng/tiếng nước ngoài kèm trợ từ suồng sã. Bài có xưng hô "chị/em" đúng mực nên chỉ được điểm một phần.	Sửa lỗi 1: "Dạ, em chào chị ạ!" Sửa lỗi 2: "Em xin gửi chị thông tin về lớp vẽ gốm VEGOM ạ." Sửa lỗi 3: "miễn phí ạ" (và dùng đúng thông tin như đã nêu ở trên).
Câu trả lời mẫu đề xuất

Dạ, em chào chị ạ! Em xin gửi chị thông tin về lớp vẽ gốm VEGOM:

Giá lớp là 250.000 đồng/người lớn.
Nếu chị đổi lịch trước giờ học 1 ngày (từ 12 đến dưới 48 giờ), phí đổi lịch là 30.000 đồng/người. Đổi trước từ 48 giờ trở lên thì miễn phí, còn dưới 12 giờ thì không thể đổi lịch ạ.

Chị vui lòng cho em xin ngày học, ca học và số người tham gia để em hỗ trợ đặt chỗ cho chị nhé. Em cảm ơn chị ạ!

Nhận xét chung

Nhân viên cần học thuộc bảng giá và chính sách đổi lịch trước khi tư vấn, vì thông tin sai về giá và phí có thể gây khiếu nại. Nhân viên cũng nên dùng văn phong lịch sự, chuyên nghiệp hơn và luôn chốt bằng việc mời khách cung cấp thông tin đặt chỗ.

ĐIỂM TỔNG: 1.5 / 10
 ```
**Link trò chuyện:**   https://claude.ai/share/6d5ff07d-2659-4460-9478-d4a923602af8
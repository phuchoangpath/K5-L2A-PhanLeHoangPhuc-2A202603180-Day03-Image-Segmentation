# Báo cáo thực hành Day 3 — điền trực tiếp trong fork của bạn

**Cách dùng:** Thay mọi dấu `…` bằng bài làm thật của bạn trước khi nộp link fork trên [LMS](https://aithucchien.vinuni.edu.vn). Giữ nguyên bốn mục và bảng để coach đọc nhanh. Viết ngắn, cụ thể theo ảnh/vùng; không cần thuật ngữ chuyên sâu. Ví dụ trong [hướng dẫn mẫu](../../reports/REPORT_TEMPLATE.md) chỉ giúp hiểu cách điền, không phải câu trả lời để chép lại.

- Mã học viên theo lớp: 2A202603180
- Ngày / CVAT local:12/11/2026
- Công cụ đã dùng: MobileSam 

Mã học viên là mã lớp cấp; không cần ghi họ tên trong report nếu kênh [LMS](https://aithucchien.vinuni.edu.vn) đã nhận diện bạn. Chỉ ghi công cụ thật sự đã dùng; không có SAM vẫn làm bài bình thường.

## 1. Bài đã nộp

Ghi tên ZIP đúng như file trong `submissions/` và số ảnh đã vẽ, Save. Chưa làm hoặc export lỗi thì ghi `chưa có`, không tạo ZIP rỗng. Cột điểm là điểm tối đa của task, **không phải điểm tự chấm**.

| Task | File ZIP đúng tên | Hoàn thành mấy ảnh | Điểm tối đa (coach chấm sau) |
| --- | --- | ---: | ---: |
| easy_semantic | x | 3 / 3 ||
| medium_instance | x | 3 / 3 ||
| hard_panoptic | x | 2 / 2 ||
| cp1_holes | x | 1 / 1 |  |
| cp2_slice | x | 1 / 1 |  |
| cp5_occlusion | x | 1 / 1 ||
| cp3_thin | x | 1 / 1 |  |
| cp4_curb | x | 1 / 1 |  |
| cp6_coverage | x | 1 / 1 |
| **Tổng tối đa** | | | **100** |

Nếu export lỗi, ghi task, dữ liệu đã Save đến đâu và lỗi đã báo coach.

## 2. Một quyết định trước khi dùng gợi ý

Chọn object đầu tiên bạn tự vẽ ở `medium_instance`, trước khi xem bất kỳ đề xuất tự động nào cho object đó. Ghi ảnh/vị trí đủ để tìm lại; “quy tắc biên” là lý do bạn chọn hoặc dừng mask ở ranh đó.

- Ảnh, vị trí và object Medium đầu tiên tự vẽ: ảnh 1 - 000000181542. Xe máy của người nam lái phía sau người phụ nữ lớn tuổi mặc áo dài
- Class và quy tắc tôi dùng để chọn biên: Class motocycle. Tôi sử dụng Mask để tô toàn bộ xe, chỉ bao gồm phần có thể quan sát được. Không bao gồm phần nền đường hoặc những khu vực bị vật thể khác che khuất.
- Nếu dùng gợi ý sau đó: vùng gợi ý sai/đúng, hành động sửa/giữ và lý do: Mình dùng MobileSam nhưng do ảnh không màu nên nhận diện sai, mình chỉnh tay lại cho khớp xe gắn máy. Tô 2 vùng sau đó dùng phím J để gộp lại do xe bị tách đôi bởi người phụ nữ đứng trước
- Nếu không dùng gợi ý: ghi “không dùng”; vẫn giải thích một quyết định gán nhãn của mình.

## 3. Một lỗi tôi tìm thấy và sửa

Chọn một lỗi **có thật** trong bài. Nếu công cụ lỗi khiến bạn chưa sửa được, ghi rõ đã thử gì và cần coach hỗ trợ gì; không ghi “đã sửa” khi chưa sửa.

- Task/ảnh/vùng: task medium_instance, ảnh 3 - 000000458325, 2 xe bên hàng trái vị trí xa nhất và bên phải người đàn ông đang đẩy xe em bé qua đường
- Lỗi thuộc loại: sai lớp / thiếu-thừa vật / gộp-tách / biên / phủ vùng / khác: gộp vật thể
- Bằng chứng tôi nhìn thấy: Nhìn thấy mui xe không phải 1 khối duy nhất, giữa 2 mui xe có vùng lỡm tam giác
- Quy tắc và hành động sửa: Theo guideline mỗi vật thể 1 mask, tôi đã xóa và tô lại thành 2 car riêng biệt 
- Sau sửa đã Save và export lại chưa? Đã save và export lại

Nếu bạn **đã xem Summary tự đánh giá trên GitHub Actions hoặc tự chạy script**, ghi ngắn một kết quả liên quan lỗi vừa sửa (ví dụ task, metric trước/sau nếu có): => Đã xem Summary, ban đầu phát hiện lỗi nộp nhầm file zip -> đã sửa, có warming -> xem lại ảnh sau  / chưa có điểm. 

Scorecard ba tier tối đa **82**, không phải điểm cuối trên 100. Không tự ghi PASS/top 3/bonus; người phụ trách xác nhận theo tiêu chí lớp. Không đưa file ground truth vào fork.

## 4. Ba ca chưa chắc hoặc đã cân nhắc

Mỗi ca là một **vùng cụ thể** khiến bạn phải cân nhắc hai cách hiểu. Ghi dấu hiệu nhìn thấy hoặc quy tắc đã dùng, rồi nêu quyết định hoặc câu hỏi cho coach. Không cần ba lỗi; ca đã quyết định được cũng hợp lệ.

| Ảnh/vị trí | Hai cách hiểu có thể | Quy tắc/chứng cứ | Quyết định hoặc câu hỏi cho coach |
| --- | --- | --- | --- |
| 1 Đoạn mép đường và vỉa hè (Task easy_semantic hoặc cp4_curb) | Cách 1: Nhận diện theo màu sắc mặt đường (chỗ nhựa đen là road, chỗ sáng màu/gạch là sidewalk).
Cách 2: Nhận diện theo chức năng và gờ bó vỉa (curb) | Ranh road–sidewalk xác định theo chức năng và bó vỉa, không chỉ theo màu nhựa đường | Quyết định: Dựa vào mép đá bó vỉa để kẻ ranh giới. |
| 2 Xe ô tô bị cột đèn che khuất ở giữa (Task medium_instance hoặc cp5_occlusion) | Cách 1: Tô 2 phần xe sau đó sử dụng phím J để gộp
Cách 2: chưa biết | Một vật bị che có thể có các vùng nhìn thấy rời nhau nhưng vẫn là một instance | Quyết định: Gán cả 2 phần nhìn thấy vào cùng 1 instance car, không vẽ phần bị cột đèn che khuất |
| 3 Kính xe  nhìn xuyên thấu nền phía sau (cp1_holes) | Tô phủ toàn bộ kính như một bộ phận hoàn chỉnh của xe  | Chỉ khoét khi là lỗ thực sự xuyên thấu | Quyết định: Giữ nguyên kính nằm trong mask của xe moto, không khoét lỗ để tránh làm nát mask của xe |

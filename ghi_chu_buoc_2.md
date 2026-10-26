# Ghi chú học tập, BƯỚC 2: Nền tảng embedding, RNN, LSTM

> Bài báo: *Character-Aware Neural Language Models* (Kim, Jernite, Sontag, Rush, AAAI-2016).
>
> **Cách đọc file này:**
> - Kiến thức được sắp xếp **theo thứ tự cần học**: khái niệm nào dùng ở mục nào thì được giải thích ở mục đó (hoặc sớm hơn), không lặp lại.
> - Mọi **câu trích từ bài báo** đều kèm **bản dịch tiếng Việt** ngay bên dưới.
> - Cuối mỗi mục có phần **"Bài báo nói gì / người học tự thêm gì"** để biết cái nào được phép trích dẫn như của bài báo.
> - Mỗi bước học nằm trong **một file riêng**. Hai phần "Timeline" và "Tiến độ chung" bên dưới **giống nhau ở mọi file**; khi cập nhật hãy sửa ở tất cả các file.
> - Khái niệm đã học ở Bước 1 (mô hình ngôn ngữ, tham số, loss, PPL, NLM, word embedding ở mức tổng quát...) xem [ghi_chu_buoc_1.md](ghi_chu_buoc_1.md), không giải thích lại ở đây.

**Các file ghi chú:**
- [ghi_chu_buoc_1.md](ghi_chu_buoc_1.md): Bước 1, Bài toán và động lực
- [ghi_chu_buoc_2.md](ghi_chu_buoc_2.md): Bước 2, Nền tảng: embedding, RNN, LSTM (**file này**)

## Timeline

Ngày ghi theo các phiên làm việc (có thể chỉnh lại cho đúng thực tế). Các bước chưa học để trống ngày dự kiến, nhóm tự điền.

| Ngày | Mốc | Kết quả |
|---|---|---|
| 14/10/2026 | Khởi động: đọc yêu cầu báo cáo, bài báo gốc và 7 slide bài giảng; lập lộ trình 8 bước | Lộ trình học; xác định slide chưa dạy mạng nơ-ron |
| 14/10/2026 | Học 1.1 (mô hình ngôn ngữ, n-gram) và 1.2 (Input/Output, huấn luyện, perplexity); tạo file ghi chú | Ghi 1.1, 1.2 |
| 15/10/2026 | Học 1.3 (vấn đề của n-gram và NLM thông thường) và bản đầu của 1.4 | Ghi 1.3 |
| 26/10/2026 | Làm rõ từng khái niệm (hình vị, OOV, Highway, tham số, PTB, T/\|V\|/\|C\|); sắp xếp lại file theo đúng thứ tự học, thêm bản dịch cho mọi câu trích; hoàn thiện 1.4 và 1.5 | Ghi đủ 1.1 đến 1.5; hoàn thành Bước 1 |
| 26/10/2026 | Tách mỗi bước thành một file riêng; tạo file Bước 2; commit và push | `ghi_chu_buoc_1.md`, `ghi_chu_buoc_2.md` |
| ...... | Bước 2: embedding, RNN, LSTM | (điền ngày) |
| ...... | Bước 3: CharCNN | (điền ngày) |
| ...... | Bước 4: Highway, softmax, hàm mất mát, perplexity | (điền ngày) |
| ...... | Bước 5: Dữ liệu | (điền ngày) |
| ...... | Bước 6: Siêu tham số, huấn luyện | (điền ngày) |
| ...... | Bước 7: Kết quả | (điền ngày) |
| ...... | Bước 8: Thảo luận, kết luận, soạn slide; nhóm thống nhất % đóng góp | (điền ngày) |

## Tiến độ chung (tất cả các bước)

| Bước | Nội dung | Mục báo cáo | File | Trạng thái |
|---|---|---|---|---|
| **1** | Bài toán và động lực | Mục 1 | [ghi_chu_buoc_1.md](ghi_chu_buoc_1.md) | **Đã ghi đủ 1.1 đến 1.5** |
| 1.1 | Mô hình ngôn ngữ và n-gram | | | Xong |
| 1.2 | Input / Output, huấn luyện, tham số, perplexity, T / \|V\| / \|C\|, PTB | | | Xong |
| 1.3 | Vì sao bài báo ra đời: vấn đề của n-gram và của NLM thông thường | | | Xong |
| 1.4 | Ý tưởng giải quyết: mô hình ký tự, cách khắc phục từng vấn đề | | | Đã ghi, đang ôn |
| 1.5 | Đóng góp của bài báo | | | Đã ghi |
| **2** | Nền tảng: embedding, RNN, LSTM | Mục 2 | [ghi_chu_buoc_2.md](ghi_chu_buoc_2.md) | Chưa học (đã tạo khung) |
| **3** | CharCNN: ký tự thành vector của từ | Mục 2 | (sẽ tạo) | Chưa học |
| **4** | Highway, softmax, hàm mất mát, perplexity | Mục 2 | (sẽ tạo) | Chưa học |
| **5** | Dữ liệu (Bảng 1) | Mục 3 | (sẽ tạo) | Chưa học |
| **6** | Siêu tham số, huấn luyện (Bảng 2) | Mục 4 | (sẽ tạo) | Chưa học |
| **7** | Kết quả (Bảng 3–8, PCA, nearest neighbor) | Mục 5 | (sẽ tạo) | Chưa học |
| **8** | Thảo luận, kết luận, soạn slide | Mục 5, 6 | (sẽ tạo) | Chưa học |

**Đối chiếu với 6 mục yêu cầu của báo cáo:** Mục 1 gần như xong; Mục 2 mới có ý tưởng tổng quát (còn cơ chế CNN, LSTM, Highway, softmax); Mục 3, 4 mới có một phần nhỏ; Mục 5 đã có phần lớn kết quả chính; Mục 6 (% đóng góp của 5 thành viên) do nhóm tự thống nhất.

## Tiến độ của riêng Bước 2

| Mục | Nội dung | Trạng thái |
|---|---|---|
| 2.1 | Chuẩn bị toán: vector, ma trận, nhân ma trận với vector, hàm sigmoid σ, tanh, phép nhân từng phần tử ⊙ | Chưa học |
| 2.2 | Mạng nơ-ron cơ bản: nơ-ron, phép biến đổi affine (Wx + b) và hàm phi tuyến | Chưa học |
| 2.3 | Word embedding chi tiết: bảng tra cứu, số chiều, one-hot so với embedding | Chưa học |
| 2.4 | RNN: ký ức qua các bước thời gian, phương trình (1) | Chưa học |
| 2.5 | Vì sao RNN thường khó học: gradient biến mất / bùng nổ | Chưa học |
| 2.6 | LSTM: ô nhớ và các cổng, phương trình (2) | Chưa học |
| 2.7 | LSTM nhiều lớp (multi-layer) | Chưa học |
| 2.8 | Ráp lại thành RNN-LM (nối sang softmax ở Bước 4) | Chưa học |

## Mục lục của file này

- [Kế hoạch học Bước 2](#kế-hoạch-học-bước-2)
- 2.1 Chuẩn bị toán *(chưa ghi)*
- 2.2 Mạng nơ-ron cơ bản *(chưa ghi)*
- 2.3 Word embedding chi tiết *(chưa ghi)*
- 2.4 RNN *(chưa ghi)*
- 2.5 Gradient biến mất / bùng nổ *(chưa ghi)*
- 2.6 LSTM *(chưa ghi)*
- 2.7 LSTM nhiều lớp *(chưa ghi)*
- 2.8 Ráp lại thành RNN-LM *(chưa ghi)*
- [Bảng thuật ngữ của Bước 2](#bảng-thuật-ngữ-của-bước-2)
- [Câu hỏi tự kiểm tra của Bước 2](#câu-hỏi-tự-kiểm-tra-của-bước-2)

---

# BƯỚC 2: Nền tảng embedding, RNN, LSTM

## Kế hoạch học Bước 2

**Mục tiêu:** hiểu hai khối còn lại của mô hình ở mức cơ chế: bảng embedding và phần **LSTM** (khối 3 trong sơ đồ ở mục 1.4 của Bước 1). Hai khối CharCNN và Highway học ở Bước 3 và 4.

**Phần bài báo liên quan:** mục "Model → Recurrent Neural Network" (trang 2742), gồm phương trình (1) cho RNN và phương trình (2) cho LSTM, cùng mô tả "nhiều lớp"; và Bảng 2 (LSTM 2 lớp, 300 / 650 đơn vị ẩn). Phương trình (3) và (4) (RNN-LM, softmax, NLL) thuộc Bước 4.

**Tại sao cần học trước:** các bước 3 và 4 đều dùng kết quả của Bước 2. Ví dụ Highway giống "ô nhớ của LSTM", và vector từ do CharCNN tạo ra là **đầu vào của LSTM**.

**Cách học đề xuất:** mỗi mục dùng ví dụ số nhỏ (vector 2 đến 3 chiều) tính tay, kèm ví dụ thực tế; câu trích từ bài báo có bản dịch; cuối mục có phần "bài báo nói gì / người học tự thêm gì".

**Xuất phát từ Bước 1:**
- Ở 1.2 đã biết: mô hình đọc câu từng từ một (mỗi lần là một time step), kết hợp từ vừa đọc với "ký ức" các từ trước (do LSTM giữ).
- Ở 1.3 đã biết: word embedding là vector số của từ; NLM thông thường tạo nó bằng cách tra bảng.
- Ở 1.4 đã biết: sơ đồ 3 khối và phần chạy thử "absurdity" với kích thước thật (LSTM 2 lớp, 300 đơn vị ẩn).

Bước 2 sẽ trả lời: **"ký ức" cụ thể là gì và LSTM giữ nó bằng cách nào?**

*(Nội dung các mục 2.1 đến 2.8 sẽ được bổ sung bên dưới khi học.)*

---

## Bảng thuật ngữ của Bước 2

Thuật ngữ của Bước 1 xem [ghi_chu_buoc_1.md](ghi_chu_buoc_1.md#bảng-thuật-ngữ-cập-nhật-dần).

| Thuật ngữ | Giải thích đời thường | Học ở |
|---|---|---|
| *(chưa có)* | | |

---

## Câu hỏi tự kiểm tra của Bước 2

*(Sẽ bổ sung cùng nội dung các mục.)*

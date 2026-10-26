# Ghi chú học tập, BƯỚC 1: Bài toán và động lực

> Bài báo: *Character-Aware Neural Language Models* (Kim, Jernite, Sontag, Rush, AAAI-2016).
>
> **Cách đọc file này:**
> - Kiến thức được sắp xếp **theo thứ tự cần học**: khái niệm nào dùng ở mục nào thì được giải thích ở mục đó (hoặc sớm hơn), không lặp lại.
> - Mọi **câu trích từ bài báo** đều kèm **bản dịch tiếng Việt** ngay bên dưới.
> - Cuối mỗi mục có phần **"Bài báo nói gì / người học tự thêm gì"** để biết cái nào được phép trích dẫn như của bài báo.
> - Mỗi bước học nằm trong **một file riêng**. Hai phần "Timeline" và "Tiến độ chung" bên dưới **giống nhau ở mọi file**; khi cập nhật hãy sửa ở tất cả các file.

**Các file ghi chú:**
- [ghi_chu_buoc_1.md](ghi_chu_buoc_1.md): Bước 1, Bài toán và động lực (**file này**)
- [ghi_chu_buoc_2.md](ghi_chu_buoc_2.md): Bước 2, Nền tảng: embedding, RNN, LSTM

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

## Mục lục của file này

- [1.1. Mô hình ngôn ngữ (Language Model)](#11-mô-hình-ngôn-ngữ-language-model), gồm mô hình n-gram
- [1.2. Input, Output, huấn luyện và perplexity](#12-input-output-huấn-luyện-và-perplexity-mục-1-của-báo-cáo), gồm tham số, T / |V| / |C|, PTB
- [1.3. Vì sao bài báo ra đời](#13-vì-sao-bài-báo-ra-đời-vấn-đề-của-n-gram-và-của-nlm-thông-thường), gồm làm mịn, NLM, NLM thông thường, vấn đề A và B, OOV
- [1.4. Ý tưởng giải quyết của bài báo](#14-ý-tưởng-giải-quyết-của-bài-báo), gồm mô hình từ / hình vị / ký tự, chia sẻ tham số, Highway, chạy thử
- [1.5. Đóng góp của bài báo](#15-đóng-góp-của-bài-báo)
- [Bảng thuật ngữ](#bảng-thuật-ngữ-cập-nhật-dần)
- [Câu hỏi tự kiểm tra](#câu-hỏi-tự-kiểm-tra)

**Lưu ý:** slide bài giảng chưa dạy mạng nơ-ron (CNN, LSTM, embedding). Các phần đó học từ Bước 2 trở đi. Bước 1 dựa vào những gì đã học: n-gram, perplexity, làm mịn, hình thái học (slide Bài 1, Bài 2, Bài 3).

---

# BƯỚC 1: Bài toán mà bài báo giải quyết

## 1.1. Mô hình ngôn ngữ (Language Model)

### Ý chính
**Mô hình ngôn ngữ là một "bộ chấm điểm" cho câu hoặc cho từ kế tiếp.** Nó cho biết một chuỗi từ nghe có tự nhiên không, và từ nào có khả năng xuất hiện tiếp theo. Slide Bài 2 định nghĩa: mô hình ngôn ngữ là *phân phối xác suất trên các tập văn bản*.

Ký hiệu trong bài báo:

> P(từ kế tiếp | các từ đã có) = P(w_{t+1} | w_1, ..., w_t)

Đọc là "xác suất của từ kế tiếp, **biết rằng** các từ trước đó là như vậy". Đây chính là công thức chuỗi xác suất ở slide Bài 2 (P(w_m | w_1 ... w_{m-1})).

Mô hình **không hiểu nghĩa** như con người. Nó chỉ học từ rất nhiều văn bản có sẵn xem từ nào hay đi sau từ nào.

### Ví dụ thực tế 1: Gợi ý từ trên bàn phím điện thoại
Bạn gõ: **"Tối nay mình đi ăn ..."**. Điện thoại gợi ý 3 từ: *cơm*, *phở*, *tối*. Mô hình ngôn ngữ đang tính:

| Từ có thể xuất hiện tiếp | Xác suất (ví dụ minh họa) |
|---|---|
| cơm | 25% |
| phở | 18% |
| tối | 10% |
| ... | ... |
| bàn | 0,0001% |
| xanh | 0,0001% |

Trong ví dụ này, P(cơm | Tối nay mình đi ăn) = 25%.

### Ví dụ thực tế 2: Chấm điểm cả câu (có trong slide Bài 2)
> P("hôm nay trời đẹp") **>** P("trời đẹp nay hôm")

Hai câu có cùng các từ, nhưng câu đầu tự nhiên nên điểm cao, câu sau bị xáo trộn nên điểm thấp.

Ứng dụng: khi bạn nói vào Google Assistant "hôm nay trời đẹp", máy nghe ra nhiều cách viết khác nhau. Mô hình ngôn ngữ giúp chọn cách viết đúng:

| Cách máy nghe ra | Điểm của mô hình ngôn ngữ |
|---|---|
| "hôm nay trời đẹp" | Cao (chọn) |
| "hôm nay chời đẹp" | Thấp |
| "ôm nay trời đẹp" | Thấp |

### Ví dụ thực tế 3: Dịch máy (có trong slide Bài 1)
Máy dịch câu tiếng Pháp *"L'avocat général"*. Có hai bản dịch ứng viên:
- "the **attorney** general" (Tổng chưởng lý): điểm **cao**.
- "the general **avocado**" (quả bơ tướng quân): điểm **cực thấp**, vì chưa ai viết như vậy.

Mô hình ngôn ngữ giúp máy chọn bản dịch hợp lý.

### Ứng dụng (bài báo nêu ở câu đầu của phần Introduction)
> *"Language modeling is a fundamental task in artificial intelligence and natural language processing (NLP), with applications in speech recognition, text generation, and machine translation."*
>
> **Dịch:** Mô hình hóa ngôn ngữ là một tác vụ nền tảng trong trí tuệ nhân tạo và xử lý ngôn ngữ tự nhiên (NLP), với các ứng dụng trong nhận dạng giọng nói, sinh văn bản và dịch máy.

---

### Mô hình n-gram: cách làm mô hình ngôn ngữ bằng **đếm** (slide Bài 2)

#### Định nghĩa
**n-gram là tên chung.** Chữ "n" là số từ mà mô hình nhìn lại để đoán từ kế tiếp, tính cả từ cần đoán. Tức là nhìn lại **n−1 từ trước**.

| Tên | n | Đoán từ kế tiếp dựa vào |
|---|---|---|
| unigram | 1 | **Không nhìn từ nào trước đó**, chỉ dựa vào độ phổ biến của từ |
| bigram | 2 | **1 từ** ngay trước |
| trigram | 3 | **2 từ** ngay trước |
| 4-gram | 4 | 3 từ ngay trước |
| n-gram | n | n−1 từ ngay trước |

Bigram và trigram chỉ là hai trường hợp của n-gram (n = 2 và n = 3).

Bài báo mô tả cách làm truyền thống:
> *"...traditional methods usually involve making an n-th order Markov assumption and estimating n-gram probabilities via counting and subsequent smoothing."*
>
> **Dịch:** ...các phương pháp truyền thống thường đưa ra giả định Markov bậc n và ước lượng xác suất n-gram bằng cách đếm, sau đó làm mịn.

(Giả định Markov bậc n chính là ý "chỉ nhìn n−1 từ trước" trong slide Bài 2.)

#### Ví dụ thực tế: đoán từ sau câu "Tối nay mình đi ăn ___"

| Mô hình | Nhìn vào | Mô hình tự hỏi | Nhận xét |
|---|---|---|---|
| **Unigram** | Không nhìn gì | "Từ nào phổ biến nhất tiếng Việt?" → và, là, của... | Không liên quan ngữ cảnh. Slide: xác suất mỗi từ độc lập với từ khác |
| **Bigram** | "ăn" | "Sau 'ăn' thường là gì?" → cơm, sáng, tối, chơi... | Có thể gợi ý nhầm, vì "ăn chơi" cũng phổ biến |
| **Trigram** | "đi ăn" | "Sau 'đi ăn' thường là gì?" → cơm, phở, tối, sáng... | Chính xác hơn vì ngữ cảnh dài hơn |
| **4-gram** | "mình đi ăn" | tương tự | Chính xác hơn nữa, nhưng xem phần nhược điểm bên dưới |

#### Công thức trong slide Bài 2
- **Bigram:** P(w_m | w_{m-1}), chỉ cần 1 từ ngay trước.
- **Trigram:** P(w_m | w_{m-2}, w_{m-1}), cần 2 từ ngay trước.
- Cách ước lượng (MLE) là **đếm**: P(w_m | w_{m-1}) = số lần cặp (w_{m-1}, w_m) xuất hiện ÷ số lần w_{m-1} xuất hiện.

Ví dụ số trong slide, với 3 câu huấn luyện:
```
<s> I am Sam </s>
<s> Sam I am </s>
<s> I do not like green eggs and ham </s>
```
- P(am | I) = số lần "I am" ÷ số lần "I" = 2/3 ≈ 0,67
- P(Sam | `<s>`) = 1/3 ≈ 0,33

(`<s>` và `</s>` là ký hiệu đầu câu và cuối câu.)

#### Nhược điểm: n càng lớn càng bị "thưa dữ liệu" (data sparsity)

| n lớn lên | Ưu | Nhược |
|---|---|---|
| Ngữ cảnh nhiều hơn | Dự đoán chính xác hơn | **Cụm càng dài càng hiếm gặp lại** |

Ví dụ: cụm "mình đi ăn" có thể gặp nhiều lần trong dữ liệu, nhưng cụm 6 từ "tối nay mình đi ăn cùng" có thể chưa xuất hiện lần nào. Khi đó xác suất đếm được là **0**.

Slide Bài 2 gọi là "TH xác suất = 0" và chữa bằng **làm mịn** (Laplace / add-one: cộng thêm 1 vào mọi số đếm). Ví dụ có số và đánh giá làm mịn ở **mục 1.3**.

#### Liên hệ với bài báo
- **KN-5** (Bảng 3) = mô hình n-gram với n = 5, làm mịn kiểu **Kneser-Ney**, dùng làm mốc so sánh "không dùng nơ-ron".
- **KN-4** (Bảng 4, 5) = n-gram với n = 4.

### Tóm tắt 1.1 (3 ý cần nhớ)
1. Mô hình ngôn ngữ = **dự đoán từ kế tiếp** (hoặc chấm độ tự nhiên của câu).
2. Nó học từ **lượng lớn văn bản có sẵn**, không phải hiểu nghĩa như người.
3. n-gram là cách làm bằng **đếm**: bigram nhìn 1 từ trước, trigram nhìn 2 từ trước; n lớn thì chính xác hơn nhưng dễ bị thưa dữ liệu.

---

## 1.2. Input, Output, huấn luyện và perplexity (mục 1 của báo cáo)

### Ý chính
- **Input:** các từ đã có trong câu. Điểm riêng của bài báo: mỗi từ được đưa vào máy **dưới dạng từng ký tự** (cách làm cụ thể ở 1.4).
- **Output:** một bảng xác suất cho **tất cả các từ trong từ điển**, cho biết từ nào có khả năng xuất hiện tiếp theo.

Điểm khác thường: **đầu vào là ký tự, đầu ra vẫn là từ.** Câu trong Abstract:
> *"We describe a simple neural language model that relies only on character-level inputs. Predictions are still made at the word-level."*
>
> **Dịch:** Chúng tôi mô tả một mô hình ngôn ngữ nơ-ron đơn giản chỉ dựa vào đầu vào ở mức ký tự. Các dự đoán vẫn được thực hiện ở mức từ.

### Output: "bảng xác suất trên toàn bộ từ vựng"

**Từ vựng (vocabulary, ký hiệu V)** là danh sách tất cả các từ mà mô hình biết. Bộ dữ liệu tiếng Anh nhỏ trong bài báo có |V| = 10.000 từ.

Output là danh sách 10.000 xác suất, mỗi từ một con số, và **tổng bằng 100%**:

| Từ trong từ điển | Xác suất |
|---|---|
| is | 20% |
| was | 12% |
| can | 5% |
| ... | ... |
| banana | 0,00001% |
| *(10.000 dòng)* | |
| **Tổng** | **100%** |

Công thức P(w_{t+1} = j | w_{1:t}) chỉ có nghĩa là "xác suất để từ kế tiếp là từ số j trong từ điển". Hàm làm ra bảng này tên là **softmax** (học ở Bước 4).

### Đo kích thước dữ liệu: token (T), từ vựng |V|, số ký tự |C|

Bảng 1 của bài báo dùng ba ký hiệu đo ba thứ **khác nhau**:

| Ký hiệu | Tên | Đếm cái gì |
|---|---|---|
| **T** | Số token (quy mô) | **Tổng số từ** trong văn bản, **mỗi lần xuất hiện đều đếm** |
| **\|V\|** | Từ vựng của từ | Số **từ khác nhau** (mỗi từ đếm 1 lần) |
| **\|C\|** | Từ vựng của ký tự | Số **ký tự khác nhau** (mỗi ký tự đếm 1 lần) |

> *"|V| = word vocabulary size; |C| = character vocabulary size; T = number of tokens in training set."*
>
> **Dịch:** |V| = kích thước từ vựng mức từ; |C| = kích thước từ vựng mức ký tự; T = số token trong tập huấn luyện.

**Ví dụ nhỏ: câu "the cat sat on the mat"**

| Con số | Cách đếm | Kết quả |
|---|---|---|
| **T** | the, cat, sat, on, the, mat | **6** ("the" đếm 2 lần) |
| **\|V\|** | the, cat, sat, on, mat | **5** ("the" chỉ đếm 1 lần) |
| **\|C\|** | t, h, e, c, a, s, o, n, m | **9** (ký tự lặp chỉ đếm 1 lần) |

**Ví dụ thực tế (một cuốn sách):** **T** giống tổng số chữ in trong sách; **|V|** giống số mục từ phải tra nếu viết từ điển cho cuốn sách đó; **|C|** giống số chữ cái và dấu khác nhau xuất hiện trong sách.

**Vì sao cần phân biệt?** Chúng quyết định kích thước mô hình (vấn đề B ở 1.3):
- Bảng word embedding có kích thước theo **|V|**: 10.000 từ × 200 chiều = 2.000.000 tham số.
- Bảng ký tự có kích thước theo **|C|**: 51 ký tự × 15 chiều = 765 tham số.
- **T** không làm mô hình to ra; nó chỉ cho biết có bao nhiêu dữ liệu để học (T lớn thì học được nhiều hơn nhưng huấn luyện lâu hơn).

Bài báo ghi chú vì sao |C| đôi khi khá lớn (ví dụ 197, 260):
> *"|C| is large because of (rarely occurring) special characters."*
>
> **Dịch:** |C| lớn là do các ký tự đặc biệt (hiếm khi xuất hiện).

### PTB là gì?

**PTB = Penn Treebank**, kho ngữ liệu tiếng Anh do Đại học Pennsylvania xây dựng (Marcus, Santorini, Marcinkiewicz 1993). *Treebank* nghĩa là "ngân hàng cây": kho văn bản mà mỗi câu được người gán sẵn cây cú pháp và nhãn từ loại. Slide Bài 4 nhắc đến **tập nhãn Penn Treebank (45 nhãn)** và slide Bài 6 nhắc **Penn Treebank có 1 triệu từ**, là nguồn ngữ liệu quan trọng cho phân tích cú pháp. Bài báo dùng **cùng kho văn bản đó** nhưng cho việc khác: mô hình ngôn ngữ chỉ dùng phần **văn bản thô**, không dùng cây cú pháp hay nhãn từ loại.

> *"We conduct hyperparameter search, model introspection, and ablation studies on the English Penn Treebank (PTB) (Marcus, Santorini, and Marcinkiewicz 1993), utilizing the standard training (0-20), validation (21-22), and test (23-24) splits along with pre-processing by Mikolov et al. (2010). With approximately 1m tokens and |V| = 10k, this version has been extensively used by the language modeling community and is publicly available."*
>
> **Dịch:** Chúng tôi tiến hành tìm kiếm siêu tham số, khảo sát bên trong mô hình và các thí nghiệm loại bỏ trên Penn Treebank (PTB) tiếng Anh (Marcus, Santorini và Marcinkiewicz 1993), dùng cách chia chuẩn gồm huấn luyện (các phần 0–20), kiểm định (21–22) và kiểm tra (23–24), cùng với tiền xử lý của Mikolov và cộng sự (2010). Với khoảng 1 triệu token và |V| = 10 nghìn, phiên bản này đã được cộng đồng mô hình ngôn ngữ dùng rộng rãi và được công bố công khai.

| Thông tin PTB | Giá trị |
|---|---|
| Quy mô T | Khoảng **1 triệu token** |
| Từ vựng \|V\| | **10.000 từ** |
| Số ký tự \|C\| | **51** (Bảng 1) |
| Chia dữ liệu | Train: phần 0–20; Validation: 21–22; Test: 23–24 |

**Vì sao dùng PTB?** (1) Là **chuẩn so sánh**: hầu như mọi nghiên cứu mô hình ngôn ngữ thời đó đều báo cáo trên PTB, nên so được trực tiếp (các số PPL ở Bảng 3 đều là trên PTB). (2) Nhỏ, chạy thử nhanh, dùng cho thử siêu tham số và thí nghiệm loại bỏ. Ví dụ thực tế: PTB giống **một kỳ thi chuẩn** (như IELTS); mọi thí sinh thi cùng một đề thì mới so điểm được.

PTB tiếng Anh chỉ là **một trong nhiều bộ dữ liệu** của bài báo; các ngôn ngữ khác dùng dữ liệu khác (Bước 5). *Kiến thức ngoài bài báo:* bản PTB dùng cho mô hình ngôn ngữ (do Mikolov xử lý) nổi tiếng là đã viết thường, bỏ dấu câu, thay số bằng một ký hiệu chung và thay từ ngoài 10.000 từ bằng `<unk>`; bài báo chỉ nói "tiền xử lý của Mikolov và cộng sự (2010)", nên nếu cần nêu cụ thể hãy kiểm tra thêm nguồn khác.

### Input: chuỗi từ đã xuất hiện

Mô hình đọc câu **từng từ một**; mỗi lần đọc một từ gọi là một **bước (time step)**. Ở mỗi bước, mô hình kết hợp từ vừa đọc với "ký ức" về các từ đã đọc trước đó (ký ức do LSTM giữ, học ở Bước 2) để đoán từ kế tiếp.

*Cách mỗi từ được biến thành vector đưa vào mô hình (tra bảng hay đọc ký tự) là chỗ bài báo khác các mô hình thông thường; xem **1.3** (cách thông thường) và **1.4** (cách của bài báo).*

### Một lượt chạy cụ thể (Hình 1 của bài báo)

Chú thích Hình 1:
> *"Here the model takes absurdity as the current input and combines it with the history (as represented by the hidden state) to predict the next word, is."*
>
> **Dịch:** Ở đây mô hình nhận *absurdity* làm đầu vào hiện tại và kết hợp nó với lịch sử (được biểu diễn bằng trạng thái ẩn) để dự đoán từ tiếp theo là *is*.

Minh họa (các từ đứng trước "absurdity" do người học thêm vào cho dễ hình dung):

| Bước | Từ đang đọc | Mô hình làm gì | Output |
|---|---|---|---|
| t = 1 | "On" | Đọc từ, kết hợp với ký ức | Bảng xác suất từ kế tiếp |
| t = 2 | "the" | Đọc từ, kết hợp ký ức | Bảng xác suất từ kế tiếp |
| ... | ... | ... | ... |
| t = k | **"absurdity"** | Đọc từ, kết hợp ký ức | Bảng xác suất: **"is"** cao nhất |

Hai điều rút ra:
1. **Input mỗi bước = từ hiện tại + "ký ức" về các từ đã đọc trước.**
2. **Output mỗi bước = bảng xác suất cho từ kế tiếp.** Kết quả được so với từ thật trong dữ liệu để biết đoán đúng hay sai, rồi mô hình điều chỉnh để lần sau đoán tốt hơn. Đó là **huấn luyện**, giải thích ngay dưới đây.

### Huấn luyện (training) và tham số

#### Ý chính
Mô hình **học bằng cách đoán, bị chấm điểm, rồi chỉnh lại**, lặp đi lặp lại rất nhiều lần.

#### Ví dụ thực tế: học sinh làm đề rồi đối chiếu đáp án
1. **Làm bài:** chọn đáp án theo hiểu biết hiện tại.
2. **Đối chiếu đáp án thật:** biết mình đúng hay sai, sai nhiều hay ít.
3. **Rút kinh nghiệm:** điều chỉnh cách học (ôn lại phần bị sai).
4. **Làm đề tiếp theo**, lặp lại hàng nghìn lần. Điểm dần tăng.

Mô hình ngôn ngữ làm y như vậy, chỉ khác là "đề thi" là các câu trong kho văn bản.

#### Áp vào mô hình, từng bước
Giả sử trong dữ liệu có câu thật: **"Tối nay mình đi ăn cơm"**.

**Bước 1: Mô hình đoán.** Đưa vào "Tối nay mình đi ăn", mô hình trả ra bảng xác suất cho từ kế tiếp:

| Từ | Xác suất mô hình đoán |
|---|---|
| phở | 40% |
| bún | 30% |
| **cơm** | **2%** |
| ... | ... |

**Bước 2: So với từ thật.** Từ thật là "cơm", mô hình chỉ cho 2%, tức là đoán tệ. Độ tệ được đo bằng một con số gọi là **loss (độ lỗi)**. Bài báo dùng cách đo gọi là negative log-likelihood (NLL). Cần nhớ:
- Từ thật được cho xác suất **cao** → loss **nhỏ** (đoán tốt).
- Từ thật được cho xác suất **thấp** → loss **lớn** (đoán tệ).

| Xác suất mô hình cho từ thật | Loss | Nhận xét |
|---|---|---|
| 90% | Rất nhỏ | Đoán rất tốt |
| 20% | Trung bình | |
| 2% | Lớn | Đoán tệ, cần chỉnh nhiều |

**Bước 3: Điều chỉnh tham số.** (Giải thích "tham số" ở mục ngay bên dưới.) Mô hình vặn các "nút" bên trong để lần sau từ "cơm" được cho xác suất cao hơn một chút sau câu "Tối nay mình đi ăn". Thuật toán quyết định vặn nút nào, vặn bao nhiêu, gọi là **SGD** (stochastic gradient descent) kết hợp **backpropagation** (lan truyền ngược). Bài báo dùng chúng; chi tiết học ở Bước 6. Hiện tại chỉ cần hiểu là "tự động tìm cách chỉnh để loss giảm".

**Bước 4: Lặp lại.** Làm với **hàng triệu từ** trong kho dữ liệu (bộ tiếng Anh nhỏ của bài báo có khoảng 1 triệu từ) và lặp nhiều vòng. Bài báo huấn luyện 25–30 **epoch**, mỗi epoch là một lượt đọc hết toàn bộ dữ liệu huấn luyện.

Kết quả: đầu huấn luyện mô hình gần như đoán bừa (PPL rất cao); sau nhiều vòng PPL giảm dần.

```
Đầu huấn luyện:  PPL cao  ████████████████  (đoán bừa)
Giữa quá trình:  PPL giảm ████████
Cuối huấn luyện: PPL thấp ███                (đoán tốt)
```

#### Tham số (parameter) là gì?
**Tham số là những con số bên trong mô hình mà mô hình tự học được từ dữ liệu.** Chúng quyết định mô hình biến đầu vào thành đầu ra như thế nào.

**Ví dụ thực tế 1: công thức dự đoán giá nhà.** Một "mô hình" đơn giản:

> Giá = **a** × (diện tích) + **b** × (số phòng ngủ) + **c**

Ba con số **a, b, c** là **tham số**. Đưa cho mô hình hàng nghìn căn nhà đã biết giá thật, nó **tự tìm** a, b, c sao cho dự đoán gần giá thật nhất (ví dụ a = 30 triệu/m², b = 200 triệu, c = 500 triệu).

| | Giá trị | Ai quyết định? |
|---|---|---|
| Dạng công thức "a × diện tích + b × phòng ngủ + c" | Cố định | Con người thiết kế |
| a, b, c | 30, 200, 500 | **Mô hình tự học** → đây là **tham số** |

**Ví dụ thực tế 2: nút vặn trên bàn trộn âm thanh (mixer).** Âm thanh ra chưa hay thì bạn vặn nút này lên, nút kia xuống một chút. Mô hình tự vặn các nút. **Mỗi nút là một tham số**; mô hình càng phức tạp càng nhiều nút (hàng triệu).

#### Tham số khác "siêu tham số" (hyperparameter)

| | Tham số (parameter) | Siêu tham số (hyperparameter) |
|---|---|---|
| Ai đặt giá trị? | **Mô hình tự học** | **Con người chọn trước** khi huấn luyện |
| Ví dụ | Các số trong bảng vector, trong LSTM... | Số lớp LSTM, số đơn vị ẩn, tốc độ học, số epoch |
| Ví dụ thực tế (nấu ăn) | Độ mặn của nồi sau khi nếm và nêm dần | **Công thức**: chọn nồi cỡ nào, nấu bao lâu |

Cách nhớ: **siêu tham số là bạn chọn, tham số là máy học.** Bảng siêu tham số của bài báo (Bảng 2) học ở Bước 6. Vị trí các tham số trong mô hình và số lượng của chúng xem ở **1.4**.

#### Vì sao chia dữ liệu thành train / validation / test?
Slide Bài 2: huấn luyện trên **training set**, đánh giá trên **test set** (dữ liệu **mới**, chưa từng thấy).

Ví dụ thực tế: học sinh luyện đề cũ rồi thi lại **chính đề cũ** thì điểm cao là hiển nhiên, không chứng tỏ gì. Muốn biết có giỏi thật phải thi bằng **đề mới**.

| Phần | Vai trò | Ví dụ thực tế |
|---|---|---|
| **Train** (huấn luyện) | Để mô hình học | Làm bài tập về nhà |
| **Validation** (kiểm định) | Theo dõi và chọn mô hình tốt nhất khi đang học | Thi thử |
| **Test** (kiểm tra) | Chấm điểm cuối cùng | Thi thật |

(Bài báo chia Penn Treebank thành train, validation, test; xem thêm ở Bước 5.)

### Thước đo: Perplexity (PPL), "độ phức tạp" trong slide Bài 2

**PPL càng thấp, mô hình càng tốt.** PPL có thể hiểu là "mô hình đang bối rối như phải chọn đều giữa bao nhiêu lựa chọn".

Ví dụ trong slide: mô hình phải đoán một chữ số ngẫu nhiên 0–9 và không biết gì nên cho mỗi chữ số 10% → **PPL = 10**.

Áp vào bài báo (Bảng 3, tiếng Anh, bộ Penn Treebank):

| Mô hình | PPL | Ý nghĩa |
|---|---|---|
| Mô hình bài báo (LSTM-Char-Large) | 78,9 | Bối rối như chọn giữa khoảng 79 từ ngang nhau |
| n-gram KN-5 (không nơ-ron) | 141,2 | Bối rối như chọn giữa khoảng 141 từ |

Công thức trong bài báo: PPL = exp(NLL / T), trong đó NLL là tổng loss (âm log xác suất) trên T từ của tập kiểm tra. Đây là cách viết khác của công thức "nghịch đảo xác suất, chuẩn hóa theo số từ" ở slide. Sẽ giải thích kỹ ở Bước 4.

### Bảng tóm tắt 1.2 (có thể chép vào báo cáo)

| | Nội dung |
|---|---|
| **Input** | Chuỗi từ đã xuất hiện w₁…w_t; mỗi từ được đưa vào dưới dạng chuỗi ký tự |
| **Output** | Phân phối xác suất P(w_{t+1} \| w₁…w_t) trên toàn bộ từ vựng, tức dự đoán từ kế tiếp |
| **Đo bằng** | Perplexity (càng thấp càng tốt) |
| **Điểm khác thường** | Đầu vào là ký tự, đầu ra vẫn là từ |

---

## 1.3. Vì sao bài báo ra đời? Vấn đề của n-gram và của NLM thông thường

### Tổng quan
Có thể hình dung như câu chuyện "sửa lỗi qua từng thế hệ":

```
Thế hệ 1: n-gram           →  gặp lỗi "thưa dữ liệu"
Thế hệ 2: NLM              →  chữa được lỗi đó
          (NLM thông thường)→  nhưng lại có 2 vấn đề: A) "mù" với cấu trúc bên trong từ
                                                     B) quá nhiều tham số
Thế hệ 3: bài báo (1.4)    →  chữa A và B bằng cách đọc ký tự
```

---

### Vấn đề của n-gram: "thưa dữ liệu", làm mịn chưa đủ

**Ví dụ thực tế:** học sinh **học thuộc lòng đề cũ**. Đề năm nay có câu y hệt đề cũ thì làm được; gặp câu mới thì bí. n-gram cũng vậy.

Dữ liệu huấn luyện có câu "Tôi uống cà phê sữa đá" nhưng **không có** "Tôi uống trà sữa đá". Mô hình đếm "uống trà" = 0 lần → xác suất **0**, dù ngoài đời đây là câu bình thường. Đây là "TH xác suất = 0" trong slide Bài 2.

Bài báo nói:
> *"The count-based models are simple to train, but probabilities of rare n-grams can be poorly estimated due to data sparsity (despite smoothing techniques)."*
>
> **Dịch:** Các mô hình dựa trên đếm thì dễ huấn luyện, nhưng xác suất của các n-gram hiếm có thể bị ước lượng kém do thưa dữ liệu (dù đã có các kỹ thuật làm mịn).

#### Làm mịn (smoothing) và ví dụ add-one có số
**Làm mịn** là kỹ thuật để cụm chưa gặp không bị xác suất 0. Slide Bài 2 dạy kiểu đơn giản nhất là **add-one (Laplace)**: cộng 1 vào mọi số đếm, mẫu số cộng thêm V (kích thước từ điển): (c + 1) / (N + V).

Giả sử từ điển chỉ có 5 từ: *nước, cà, sữa, trà, bàn*. Trong dữ liệu, từ **"uống"** xuất hiện 10 lần (N = 10), các từ theo sau là:

| Từ đứng sau "uống" | Số lần đếm | Chưa làm mịn (MLE) | Đếm + 1 | Sau add-one |
|---|---|---|---|---|
| nước | 6 | 6/10 = 60% | 7 | 7/15 ≈ 46,7% |
| cà (cà phê) | 3 | 30% | 4 | 4/15 ≈ 26,7% |
| sữa | 1 | 10% | 2 | 2/15 ≈ 13,3% |
| **trà** | **0** | **0%** | 1 | 1/15 ≈ **6,7%** |
| **bàn** | **0** | **0%** | 1 | 1/15 ≈ **6,7%** |
| **Tổng** | 10 | 100% | 15 | 100% |

- **Giúp được:** hết xác suất 0; "uống trà" không còn bị 0.
- **Cái giá:** xác suất bị "lấy bớt" từ từ phổ biến (nước từ 60% xuống 46,7%) để chia cho từ chưa thấy.
- **Chưa đủ (với add-one):** "trà" và "bàn" nhận **đúng bằng nhau (6,7%)**. Nhưng "uống trà" hợp lý, "uống bàn" vô nghĩa. Add-one chia đều cho mọi cụm chưa gặp, **không biết cụm nào hợp lý hơn**.
- **Lưu ý khi báo cáo:** nhận xét "chia đều" chỉ đúng cho **add-one** (kỹ thuật trong slide). Bài báo dùng **Kneser-Ney** làm mốc so sánh, tinh vi hơn add-one (có dùng thông tin từ n-gram ngắn hơn). Bài báo chỉ nói chung là làm mịn giảm nhưng **không hết** thưa dữ liệu (*"despite smoothing techniques"* = "dù đã có các kỹ thuật làm mịn"). Ví dụ trà/bàn chỉ là minh họa cho add-one.

---

### NLM ra đời để khắc phục thưa dữ liệu

#### NLM là gì?
**NLM (Neural Language Model) = Mô hình ngôn ngữ nơ-ron.** Vẫn là mô hình ngôn ngữ (đoán từ kế tiếp), nhưng làm bằng mạng nơ-ron thay vì đếm. Mỗi từ được biểu diễn bằng một **vector số** gọi là **word embedding**.

| | n-gram (slide Bài 2) | NLM |
|---|---|---|
| Cách làm | **Đếm** số lần cụm từ xuất hiện | **Học** các con số (tham số, xem 1.2) bằng mạng nơ-ron |
| Từ được biểu diễn bằng | Chính từ đó (chuỗi chữ) | Một **vector số** (word embedding) |
| Gặp cụm chưa từng thấy | Xác suất = 0 (phải làm mịn) | Vẫn đoán được, vì từ gần nghĩa có vector gần nhau |

Ví dụ thực tế: n-gram giống học sinh **học thuộc lòng**; NLM giống học sinh **hiểu bài** (hiểu "cà phê" và "trà" đều là đồ uống nên gặp câu lạ vẫn suy ra được).

Bài báo nói:
> *"Neural Language Models (NLM) address the n-gram data sparsity issue through parameterization of words as vectors (word embeddings) and using them as inputs to a neural network."*
>
> **Dịch:** Các mô hình ngôn ngữ nơ-ron (NLM) giải quyết vấn đề thưa dữ liệu của n-gram bằng cách tham số hóa các từ thành vector (word embedding) và dùng chúng làm đầu vào cho một mạng nơ-ron.

> *"Word embeddings obtained through NLMs exhibit the property whereby semantically close words are likewise close in the induced vector space."*
>
> **Dịch:** Các word embedding thu được từ NLM có tính chất là các từ gần nhau về ngữ nghĩa cũng nằm gần nhau trong không gian vector được học ra.

#### NLM khắc phục thưa dữ liệu như thế nào? (phần giải thích cơ chế là của người học)

**Gốc lỗi của n-gram:** coi các từ là **ký hiệu rời rạc, không liên quan nhau**. "cà phê", "trà", "bàn" chỉ là ba nhãn khác nhau. n-gram chỉ **đếm** xem cụm đó xuất hiện bao nhiêu lần, nên hiểu biết về "uống cà phê" **không giúp gì** cho "uống trà" (hai ô đếm riêng).

**Cách NLM chữa:**

1. **Mỗi từ có một vector (tọa độ trên bản đồ).** Ví dụ minh họa, 2 chiều (thực tế hàng trăm chiều):

   | Từ | Tọa độ (minh họa) |
   |---|---|
   | cà phê | (0,9 ; 0,8) |
   | trà | (0,85 ; 0,75) |
   | nước ngọt | (0,8 ; 0,9) |
   | bàn | (−0,7 ; 0,1) |

   ```
      cà phê •   • trà          ← đều là đồ uống, ở gần nhau
             • nước ngọt

                                 • xe máy     ← là phương tiện, nằm xa
                                    • ô tô
   ```

2. **Tọa độ không gán tay mà được học khi huấn luyện.** Những từ xuất hiện trong **ngữ cảnh giống nhau** ("pha ___", "một ly ___", "uống ___") bị kéo về cùng một vùng, vì mô hình phải đoán giống nhau ở các ngữ cảnh đó.

3. **Xác suất được tính bằng một hàm mượt trên các tọa độ**, không phải bằng bảng đếm. Đầu vào gần nhau thì đầu ra gần nhau.

**Áp vào ví dụ:** dữ liệu có "Tôi uống cà phê" rất nhiều lần, nhưng "Tôi uống trà" chưa từng xuất hiện ("trà" chỉ xuất hiện ở ngữ cảnh khác: "pha trà", "một ly trà").

| | n-gram | NLM |
|---|---|---|
| Cơ chế | Tra ô đếm "uống trà" = 0 | Hàm trên tọa độ: sau "uống", từ nào ở **vùng đồ uống**? |
| P(trà \| uống) | **0** (sau add-one: 6,7%, bằng "bàn") | **Cao** (cùng vùng với "cà phê") |
| P(bàn \| uống) | 0 (sau add-one: 6,7%) | **Rất thấp** (xa vùng đồ uống) |

**Ví dụ thực tế: dự đoán giá nhà.** n-gram giống người môi giới chỉ nhớ đúng những căn đã bán; hỏi căn chưa có trong sổ thì "không biết". NLM giống người môi giới đã học quy luật (gần trung tâm thì đắt, rộng thì đắt), nên suy ra giá căn mới từ căn tương tự. NLM **tổng quát hóa**, n-gram **học thuộc**.

**Ví dụ kinh điển (Bengio 2003):** nếu đã thấy "The **cat** is **walking** in the **bedroom**", mô hình cũng cho xác suất cao câu **chưa từng thấy** "A **dog** was **running** in a **room**", vì cat ≈ dog, walking ≈ running, bedroom ≈ room.

**Còn một lỗ hổng:** cơ chế trên chỉ chạy tốt khi các từ có tọa độ tốt, mà tọa độ chỉ được học tốt khi từ xuất hiện đủ nhiều. NLM sửa lỗi cụm từ thưa nhưng **chưa sửa được từ hiếm**. Xem phần tiếp theo.

---

### NLM thông thường (conventional NLM): tạo vector bằng cách **tra bảng theo từ**

Bài báo dùng cụm "conventional NLM" để chỉ các NLM thông dụng:
> *"Whereas a conventional NLM takes word embeddings as inputs, our model instead takes the output from a single-layer character-level convolutional neural network with max-over-time pooling."*
>
> **Dịch:** Trong khi một NLM thông thường nhận các word embedding làm đầu vào, mô hình của chúng tôi thay vào đó nhận đầu ra của một mạng nơ-ron tích chập mức ký tự một lớp có max-over-time pooling.

Cách làm cụ thể (diễn giải của người học):
1. Có một từ điển (ví dụ 10.000 từ), mỗi từ có số thứ tự.
2. Có một **bảng tra cứu (embedding matrix)** 10.000 dòng; mỗi dòng là vector của một từ.
3. Gặp từ "absurdity" (giả sử là từ số 4.217) → lấy **dòng 4.217** của bảng.
4. Đưa vector đó vào mạng nơ-ron (RNN/LSTM).

```
 NLM thông thường
 "absurdity" ──► số 4.217 ──► [tra bảng 10.000 dòng] ──► vector ──► LSTM ──► dự đoán
```

Ví dụ thực tế: bảng tra giống **danh bạ điện thoại**. Mỗi tên có một dòng, tra tên là ra. Ai không có trong danh bạ thì không tra được. Máy không hề biết "absurdity" gồm những chữ gì: với nó, từ này chỉ là cái **nhãn số** 4.217, giống như nhận biết một người **chỉ qua số căn cước**.

---

### Vấn đề A của NLM thông thường: "mù" với cấu trúc bên trong từ, từ hiếm có vector tệ

Đây là **vấn đề chính** của bài báo. Đoạn gốc:

> *"While NLMs have been shown to outperform count-based n-gram language models, they are blind to subword information (e.g. morphemes). For example, they do not know, a priori, that eventful, eventfully, uneventful, and uneventfully should have structurally related embeddings. Embeddings of rare words can thus be poorly estimated, leading to high perplexities for rare words (and words surrounding them). This is especially problematic in morphologically rich languages with long-tailed frequency distributions or domains with dynamic vocabularies (e.g. social media)."*
>
> **Dịch:** Dù NLM đã được chứng minh là vượt trội so với các mô hình ngôn ngữ n-gram dựa trên đếm, chúng "mù" với thông tin dưới mức từ (ví dụ hình vị). Chẳng hạn, ngay từ đầu chúng không biết rằng *eventful, eventfully, uneventful* và *uneventfully* nên có các embedding liên quan về cấu trúc. Do đó embedding của các từ hiếm có thể bị ước lượng kém, dẫn đến perplexity cao cho các từ hiếm (và các từ xung quanh chúng). Điều này đặc biệt nghiêm trọng với các ngôn ngữ giàu hình thái có phân phối tần suất đuôi dài, hoặc các lĩnh vực có từ vựng thay đổi liên tục (ví dụ mạng xã hội).

#### Vì sao gọi là "mù"?
Với bảng tra, "eventful", "eventfully", "uneventful", "uneventfully" chỉ là 4 dòng khác nhau, **không có liên hệ gì**. Con người nhìn là biết cùng gốc *event* (sự kiện), *-ful* (đầy), *un-* (không), *-ly* (một cách). Mô hình thì không.

**Ví dụ thực tế:** thấy tên "Nguyễn Thị Hồng Nhung" lần đầu, bạn đoán được ngay đó là nữ vì có "Thị", tức là bạn dựa vào **cấu trúc bên trong cái tên**. NLM thông thường chỉ thấy một nhãn số nên không làm được điều đó.

#### Vì sao từ xuất hiện nhiều thì vector tốt, từ hiếm thì vector tệ?
Vector của từ **không có sẵn mà được học** (cơ chế là của người học):
- Lúc đầu mọi dòng trong bảng chỉ là **số ngẫu nhiên** (bài báo khởi tạo các tham số trong khoảng [−0,05; 0,05]).
- Mỗi lần từ xuất hiện trong dữ liệu huấn luyện, mô hình đoán, bị chấm loss, rồi **chỉnh dòng vector của đúng từ đó một chút** (xem "Huấn luyện" ở 1.2).
- Chỉ khi từ xuất hiện thì dòng của nó mới được chỉnh.

| Từ | Số lần xuất hiện | Số lần vector được chỉnh | Kết quả |
|---|---|---|---|
| "the" | 50.000 | 50.000 | Vector được tinh chỉnh kỹ, phản ánh đúng cách dùng |
| "uneventfully" | 1 | 1 | Gần như vẫn là số ngẫu nhiên ban đầu |

**Ví dụ thực tế:** gặp một người 100 lần thì bạn hiểu rõ tính cách họ; chỉ gặp 1 lần trong 5 phút thì ấn tượng rất mơ hồ, có thể sai hoàn toàn.

Ở NLM thông thường, dòng của "uneventfully" **chỉ học từ chính những lần nó xuất hiện**. Nó không học được gì từ "eventful" hay "uneventful", vì chúng là dòng khác.

#### Giải thích ý: "từ hiếm có vector tệ → dự đoán sai quanh từ đó → PPL cao cho từ đó và cả các từ nằm cạnh nó"
Dùng câu ví dụ (giả sử "uneventfully" là từ hiếm):

> **"The trip was uneventfully smooth and we arrived on time."**

- **Mắt xích 1: từ hiếm có vector tệ.** Vector của "uneventfully" gần như số ngẫu nhiên, không mang ý nghĩa.
- **Mắt xích 2: mô hình đoán sai quanh từ đó** (cơ chế (a), (b) là diễn giải của người học):
  - **(a) Khi từ hiếm là từ cần đoán:** mô hình không hiểu từ này nên chỉ cho xác suất rất thấp → loss lớn.
  - **(b) Khi từ hiếm là input của các bước sau:** LSTM giữ "ký ức" tạo từ vector các từ đã đọc. Vector rác làm **nhiễu ký ức**, nên các từ ngay sau ("smooth", "and", "we"...) bị đoán kém.
- **Mắt xích 3: perplexity cao.** PPL là thước đo trung bình trên mọi từ của tập kiểm tra. Một từ hiếm kéo theo vài từ đoán tệ → loss lớn ở các từ đó → PPL cả mô hình tăng.

| Từ trong câu | Mô hình đoán | Loss |
|---|---|---|
| The, trip, was | Tốt | Nhỏ |
| **uneventfully** | Tệ | **Lớn** |
| **smooth, and, we** (ngay sau) | Bị ảnh hưởng | **Lớn hơn bình thường** |
| arrived, on, time | Dần hồi phục | Nhỏ |

**Ví dụ thực tế:** bạn nghe giảng và gặp một từ chuyên ngành lạ. Bạn không hiểu từ đó, và vì thế **mất mạch vài câu liền sau**, dù các câu sau dùng toàn từ quen.

Nếu văn bản có **nhiều từ hiếm** (ngôn ngữ giàu hình thái, mạng xã hội), tác động cộng dồn → PPL cao.

#### Vì sao đặc biệt tệ ở hai trường hợp?

**Trường hợp 1: ngôn ngữ giàu hình thái (morphologically rich).**
Một từ gốc biến đổi thành rất nhiều dạng. Ví dụ tiếng Đức, động từ "gehen" (đi):

| Dạng | Nghĩa |
|---|---|
| gehe | tôi đi |
| gehst | bạn đi |
| geht | anh ấy đi |
| gingen | họ đã đi |
| gegangen | đã đi (quá khứ phân từ) |

Từ vựng phình rất to và đa số dạng hiếm. Bài báo gọi là *long-tailed frequency distribution* (phân phối tần suất đuôi dài): vài từ rất phổ biến, còn lại hàng chục nghìn từ cực hiếm.

**Trường hợp 2: mạng xã hội (dynamic vocabulary, từ vựng luôn thay đổi).**
Bình luận như "đỉnh quáaaaa", "hayyyy lắmmmm", "xĩu thật sự": từ mới, từ kéo dài, từ sai chính tả xuất hiện mỗi ngày. Bảng tra cố định không thể có mọi biến thể, nên gặp từ mới thì không có dòng nào để tra. Từ như vậy gọi là **OOV (out-of-vocabulary, từ ngoài từ điển)**.

#### OOV (từ ngoài từ điển) và ký hiệu `<unk>`

**OOV = Out-Of-Vocabulary = "từ nằm ngoài từ điển".** Đó là những từ mà mô hình **chưa từng biết** vì chúng không có trong danh sách từ vựng V lúc huấn luyện.

**Ví dụ thực tế:**
- Bạn học từ vựng tiếng Anh từ một cuốn sách có 10.000 từ. Gặp từ "yeet" hay "doomscrolling" không có trong sách thì đó là từ OOV đối với bạn.
- Trên mạng xã hội: "đỉnh quáaaaa", "xĩu", tên quán mới mở, từ viết tắt mới xuất hiện hôm qua.

**NLM thông thường xử lý OOV thế nào?** Vì tra bảng theo từ, từ OOV **không có dòng nào trong bảng**. Người ta thường gộp mọi từ lạ vào **một ký hiệu chung `<unk>`** (unknown):

> "Hôm nay tôi mua một chiếc **doomscrolling-phone**" → "Hôm nay tôi mua một chiếc `<unk>`"

Hậu quả: mọi từ lạ, dù khác nhau hoàn toàn, đều bị coi là **một từ duy nhất**, mất hết thông tin. (Các bộ dữ liệu của bài báo cũng dùng `<unk>`, xem 1.4.)

**Phân biệt từ hiếm và từ OOV:**

| | Từ hiếm | Từ OOV |
|---|---|---|
| Có trong từ điển không? | **Có**, nhưng xuất hiện rất ít lần | **Không** |
| Vector ở NLM thông thường | Có nhưng **tệ** (ít được học) | **Không có** (bị gộp vào `<unk>`) |
| Ví dụ | "uneventfully" xuất hiện 1 lần | "looooook" chưa từng xuất hiện |

Cả hai đều thuộc vấn đề A: NLM thông thường không dùng được cấu trúc bên trong từ để xử lý chúng. Cách bài báo xử lý OOV xem ở 1.4.

#### Liên hệ với slide: hình thái học và tách từ

**Hình thái học (morphology)** nghiên cứu cách từ được xây dựng: gốc từ, tiền tố, hậu tố, từ ghép...

**Hình thái học có phải là tách từ không? Không hoàn toàn, tách từ chỉ là một phần.** Theo slide Bài 1, Morphology gồm:
- cách từ được xây dựng, tiền tố và hậu tố,
- xử lý từ ghép (compound word),
- nhận diện tên riêng,
- **nhận diện ranh giới từ (word boundary)** → chính là **tách từ**.

| | Tiếng Việt | Tiếng Đức, Nga, Czech... |
|---|---|---|
| Loại ngôn ngữ | **Đơn lập, không biến hình** (slide Bài 3) | **Biến hình** (inflectional) |
| Hình thái học chủ yếu là | Cách **tạo từ** (từ đơn, từ ghép, từ láy) và **tách từ** | Cách **biến đổi từ** (gốc + tiền tố + hậu tố: gehe, gehst, geht, gingen...) |
| Ví dụ | "học sinh" là một từ ghép 2 âm tiết | "geht", "gingen" là các dạng của "gehen" |

Ví dụ tách từ tiếng Việt ở slide: "Học sinh học sinh học" có thể tách "học sinh | học | sinh học" hoặc "học | sinh | học | sinh học".

**Điều cần nhớ khi báo cáo:**
- "Morphologically rich" trong bài báo nghĩa là **nhiều dạng biến đổi của một từ gốc**. **Tiếng Việt không thuộc nhóm này** và bài báo **không thử nghiệm tiếng Việt**.
- Ý "mô hình theo ký tự có thể hữu ích với tiếng Việt trên mạng xã hội" là suy luận bên ngoài, **không phải kết quả của bài báo**.

---

### Vấn đề B của NLM thông thường: quá nhiều tham số

Bài báo nói:
> *"Given that most of the parameters in NLMs are from the word embeddings, the proposed model has significantly fewer parameters than previous NLMs, making it attractive for applications where model size may be an issue (e.g. cell phones)."*
>
> **Dịch:** Vì phần lớn tham số trong các NLM nằm ở các word embedding, mô hình đề xuất có ít tham số hơn đáng kể so với các NLM trước đây, khiến nó hấp dẫn cho các ứng dụng mà kích thước mô hình có thể là vấn đề (ví dụ điện thoại di động).

Giải thích:
- **Tham số** (xem 1.2) là các con số mô hình phải lưu và học. Nhiều tham số thì tốn **bộ nhớ, dung lượng**, khó chạy trên thiết bị nhỏ như điện thoại.
- NLM thông thường có **một dòng vector cho mỗi từ** trong từ điển (bảng tra ở trên). Từ vựng càng lớn thì bảng càng to, giống cuốn từ điển **mỗi từ một dòng**: càng nhiều từ thì cuốn sách càng dày.
- Đây là vấn đề về **kích thước / hiệu quả**, **không phải** độ chính xác. Số liệu cụ thể xem ở 1.4.

---

### Bài báo nói gì / người học tự thêm gì (mục 1.3)

**Là của bài báo (Introduction):**
- n-gram ước lượng bằng đếm và làm mịn; n-gram hiếm bị ước lượng kém do thưa dữ liệu dù có làm mịn.
- NLM giải quyết thưa dữ liệu bằng vector từ; từ gần nghĩa thì gần nhau trong không gian vector.
- NLM "mù" với thông tin bên trong từ (ví dụ eventful / uneventful); embedding từ hiếm bị ước lượng kém → PPL cao cho từ hiếm **và các từ xung quanh**; đặc biệt tệ với ngôn ngữ giàu hình thái và mạng xã hội.
- Phần lớn tham số của NLM nằm ở word embedding.
- Cụm từ *conventional NLM* (NLM thông thường).

**Là của người học (diễn giải, không có trong bài báo):**
- Các ví dụ: trà/bàn, gehen, Nguyễn Thị Hồng Nhung, TikTok, danh bạ, số căn cước, giá nhà, học thuộc/hiểu bài...
- Cơ chế "dòng vector chỉ được chỉnh khi từ đó xuất hiện".
- Cơ chế (a)/(b): vector rác làm nhiễu ký ức LSTM nên các từ ngay sau cũng bị đoán kém (bài báo chỉ nêu kết quả "và các từ xung quanh").
- Cách mô tả "NLM thông thường = tra bảng theo từ" và cơ chế "tọa độ bản đồ" của NLM.
- Ví dụ add-one có số (add-one thuộc slide Bài 2; bài báo chỉ nói chung "smoothing" và dùng Kneser-Ney).

### Tóm tắt 1.3

| Vấn đề | Ví dụ đời thường | Cách chữa |
|---|---|---|
| **n-gram:** thưa dữ liệu; add-one chia đều, không biết cụm nào hợp lý | Học thuộc đề cũ; "uống trà" và "uống bàn" cùng 6,7% | Dùng **NLM** (vector từ) |
| **NLM thông thường, vấn đề A:** mù cấu trúc từ, từ hiếm vector tệ, từ lạ không tra được | Chỉ biết số căn cước; gặp bạn 1 lần thì không hiểu bạn | Đọc ký tự (1.4) |
| **NLM thông thường, vấn đề B:** bảng từ chiếm phần lớn tham số | Cuốn từ điển mỗi từ một dòng | Bỏ bảng từ ở đầu vào (1.4) |

---

## 1.4. Ý tưởng giải quyết của bài báo

### Ý chính
> **Đừng tra bảng theo từ nữa. Hãy cho mô hình đọc từng ký tự của từ, rồi tự ghép các ký tự thành một vector đại diện cho từ.**

Phần còn lại của mô hình (LSTM, đoán từ kế tiếp) giữ nguyên như NLM thông thường.

### Khái niệm cần biết trước: mô hình từ, mô hình ký tự, mô hình hình vị

Cả ba đều là **NLM đoán từ kế tiếp**. Chúng chỉ khác nhau ở **cách biến mỗi từ đầu vào thành vector**.

| Loại | Tên trong bài báo | Vector của từ lấy từ đâu | Cần công cụ tách hình vị? |
|---|---|---|---|
| **Mô hình từ** (word-level) | Word, LSTM-Word | **Tra bảng** theo từ. Đây chính là "NLM thông thường" ở 1.3 | Không |
| **Mô hình hình vị** (morpheme-level) | Morph | Vector của từ **cộng** vector các hình vị của từ (un + event + ful + ly) | **Có** (chạy công cụ Morfessor trước) |
| **Mô hình ký tự** (character-level) | Char, LSTM-Char | **Tính** từ các ký tự bằng CNN + Highway. Đây là **mô hình của bài báo** | **Không** |

Ba loại này là ba hàng **Word / Morph / Char** trong Bảng 4 và 5 của bài báo. **Đầu ra của cả ba đều là xác suất cho từ kế tiếp**, và phần LSTM, softmax là giống nhau.

**Ví dụ thực tế: hai cách đọc sách.**
- **Đọc theo từ (mô hình từ):** em bé nhận mặt chữ **nguyên khối**, thấy hình chữ "mẹ" thì nhớ ngay. Gặp từ lạ chưa học thì không đọc được.
- **Đọc theo ký tự (mô hình ký tự):** em bé **đánh vần** từng chữ cái rồi ghép lại. Gặp từ lạ vẫn đánh vần được.

#### Lưu ý: "mô hình ký tự" trong bài báo là loại đặc biệt
Có **hai** kiểu "ký tự":

| Kiểu | Đầu vào | **Đầu ra** | Ghi chú |
|---|---|---|---|
| **Thuần ký tự** (nghiên cứu cũ: Sutskever 2011, Graves 2013) | Ký tự | **Ký tự** (đoán chữ cái tiếp theo) | Có thể sinh từ mới, nhưng thường kém mô hình theo từ |
| **Bài báo này** | Ký tự | **Từ** (đoán từ tiếp theo) | Mô hình của bài báo |

> *"Character-level models obviate the need for morphological tagging or manual feature engineering, and have the attractive property of being able to generate novel words. However they are generally outperformed by word-level models (Mikolov et al. 2012)."*
>
> **Dịch:** Các mô hình mức ký tự loại bỏ nhu cầu gán nhãn hình thái hay thiết kế đặc trưng thủ công, và có ưu điểm hấp dẫn là có thể sinh ra từ mới. Tuy nhiên, nhìn chung chúng bị các mô hình mức từ vượt qua (Mikolov và cộng sự 2012).

Vì vậy "character-level" trong bài báo nghĩa là **đầu vào ở mức ký tự**, còn **dự đoán vẫn ở mức từ** (xem câu trong Abstract ở 1.2). Đừng hiểu là mô hình sinh từng chữ cái.

#### Mô hình hình vị được xây thế nào? (mô hình đối chứng của bài báo)

**Hình vị (morpheme)** là đơn vị nhỏ nhất có nghĩa trong một từ.

| Từ | Cắt thành hình vị | Nghĩa từng mảnh |
|---|---|---|
| uneventfully | **un** + **event** + **ful** + **ly** | không + sự kiện + đầy + một cách |
| unhappy | **un** + **happy** | không + hạnh phúc |
| books | **book** + **s** | quyển sách + số nhiều |

Ví dụ thực tế: giống **ghép Lego**; mỗi miếng nhỏ có ý nghĩa riêng, ghép lại thành một từ. (Ghi chú tiếng Việt: đơn vị tương tự thường được coi là "tiếng", nên "học sinh" gồm hai hình vị "học" và "sinh". Nhưng tiếng Việt không biến hình nên khái niệm này ít quan trọng hơn so với tiếng Czech.)

**Cách xây (công thức (11) của bài báo):** vector đầu vào của từ k là

> x_k + Σ m_j (cộng trên các hình vị j của từ k)

trong đó x_k là **vector của chính từ k** (như mô hình từ) và m_j là vector của từng hình vị. Ví dụ minh họa: vector("uneventfully") = vector từ "uneventfully" + vector("un") + vector("event") + vector("ful") + vector("ly").

> *"The morphemes are obtained by running an unsupervised morphological tagger as a preprocessing step. We emphasize that the word embedding itself (i.e. x_k) is added on top of the morpheme embeddings, as was done in Botha and Blunsom (2014). The morpheme embeddings are of size 200/650 for the small/large models respectively."*
>
> **Dịch:** Các hình vị được thu được bằng cách chạy một công cụ gán nhãn hình thái không giám sát như một bước tiền xử lý. Chúng tôi nhấn mạnh rằng bản thân word embedding (tức x_k) được cộng thêm lên trên các morpheme embedding, như đã làm trong Botha và Blunsom (2014). Kích thước các morpheme embedding là 200/650 lần lượt cho mô hình nhỏ/lớn.

- Công cụ tách hình vị là **Morfessor Cat-MAP** (Creutz và Lagus 2007), chạy **tự động** nên có thể cắt chưa chuẩn như con người. Cách cắt "un + event + ful + ly" ở trên chỉ là minh họa.
- Vì vector của chính từ vẫn được cộng vào, mô hình hình vị vẫn **cần bảng word embedding**:
  > *"Note that the morpheme models have strictly more parameters than the word models because word embeddings are used as part of the input."*
  >
  > **Dịch:** Lưu ý rằng các mô hình hình vị có nhiều tham số hơn hẳn các mô hình từ vì word embedding vẫn được dùng như một phần của đầu vào.

**Vì sao bài báo tự huấn luyện mô hình này?** Mô hình hình vị trước đó (MLBL của Botha 2014) dùng kiến trúc log-bilinear, không phải LSTM. Nếu chỉ so với nó, rất khó biết mô hình ký tự tốt hơn nhờ **cách dùng thông tin dưới mức từ** hay chỉ nhờ **LSTM mạnh hơn**:
> *"As comparison against the MLBL models is confounded by our use of LSTMs--widely known to outperform their feed-forward/log-bilinear cousins--we also train an LSTM version of the morphological NLM, where the input representation of a word given to the LSTM is a summation of the word's morpheme embeddings."*
>
> **Dịch:** Vì việc so sánh với các mô hình MLBL bị nhiễu bởi việc chúng tôi dùng LSTM (vốn được biết là vượt trội so với các mô hình họ hàng feed-forward/log-bilinear), chúng tôi cũng huấn luyện một phiên bản LSTM của NLM hình thái, trong đó biểu diễn đầu vào của một từ đưa vào LSTM là tổng các embedding hình vị của từ.

Ví dụ thực tế: muốn biết **loại nhiên liệu** nào tốt hơn thì phải đổ vào **cùng một loại xe**; nếu hai xe khác động cơ thì không biết khác biệt do nhiên liệu hay do động cơ. Mô hình hình vị dùng LSTM chính là "xe cùng động cơ".

**Đọc kết quả (Bảng 4, tiếng Czech, bộ nhỏ, cỡ nhỏ; số là PPL, thấp là tốt):**

| Mô hình | PPL | Nhận xét |
|---|---|---|
| Từ (Word) | 503 | Tệ nhất (không dùng thông tin dưới mức từ) |
| Hình vị (Morph) | 414 | Tốt hơn mô hình từ 89 điểm |
| Ký tự (Char) | **401** | Tốt nhất; hơn mô hình hình vị 13 điểm mà **không cần** công cụ tách hình vị |

> *"The character models also outperform their morphological counterparts (both MLBL and LSTM architectures), although improvements over the morphological LSTMs are more measured."*
>
> **Dịch:** Các mô hình ký tự cũng vượt các mô hình hình thái tương ứng (cả kiến trúc MLBL lẫn LSTM), dù mức cải thiện so với các LSTM hình thái là khiêm tốn hơn.

### So sánh luồng xử lý: NLM thông thường và mô hình bài báo

```
NLM thông thường (mô hình từ)
 "absurdity" ──► số 4.217 ──► [tra bảng 10.000 dòng] ───────────────► vector ──► LSTM ──► dự đoán

Mô hình bài báo (mô hình ký tự)
 "absurdity" ──► a b s u r d i t y ──► [CNN + Highway] ──► vector ──► LSTM ──► dự đoán
                                         (đọc ký tự)
```

Chỉ phần tạo vector của từ được thay: **bỏ bảng tra theo từ, thay bằng khối đọc ký tự**.

**Ví dụ thực tế:** cách thông thường giống nhận biết một người **chỉ qua số căn cước**; cách của bài báo giống nhận biết người **qua họ tên đầy đủ**. Thấy "Nguyễn Văn An" và "Nguyễn Văn Bình" bạn biết ngay có thể cùng họ. Tương tự, "eventful" và "uneventful" có chung ký tự "event", nên mô hình có cơ sở nhận ra chúng liên quan.

**Ví dụ thực tế khác: nhận biết món ăn qua tên.** Gặp món chưa từng nghe tên, "bánh bột lọc trần", bạn vẫn đoán được nó là một loại bánh nhờ **các mảnh trong tên**. Mô hình bài báo làm tương tự với từ.

### Sơ đồ tổng thể: 3 khối nối tiếp (chi tiết học ở Bước 2–4)

```
Từ "absurdity"
   │
   ▼
┌───────────────────────────────┐
│ KHỐI 1: CNN trên ký tự        │  ← đọc các ký tự, tìm các "mảnh" quan trọng
│ (CharCNN)                     │    → ra 1 vector sơ bộ cho từ
└───────────────────────────────┘
   │
   ▼
┌───────────────────────────────┐
│ KHỐI 2: Highway network       │  ← tinh chỉnh vector sơ bộ cho tốt hơn
└───────────────────────────────┘
   │  (vector đại diện cho từ)
   ▼
┌───────────────────────────────┐
│ KHỐI 3: LSTM                  │  ← nhớ các từ đã đọc trước, hiểu ngữ cảnh
└───────────────────────────────┘
   │
   ▼
 Softmax → bảng xác suất trên từ vựng → "is" cao nhất
```

- **Khối 1 (CNN):** CNN (mạng nơ-ron tích chập) là công cụ quét qua chuỗi để tìm các mẫu. Ví dụ thực tế: **một nhóm máy quét mã vạch**, mỗi máy tìm một mẫu ký tự riêng ("un", "event", "ful", "ly"...) rồi báo điểm "mẫu của tôi có xuất hiện không, mạnh cỡ nào?". Gộp điểm các máy lại thành một vector. Mỗi "máy quét" gọi là một **filter**.
- **Khối 2 (Highway):** một mạng nhỏ tinh chỉnh vector, có "cổng" quyết định giữ nguyên bao nhiêu phần, biến đổi bao nhiêu phần. Ví dụ thực tế: **biên tập viên** đọc bản nháp, chỗ nào ổn giữ nguyên, chỗ nào cần sửa thì sửa.
- **Khối 3 (LSTM):** khối quen thuộc của NLM, đọc từng từ theo thứ tự và giữ "ký ức" về các từ đã đọc.

### Cốt lõi của giải pháp: **chia sẻ tham số giữa các từ**

Bài báo không gọi tên ý này, nhưng đây là lý do mô hình khắc phục được vấn đề A (cách gọi là của người học).

- **NLM thông thường:** mỗi từ có tham số riêng (một dòng trong bảng). Dòng của "uneventfully" **chỉ được học khi chính từ đó xuất hiện**.
- **Mô hình bài báo:** vector của từ được **tính** từ ký tự bằng CNN. Các filter và bảng ký tự **dùng chung cho mọi từ**, nên mỗi lần bất kỳ từ nào chứa mẫu đó xuất hiện, chúng đều được học thêm.

**Ví dụ thực tế: học đọc.** Cách 1 (như NLM thông thường): học thuộc từng từ nguyên khối ("careful", "helpful"...), gặp "uneventfully" lần đầu thì chịu. Cách 2 (như bài báo): học theo vần, theo mảnh; học "-ful", "-ly", "un-" một lần rồi dùng cho hàng nghìn từ.

**Ví dụ có số (số liệu minh họa của người học):**

| Từ | Số lần xuất hiện |
|---|---|
| eventful | 50 |
| uneventful | 5 |
| eventfully | 2 |
| **uneventfully** | **1** |
| careful, helpful, beautiful... (đuôi "ful") | ~ 5.000 cộng lại |
| quickly, slowly, really... (đuôi "ly") | ~ 20.000 cộng lại |

| | Số lần phần liên quan đến "uneventfully" được học |
|---|---|
| NLM thông thường (dòng riêng) | **1 lần** → vector gần như số ngẫu nhiên |
| Mô hình bài báo (filter "ful", "ly", "un", "event" dùng chung) | **Hàng chục nghìn lần**, vì các filter học từ mọi từ chứa mẫu đó |

Từ hiếm nhưng **các mảnh của nó không hiếm**.

### Khắc phục vấn đề A (từ hiếm, từ lạ) → đọc ký tự, chia sẻ tham số

| Nội dung | NLM thông thường | Mô hình bài báo |
|---|---|---|
| Vector của từ lấy từ đâu | Dòng riêng trong bảng | **Tính** từ ký tự bằng CNN + Highway |
| Từ hiếm | Vector tệ | Vector tốt hơn (mảnh ký tự học từ nhiều từ khác) |
| Từ chưa từng thấy (OOV) | Không có dòng, không tra được | **Vẫn tính được** từ ký tự |
| Từ cùng gốc (eventful / uneventful) | Hai dòng không liên quan | Chung ký tự "event" nên vector **liên hệ nhau** |
| Cần công cụ phân tích hình vị trước? | (các hướng morpheme thì cần) | **Không cần** |

Bài báo nêu hai điểm khác biệt với các hướng trước:
> *"Unlike previous works that utilize subword information via morphemes (Botha and Blunsom 2014; Luong, Socher, and Manning 2013), our model does not require morphological tagging as a pre-processing step. And, unlike the recent line of work which combines input word embeddings with features from a character-level model (dos Santos and Zadrozny 2014; dos Santos and Guimaraes 2015), our model does not utilize word embeddings at all in the input layer."*
>
> **Dịch:** Khác với các nghiên cứu trước dùng thông tin dưới mức từ thông qua hình vị (Botha và Blunsom 2014; Luong, Socher và Manning 2013), mô hình của chúng tôi không cần gán nhãn hình thái như một bước tiền xử lý. Và khác với hướng nghiên cứu gần đây kết hợp word embedding ở đầu vào với đặc trưng từ một mô hình mức ký tự (dos Santos và Zadrozny 2014; dos Santos và Guimaraes 2015), mô hình của chúng tôi hoàn toàn không dùng word embedding ở lớp đầu vào.

**Bằng chứng trong bài báo:**
- **Bảng 4, 5:** mô hình ký tự có PPL thấp hơn mô hình từ và mô hình hình vị ở các ngôn ngữ giàu hình thái. Ví dụ tiếng Czech, bộ nhỏ, cỡ nhỏ: từ 503, hình vị 414, **ký tự 401**.
- **Bảng 6:** từ ngoài từ điển (*computer-aided*, *misinformed*, *looooook*) được đặt gần các từ cùng loại (*computer-guided*, *informed*, *look*). Mô hình từ không có vector cho chúng.
- **Bảng 8:** tiếng Đức, mô hình ký tự tốt hơn mô hình từ ở **mọi** cỡ dữ liệu và từ vựng đã thử (PPL giảm 8% đến 21%).

#### Riêng với từ OOV: bài báo xử lý thế nào?
Vì vector của từ được **tính từ ký tự**, từ OOV vẫn có vector (cứ đưa các ký tự của nó qua CNN và Highway), không cần "dòng" nào trong bảng. Mô hình từ thì không có vector cho chúng.

Bài báo nhận xét về Bảng 6:
> *"The learned representations of OOV words (computer-aided, misinformed) are positioned near words with the same part-of-speech. The model is also able to correct for incorrect/non-standard spelling (looooook), indicating potential applications for text normalization in noisy domains."*
>
> **Dịch:** Các biểu diễn học được của từ OOV (computer-aided, misinformed) nằm gần các từ có cùng từ loại. Mô hình cũng có thể bù cho cách viết sai/không chuẩn (looooook), cho thấy tiềm năng ứng dụng vào chuẩn hóa văn bản trong các lĩnh vực nhiều nhiễu.

Các từ gần nhất (Bảng 6, mô hình ký tự):

| Từ OOV | Gần nhất **trước** Highway | Gần nhất **sau** Highway |
|---|---|---|
| computer-aided | computer-guided, computerized, disk-drive, computer | computer-guided, computer-driven, computerized, computer |
| misinformed | informed, performed, transformed, inform | informed, performed, outperformed, transformed |
| looooook | look, cook, looks, shook | look, looks, looked, looking |

Nhận xét: *looooook* kéo dài chữ "o" nhưng vẫn được đặt gần *look*, *looks*. Trước Highway còn lẫn *cook*, *shook* (giống chữ nhưng khác nghĩa); sau Highway cụm gần nhất là các dạng của động từ *look*.

**Bảng 6 là bằng chứng định tính (minh họa), không phải số liệu đo PPL.** Xem lưu ý 1 ngay bên dưới.

**Hai lưu ý trung thực:**
1. Ở các thí nghiệm chính, một số từ đã bị thay bằng `<unk>` trong dữ liệu tiền xử lý của các nghiên cứu trước, và bài báo **cố ý không** cho mô hình ký tự nhìn mặt chữ của chúng:
   > *"In these datasets only singleton words were replaced with* `<unk>` *and hence we effectively use the full vocabulary. It is worth noting that the character model can utilize surface forms of OOV tokens (which were replaced with* `<unk>`*), but we do not do this and stick to the preprocessed versions (despite disadvantaging the character models) for exact comparison against prior work."*
   >
   > **Dịch:** Trong các bộ dữ liệu này chỉ những từ singleton (xuất hiện đúng một lần) bị thay bằng `<unk>`, nên thực chất chúng tôi dùng toàn bộ từ vựng. Cần lưu ý rằng mô hình ký tự có thể tận dụng mặt chữ của các token OOV (vốn đã bị thay bằng `<unk>`), nhưng chúng tôi không làm vậy mà giữ nguyên các phiên bản đã tiền xử lý (dù điều này gây bất lợi cho các mô hình ký tự) để so sánh chính xác với các nghiên cứu trước.

   Vì vậy số liệu định lượng chưa phát huy hết lợi thế OOV; phần OOV chủ yếu được minh họa **định tính** ở Bảng 6.
2. Các filter **không phải lúc nào cũng khớp đúng hình vị**:
   > *"...upon reviewing the character n-grams picked up by the filters (i.e. those that maximized the value of the filter), we found that they did not (in general) correspond to valid morphemes."*
   >
   > **Dịch:** ...khi xem xét các n-gram ký tự mà filter chọn ra (tức là những n-gram làm cực đại giá trị của filter), chúng tôi thấy chúng (nhìn chung) không tương ứng với các hình vị hợp lệ.

   Vậy ví dụ "máy quét 'event'/'ful'" chỉ là trực giác. Tuy vậy Hình 2 (PCA) cho thấy mô hình vẫn học được phân biệt tiền tố, hậu tố.

#### Giải thích lưu ý 1: vì sao số liệu chưa "phát huy hết" lợi thế OOV?

**Bối cảnh:** các bộ dữ liệu bài báo dùng (Penn Treebank, bộ của Botha...) do các nhóm khác **tiền xử lý từ trước**: những từ chỉ xuất hiện **đúng một lần** trong dữ liệu (*singleton*) đã bị thay bằng `<unk>`. Ví dụ, câu gốc "The film was **uneventfully-paced** and slow" (giả sử "uneventfully-paced" chỉ xuất hiện 1 lần trong cả kho dữ liệu) trong file dữ liệu đã thành "The film was `<unk>` and slow". Vì chỉ thay từ xuất hiện đúng 1 lần nên từ vựng gần như đầy đủ (*"we effectively use the full vocabulary"*).

**Mô hình ký tự có thể làm tốt hơn nhưng bài báo không cho nó làm.** Về nguyên tắc, mô hình ký tự đọc mặt chữ nên có thể xử lý "uneventfully-paced". Nhưng dữ liệu **đã mất** mặt chữ này. Bài báo chọn cho mô hình ký tự nhìn đúng cái `<unk>` như mô hình từ:
> *"As with previous experiments the character model does not utilize surface forms of* `<unk>` *and simply treats it as another token."*
>
> **Dịch:** Như các thí nghiệm trước, mô hình ký tự không tận dụng mặt chữ của `<unk>` mà chỉ coi nó như một token bình thường.

**Vì sao làm vậy? Để so sánh công bằng.** Kết quả của Botha và các tác giả trước được chạy trên đúng bộ dữ liệu đã tiền xử lý này. Ví dụ thực tế: hai thí sinh thi cùng đề; thí sinh A có thêm bản gốc đầy đủ của tài liệu, thí sinh B chỉ có bản đã bị che bớt. Nếu A dùng hết tài liệu thì A hơn là đương nhiên. Muốn biết **cách học** của ai tốt hơn, ban tổ chức bắt A **cũng chỉ dùng bản đã che bớt**. Bài báo chấp nhận bất lợi (*"despite disadvantaging the character models"*) để kết quả đáng tin.

| Nội dung | Nói như thế nào khi báo cáo |
|---|---|
| Kết quả PPL (Bảng 3–5) | Mô hình ký tự vẫn **tốt hơn**, dù "bị trói tay" |
| Lợi thế OOV | Chưa được **đo bằng số liệu**; chỉ **minh họa** ở Bảng 6 |
| Nên tránh nói | "Bài báo chứng minh bằng số liệu rằng mô hình ký tự xử lý OOV tốt hơn X%" |

#### Giải thích lưu ý 2: filter không khớp hình vị nhưng mô hình vẫn học được cấu trúc

**Điều tác giả kỳ vọng:**
> *"Our initial expectation was that each filter would learn to activate on different morphemes and then build up semantic representations of words from the identified morphemes."*
>
> **Dịch:** Kỳ vọng ban đầu của chúng tôi là mỗi filter sẽ học cách kích hoạt trên các hình vị khác nhau, rồi dựng nên biểu diễn ngữ nghĩa của từ từ các hình vị đã nhận diện.

Nghĩa là mong mỗi filter = một "máy quét" một hình vị ("un", "event", "ful", "ly"...).

**Điều thực tế thấy:** họ lấy từng filter, xem những chuỗi ký tự nào làm giá trị của filter lớn nhất (câu trích ở lưu ý 2 phía trên): chúng **nhìn chung không tương ứng với hình vị hợp lệ**. Bài báo **không liệt kê ví dụ cụ thể** ở đoạn này nên không nên bịa ví dụ filter.

**Ví dụ minh họa (chỉ là ẩn dụ, không phải số liệu bài báo):** bạn thuê một đội trinh sát tìm hồ sơ quan trọng. Bạn mong mỗi người tìm đúng một loại giấy tờ rõ ràng, nhưng thực tế mỗi người chú ý những dấu hiệu lạ khó gọi tên. Tuy vậy **báo cáo gộp của cả đội** vẫn cho bức tranh đúng. Từng filter không "sạch", nhưng **tổng hợp hàng trăm filter** vẫn mã hóa được thông tin có ích.

**Bằng chứng mô hình vẫn học được cấu trúc (Hình 2, PCA).** PCA (principal components analysis) là kỹ thuật thu gọn vector nhiều chiều xuống 2 chiều để vẽ lên biểu đồ.
> *"To get a better intuition for what the character composition model is learning, we plot the learned representations of all character n-grams (that occurred as part of at least two words in V) via principal components analysis (Figure 2). We feed each character n-gram into the CharCNN and use the CharCNN's output as the fixed dimensional representation for the corresponding character n-gram."*
>
> **Dịch:** Để hiểu rõ hơn mô hình ghép ký tự đang học điều gì, chúng tôi vẽ các biểu diễn học được của mọi n-gram ký tự (xuất hiện trong ít nhất hai từ của V) bằng phân tích thành phần chính (Hình 2). Chúng tôi đưa từng n-gram ký tự vào CharCNN và dùng đầu ra của CharCNN làm biểu diễn có số chiều cố định cho n-gram ký tự đó.

> *"As is apparent from Figure 2, the model learns to differentiate between prefixes (red), suffixes (blue), and others (grey). We also find that the representations are particularly sensitive to character n-grams containing hyphens (orange), presumably because this is a strong signal of a word's part-of-speech."*
>
> **Dịch:** Như thấy rõ ở Hình 2, mô hình học cách phân biệt giữa tiền tố (đỏ), hậu tố (xanh dương) và các loại khác (xám). Chúng tôi cũng thấy các biểu diễn đặc biệt nhạy với các n-gram ký tự chứa dấu gạch nối (cam), có lẽ vì đó là tín hiệu mạnh về từ loại của từ.

Định nghĩa trong chú thích Hình 2:
> *"Prefixes refer to character n-grams which start with the start-of-word character. Suffixes likewise refer to character n-grams which end with the end-of-word character."*
>
> **Dịch:** Tiền tố là các n-gram ký tự bắt đầu bằng ký tự bắt đầu từ. Hậu tố tương tự là các n-gram ký tự kết thúc bằng ký tự kết thúc từ.

(Hai ký tự đặc biệt này là cái bài báo thêm vào mỗi từ, xem chú thích 4 và mục "Chạy thử" bên dưới.)

| Khi báo cáo | Nội dung |
|---|---|
| **Nên nói** | "CharCNN học được biểu diễn mang thông tin về tiền tố, hậu tố và dấu gạch nối" |
| **Không nên nói** | "Mỗi filter học đúng một hình vị" hoặc "mô hình tự học ra hình vị" |

### Khắc phục vấn đề B (quá nhiều tham số) → bỏ bảng từ ở đầu vào

#### Tham số nằm ở đâu trong mô hình?

| Phần | Tham số là gì | Ví dụ (kích thước thật, Bảng 1 và 2) |
|---|---|---|
| **Bảng word embedding** (mô hình từ) | Vector của mỗi từ | 10.000 từ × 200 số = **2 triệu** |
| **Bảng ký tự** (mô hình ký tự) | Vector của mỗi ký tự | 51 ký tự × 15 số = **765** |
| **Filter của CNN** | Các số trong mỗi "máy quét" | ≈ 77.000 (mô hình lớn) |
| **Highway, LSTM** | Các ma trận trọng số bên trong | Hàng triệu |
| **Lớp đầu ra (softmax)** | Vector cho mỗi từ trong từ điển | Hàng triệu |

Bảng ký tự cực nhỏ vì chỉ có vài chục đến vài trăm ký tự, trong khi từ thì có hàng chục nghìn.

**Phép tính minh họa (của người học, dựa trên Bảng 1 và 2; tiếng Đức bộ lớn: 206.000 từ, 195 ký tự, vector 650 chiều, bỏ qua bias):**

| | Cách tính | Tham số ở đầu vào |
|---|---|---|
| Bảng từ (NLM thông thường) | 206.000 × 650 | ≈ **134 triệu** |
| Mô hình bài báo | bảng ký tự 195 × 15 ≈ 3.000; filter CNN ≈ 77.000; Highway 2 lớp ≈ 4,8 triệu | ≈ **5 triệu** |

Từ vựng càng lớn thì bảng từ càng phình, trong khi số ký tự gần như cố định. Chú thích 12 của bài báo:
> *"The difference in parameters is greater for non-PTB corpora as the size of the word model scales faster with |V|."*
>
> **Dịch:** Sự khác biệt về số tham số lớn hơn ở các bộ dữ liệu ngoài PTB, vì kích thước của mô hình từ tăng nhanh hơn theo |V| (kích thước từ vựng).

**Ví dụ thực tế:** thay vì mang theo một **cuốn từ điển 10.000 trang**, bạn chỉ mang **một bảng chữ cái** và kỹ năng ghép chữ.

#### Số liệu thực tế bài báo báo cáo (toàn mô hình, gồm cả đầu ra)

| Trường hợp | Mô hình từ | Mô hình ký tự |
|---|---|---|
| Tiếng Ả Rập, cỡ nhỏ | 35 triệu | 29 triệu |
| Tiếng Ả Rập, cỡ lớn | 121 triệu | **69 triệu** |
| PTB, cỡ lớn, so với LSTM-2 (Zaremba) | 52 triệu (PPL 78,4) | **19 triệu** (PPL 78,9), ít hơn ≈ 60% |
| PTB, so với mô hình từ cùng cỡ | 20 triệu (PPL 85,4) | 19 triệu (PPL **78,9**) |

**Lưu ý:** mức tiết kiệm thực tế thấp hơn phép tính minh họa, vì **đầu ra vẫn dùng bảng theo từ vựng**:
> *"In our work, predictions are at the word-level, and hence we still utilize word embeddings in the output layer."*
>
> **Dịch:** Trong công trình của chúng tôi, dự đoán được thực hiện ở mức từ, và do đó chúng tôi vẫn dùng word embedding ở lớp đầu ra.

Bài báo chỉ bỏ bảng từ ở **đầu vào**. Khi báo cáo nói "**ít tham số hơn**", đừng nói "giảm 90%". Con số "ít hơn khoảng 60%" là so với mô hình tốt nhất lúc đó (LSTM-2); so với mô hình từ cùng cỡ trên PTB thì tham số gần như bằng nhau nhưng PPL tốt hơn. Điểm hay: bài báo **vừa giảm tham số (khi từ vựng lớn) vừa giảm PPL**.

### Cải tiến Highway (không phải vấn đề của NLM thông thường)

Highway là một **cải tiến bên trong mô hình của bài báo**, không phải cách chữa vấn đề A hay B. Lý do: sau khi thay bảng tra bằng CNN, mô hình đã chạy khá tốt:
> *"We could simply replace x_k (the word embedding) with y_k at each t in the RNN-LM, and as we show later, this simple model performs well on its own (Table 7)."*
>
> **Dịch:** Ta có thể đơn giản thay x_k (word embedding) bằng y_k tại mỗi bước t trong RNN-LM, và như sẽ chỉ ra sau đây, mô hình đơn giản này tự nó đã hoạt động tốt (Bảng 7).

Nhưng khi chỉ có CNN, các từ gần nhau thường vì **chính tả giống**. Thêm Highway thì vector mang cả **ngữ nghĩa**:
> *"The highway layers however, seem to enable encoding of semantic features that are not discernable from orthography alone."*
>
> **Dịch:** Tuy nhiên, các lớp highway dường như cho phép mã hóa các đặc trưng ngữ nghĩa mà chỉ riêng chính tả thì không nhận ra được.

Bảng 6, từ **"you"**:

| | Các từ gần "you" nhất |
|---|---|
| Sau CNN, **trước** Highway | your, young, four, youth (giống chữ) |
| **Sau** Highway | **we**, your, doug, i (đại từ, gần nghĩa hơn) |

Bảng 7 (PPL trên PTB, thấp là tốt). Đây là một **thí nghiệm loại bỏ (ablation study)**: bỏ từng thành phần để xem nó đóng góp bao nhiêu.

| Cấu hình | Nhỏ | Lớn |
|---|---|---|
| Không có Highway | 100,3 | 84,6 |
| 1 lớp Highway | 92,3 | 79,7 |
| 2 lớp Highway | **90,1** | **78,9** |
| 1 lớp MLP (thay Highway) | 111,2 | 92,6 |

Bỏ Highway thì PPL tệ hơn rõ; thay bằng MLP thông thường còn tệ hơn.

Ví dụ thực tế: **CNN** như người đọc chính tả (nhìn mặt chữ), **Highway** như người biên tập sửa cho hợp nghĩa (giữ phần đã đúng, sửa phần cần sửa). Cách hoạt động ở mục ngay bên dưới; công thức đầy đủ và vai trò trong cả mô hình học ở Bước 4.

#### Highway hoạt động thế nào? (trực giác)

**Ý chính:** Highway là một mạng nhỏ tinh chỉnh vector, và có "cổng" quyết định, **cho từng số trong vector**, nên **giữ nguyên** hay **biến đổi**.

**Vì sao tên là "highway" (đường cao tốc)?** Hình dung vector đi qua một đoạn đường: một số thông tin **đi thẳng trên đường cao tốc** (giữ nguyên), một số **rẽ vào làn phụ để xử lý** (biến đổi). Mạng tự quyết định thông tin nào đi làn nào.

**So với mạng thông thường (MLP).**
> *"Whereas one layer of an MLP applies an affine transformation followed by a nonlinearity to obtain a new set of features, z = g(Wy + b) (7), one layer of a highway network does the following: z = t ⊙ g(W_H y + b_H) + (1 − t) ⊙ y (8)"*
>
> **Dịch:** Trong khi một lớp MLP áp dụng một phép biến đổi affine rồi một hàm phi tuyến để thu được một tập đặc trưng mới, z = g(Wy + b) (7), thì một lớp highway network làm như sau: z = t ⊙ g(W_H y + b_H) + (1 − t) ⊙ y (8)

| Ký hiệu | Nghĩa |
|---|---|
| y | Vector đầu vào (kết quả từ CNN) |
| g(W_H y + b_H) | Phiên bản **đã biến đổi** của y |
| t | **Cổng biến đổi (transform gate)**, mỗi số nằm trong khoảng 0 đến 1 |
| 1 − t | **Cổng giữ nguyên (carry gate)** |
| ⊙ | Nhân từng số với nhau (cùng vị trí) |

> *"...where g is a nonlinearity, t = σ(W_T y + b_T) is called the transform gate, and (1 − t) is called the carry gate."*
>
> **Dịch:** ...trong đó g là một hàm phi tuyến, t = σ(W_T y + b_T) được gọi là cổng biến đổi (transform gate), và (1 − t) được gọi là cổng giữ nguyên (carry gate).

(σ là hàm sigmoid: biến bất kỳ số nào thành một số trong khoảng 0 đến 1, nên t luôn là một "tỷ lệ phần trăm".)

Ý nghĩa: z = (phần biến đổi × t) + (phần gốc × (1 − t)). Nếu t gần 1 thì lấy **bản mới**; nếu t gần 0 thì **giữ bản gốc**. MLP thì luôn biến đổi **toàn bộ**, không có lựa chọn giữ nguyên.

**Ví dụ số:** giả sử y = (4, 8), phiên bản đã biến đổi g(...) = (1, 2) và cổng t = (0,8 ; 0,1):

| Vị trí | Công thức | Kết quả | Hành vi |
|---|---|---|---|
| Số thứ nhất | 0,8 × 1 + 0,2 × 4 | **1,6** | Phần lớn lấy bản **mới** (80%) |
| Số thứ hai | 0,1 × 2 + 0,9 × 8 | **7,4** | Phần lớn **giữ bản gốc** (90%) |

Hai số trong cùng một vector được xử lý **khác nhau**, và mạng **tự học** cổng t. Đây cũng là chỗ tương tự "ô nhớ" của LSTM:
> *"Similar to the memory cells in LSTM networks, highway layers allow for training of deep networks by adaptively carrying some dimensions of the input directly to the output."*
>
> **Dịch:** Tương tự các ô nhớ trong mạng LSTM, các lớp highway cho phép huấn luyện các mạng sâu bằng cách mang một số chiều của đầu vào đi thẳng tới đầu ra một cách thích ứng.

**Khởi tạo nghiêng về "giữ nguyên":**
> *"Srivastava et al. (2015) recommend initializing b_T to a negative value, in order to militate the initial behavior towards carry. We initialized b_T to a small interval around −2."*
>
> **Dịch:** Srivastava và cộng sự (2015) khuyến nghị khởi tạo b_T bằng một giá trị âm để nghiêng hành vi ban đầu về phía giữ nguyên (carry). Chúng tôi khởi tạo b_T trong một khoảng nhỏ quanh −2.

(Với b_T = −2 thì t = σ(−2) ≈ 0,12, tức lúc đầu mạng giữ khoảng 88% bản gốc và chỉ biến đổi nhẹ.)

**Vì sao không dùng MLP?** Bài báo thử rồi và thấy tệ hơn:
> *"One could also have a multilayer perceptron (MLP) over y_k to model interactions between the character n-grams picked up by the filters, but we found that this resulted in worse performance. Instead we obtained improvements by running y_k through a highway network, recently proposed by Srivastava et al. (2015)."*
>
> **Dịch:** Người ta cũng có thể đặt một perceptron nhiều lớp (MLP) lên y_k để mô hình hóa tương tác giữa các n-gram ký tự mà các filter bắt được, nhưng chúng tôi thấy điều này cho hiệu năng tệ hơn. Thay vào đó, chúng tôi thu được cải thiện bằng cách cho y_k đi qua một highway network, do Srivastava và cộng sự (2015) mới đề xuất gần đây.

**Giả thuyết và quan sát của bài báo:**
> *"We hypothesize that highway networks are especially well-suited to work with CNNs, adaptively combining local features detected by the individual filters."*
>
> **Dịch:** Chúng tôi đưa ra giả thuyết rằng highway network đặc biệt phù hợp để làm việc với CNN, kết hợp một cách thích ứng các đặc trưng cục bộ do từng filter phát hiện.

> *"We also anecdotally note that (1) having one to two highway layers was important, but more highway layers generally resulted in similar performance (though this may depend on the size of the datasets), (2) having more convolutional layers before max-pooling did not help, and (3) highway layers did not improve models that only used word embeddings as inputs."*
>
> **Dịch:** Chúng tôi cũng ghi nhận qua quan sát rằng (1) có một đến hai lớp highway là quan trọng, nhưng nhiều lớp highway hơn nhìn chung cho hiệu năng tương tự (dù điều này có thể phụ thuộc kích thước bộ dữ liệu), (2) có thêm các lớp tích chập trước max-pooling không giúp ích, và (3) các lớp highway không cải thiện được các mô hình chỉ dùng word embedding làm đầu vào.

Điểm (3) quan trọng: Highway **gắn với CNN trên ký tự**, không phải cải tiến tổng quát cho mọi mô hình.

### Phân loại: 2 vấn đề của NLM thông thường và 1 cải tiến

| Nhãn | Là gì | Của ai | Loại | Cách giải quyết |
|---|---|---|---|---|
| **Vấn đề A** | Từ hiếm, từ lạ có vector tệ (mù cấu trúc từ) | NLM thông thường | **Độ chính xác** (PPL cao) | CNN trên ký tự, chia sẻ tham số |
| **Vấn đề B** | Quá nhiều tham số, mô hình nặng | NLM thông thường | **Kích thước / tài nguyên** | Bỏ bảng từ ở đầu vào |
| **Highway** | Chỉ dùng CNN thì vector thiên về chính tả | Hạn chế của **chính mô hình bài báo khi chỉ có CNN** | Cải thiện bên trong mô hình bài báo | Thêm Highway network |

### Chạy thử từ "absurdity" với kích thước thật (mô hình nhỏ, Bảng 2)

Quy ước kích thước (siêu tham số của mô hình nhỏ):

| Ký hiệu | Giá trị | Ý nghĩa |
|---|---|---|
| d | 15 | Mỗi ký tự là một vector 15 số |
| w | 1, 2, 3, 4, 5, 6 | Các độ rộng filter (filter quét 1, 2, ... 6 ký tự một lúc) |
| h | 25 × w | Số filter cho mỗi độ rộng (25, 50, 75, 100, 125, 150) |
| Tổng số filter | 525 | = 25 × (1+2+3+4+5+6) |
| Highway | 1 lớp | |
| LSTM | 2 lớp, 300 đơn vị ẩn | |

**Bước 0: chuẩn bị chuỗi ký tự.** Từ "absurdity" có 9 chữ. Bài báo thêm **ký tự bắt đầu từ** và **ký tự kết thúc từ** (chú thích 4) để nhận ra tiền tố và hậu tố:

```
[bắt đầu]  a  b  s  u  r  d  i  t  y  [kết thúc]   → 11 ký tự
```

Mỗi ký tự tra bảng ký tự lấy vector 15 số → **ma trận 15 hàng × 11 cột** (mỗi cột là một ký tự). (Thực tế còn đệm số 0 để mọi từ cùng độ dài, phục vụ xử lý theo lô.)

**Khối 1: CNN.** Một filter có độ rộng 3 trượt dọc dải ký tự, mỗi lần nhìn **3 ký tự liền nhau** (một n-gram ký tự), cho một điểm số:

```
[bắt đầu a b] [a b s] [b s u] [s u r] [u r d] [r d i] [d i t] [i t y] [t y kết thúc]
   9 vị trí (11 − 3 + 1 = 9) → 9 điểm số
```

Sau đó **max-over-time pooling**: chỉ giữ **điểm cao nhất** trong 9 điểm.
> *"The idea is to capture the most important feature--the one with the highest value--for a given filter."*
>
> **Dịch:** Ý tưởng là nắm bắt đặc trưng quan trọng nhất, tức là đặc trưng có giá trị cao nhất, đối với một filter cho trước.

Ý nghĩa: "trong cả từ này, mẫu mà filter của tôi tìm có xuất hiện mạnh nhất cỡ nào?", không quan tâm mẫu nằm ở vị trí nào. Ví dụ thực tế: **máy dò kim loại trên bãi biển** quét cả bãi và chỉ báo **tín hiệu mạnh nhất**.

525 filter như vậy, mỗi cái cho một số → ghép thành **một vector 525 số** đại diện cho từ. Nhờ max-over-time pooling, từ dài 3 ký tự hay 15 ký tự đều cho vector **cùng cỡ**.

**Khối 2: Highway.** Vector 525 số đi qua 1 lớp Highway. **Kích thước giữ nguyên (525 số)**:
> *"By construction the dimensions of y and z have to match, and hence W_T and W_H are square matrices."*
>
> **Dịch:** Theo cách xây dựng, số chiều của y và z phải khớp nhau, do đó W_T và W_H là các ma trận vuông.

**Khối 3: LSTM + softmax.** Vector 525 số này là **đầu vào của LSTM tại bước t** (thay cho vector tra bảng). LSTM kết hợp nó với ký ức các từ trước (300 đơn vị ẩn), rồi qua softmax cho bảng xác suất trên 10.000 từ. Kỳ vọng: "is" có xác suất cao.

**Luồng kích thước:**
```
absurdity (9 chữ)
  → 11 ký tự (thêm bắt đầu/kết thúc)
  → ma trận 15 × 11
  → CNN 525 filter + max-over-time
  → vector 525
  → Highway (1 lớp)
  → vector 525
  → LSTM 2 lớp (300 đơn vị ẩn) + ký ức
  → softmax
  → bảng 10.000 xác suất
```

### Cái giá phải trả (mục "Further Observations")

> *"...on PTB the large character-level model trained at 1500 tokens/sec compared to the word-level model which trained at 3000 tokens/sec."*
>
> **Dịch:** ...trên PTB, mô hình mức ký tự cỡ lớn huấn luyện với tốc độ 1.500 từ/giây, so với 3.000 từ/giây của mô hình mức từ.

> *"For scoring, our model can have the same running time as a pure word-level model, as the CharCNN's outputs can be pre-computed for all words in V."*
>
> **Dịch:** Khi chấm điểm, mô hình của chúng tôi có thể có thời gian chạy bằng mô hình mức từ thuần, vì đầu ra của CharCNN có thể được tính trước cho mọi từ trong V.

Tức là: huấn luyện **chậm hơn** (thêm phép tích chập trên ký tự); khi chạy có thể tính trước để nhanh bằng, nhưng **đổi lại tốn bộ nhớ hơn** (đánh đổi tốc độ và bộ nhớ).

### Ba hiểu nhầm thường gặp

| Hiểu nhầm | Đúng là |
|---|---|
| "Mô hình sinh từng ký tự" | **Không.** Đầu vào là ký tự, nhưng đầu ra vẫn là xác suất của **từ** |
| "Mỗi filter học đúng một hình vị (un, event, ful...)" | Chỉ là trực giác; bài báo thấy filter **không phải lúc nào cũng khớp hình vị** |
| "Mô hình bỏ hoàn toàn mọi bảng theo từ" | **Không.** Bảng theo từ **vẫn còn ở đầu ra** (softmax) |

### Bài báo nói gì / người học tự thêm gì (mục 1.4)

**Là của bài báo:**
- Mô hình dùng CNN + Highway trên ký tự rồi đưa vào LSTM; đầu vào là ký tự, dự đoán ở mức từ.
- Không cần gán nhãn hình thái trước; không dùng word embedding ở đầu vào; ít tham số hơn.
- Highway cải thiện PPL (Bảng 7) và làm vector mang ngữ nghĩa (Bảng 6).
- Chậm hơn khi huấn luyện, có thể tính trước khi chấm điểm.
- Các số liệu ở Bảng 1–8.
- Mô hình hình vị là mô hình đối chứng do bài báo tự huấn luyện (công thức (11), Morfessor Cat-MAP, vì sao dùng LSTM để so sánh công bằng).
- Công thức Highway, cổng biến đổi / cổng giữ nguyên, khởi tạo b_T quanh −2, giả thuyết Highway hợp với CNN, quan sát (1)–(3).
- Kỳ vọng ban đầu về filter và kết quả PCA (Hình 2: tiền tố, hậu tố, dấu gạch nối).
- Chỉ thay từ singleton bằng `<unk>` và việc cố ý không dùng mặt chữ của `<unk>`.

**Là của người học (diễn giải, không có trong bài báo):**
- Cách gọi **chia sẻ tham số** và ví dụ có số ("ful", "ly"...).
- Ví dụ: đọc sách theo từ / ký tự, nhận biết món ăn qua tên, đánh vần, học đọc, máy quét mã vạch, biên tập viên, máy dò kim loại, từ điển 10.000 trang.
- Phép tính 134 triệu so với 5 triệu.
- Cách phân loại "vấn đề A / vấn đề B / cải tiến Highway".
- Phần chạy thử "absurdity" là tính toán áp dụng kích thước Bảng 2 vào ví dụ của Hình 1.
- Các ví dụ minh họa: ghép Lego, "xe cùng động cơ" (vì sao cần mô hình hình vị dùng LSTM), hai thí sinh thi cùng đề, đội trinh sát, đường cao tốc, ví dụ số Highway (1,6 và 7,4), cách cắt "un + event + ful + ly" (Morfessor có thể cắt khác).
- Nhận xét "với b_T = −2 thì t ≈ 0,12, giữ khoảng 88% bản gốc" (tính từ công thức sigmoid).

### Tóm tắt 1.4 (có thể chép vào báo cáo)

| | Nội dung |
|---|---|
| **Ý tưởng** | Tạo vector của từ từ **ký tự** bằng CNN + Highway, thay cho bảng tra word embedding |
| **Luồng** | Ký tự → CNN (nhiều filter nhiều độ rộng, max-over-time pooling) → Highway → LSTM → Softmax trên từ vựng |
| **Chìa khóa** | **Chia sẻ tham số**: mọi từ dùng chung filter và bảng ký tự |
| **Khác nghiên cứu trước** | Không cần phân tích hình vị; không dùng word embedding ở đầu vào; ít tham số hơn khi từ vựng lớn |
| **Giữ nguyên** | Dự đoán ở mức từ; LSTM; hàm mất mát; perplexity |
| **Cái giá** | Huấn luyện chậm hơn (1.500 so với 3.000 từ/giây) |

---

## 1.5. Đóng góp của bài báo

### Ý chính
**Đóng góp (contribution)** là phần tác giả **tự nêu**: bài báo làm được điều gì mới hoặc tốt hơn. Báo cáo của nhóm cần nêu rõ phần này. Bài báo có danh sách đóng góp rõ ràng ở cuối Introduction, cộng thêm hai đóng góp phụ ở Abstract và Discussion.

> *"To summarize, our contributions are as follows: • on English, we achieve results on par with the existing state-of-the-art on the Penn Treebank (PTB), despite having approximately 60% fewer parameters, and • on morphologically rich languages (Arabic, Czech, French, German, Spanish, and Russian), our model outperforms various baselines (Kneser-Ney, word-level/morpheme-level LSTM), again with fewer parameters."*
>
> **Dịch:** Tóm lại, các đóng góp của chúng tôi như sau: • Trên tiếng Anh, chúng tôi đạt kết quả ngang với mức tốt nhất hiện có (state-of-the-art) trên Penn Treebank (PTB), dù có ít hơn khoảng 60% tham số, và • Trên các ngôn ngữ giàu hình thái (Ả Rập, Czech, Pháp, Đức, Tây Ban Nha và Nga), mô hình của chúng tôi vượt nhiều mô hình cơ sở (baseline) (Kneser-Ney, LSTM mức từ / mức hình vị), cũng với ít tham số hơn.

**Hai thuật ngữ cần biết:** **state-of-the-art** (SOTA) là kết quả tốt nhất đã công bố tại thời điểm đó; **baseline (mô hình cơ sở)** là mô hình dùng làm mốc để so sánh (ở đây: Kneser-Ney n-gram, LSTM mức từ, LSTM mức hình vị).

### Đóng góp 1: Tiếng Anh, ngang mức tốt nhất, ít tham số hơn nhiều

| Mô hình (Bảng 3, PTB) | PPL | Tham số |
|---|---|---|
| LSTM-2 (Zaremba 2014, **tốt nhất lúc đó**) | **78,4** | 52 triệu |
| **LSTM-Char-Large (bài báo)** | 78,9 | **19 triệu** |
| LSTM-1 (Zaremba 2014) | 82,7 | 20 triệu |
| LSTM-Word-Large (bài báo tự huấn luyện) | 85,4 | 20 triệu |
| KN-5 (n-gram, không nơ-ron) | 141,2 | 2 triệu |

**Ví dụ thực tế:** hai chiếc xe chạy cùng quãng đường với **tốc độ gần bằng nhau**, nhưng xe của bài báo chỉ nặng khoảng **một phần ba** (19 so với 52 triệu tham số).

**Cách nói đúng:**
- Nói **"ngang bằng"** (*on par*), **không** nói "tốt hơn", vì 78,9 chỉ kém 78,4 một chút.
- "Ít hơn khoảng 60%" là so với **LSTM-2**. So với mô hình từ **cùng cỡ** (20 triệu) thì tham số gần bằng nhau, nhưng PPL bài báo tốt hơn (78,9 so với 85,4). Đã giải thích ở 1.4.
- Bảng 3 ghi chú: số tham số của một số mô hình cũ là **ước lượng** của tác giả vì các nghiên cứu đó không nêu rõ.

### Đóng góp 2 (đóng góp chính): Ngôn ngữ giàu hình thái, vượt các mô hình so sánh

> *"English is relatively simple from a morphological standpoint, and thus our next set of results (and arguably the main contribution of this paper) is focused on languages with richer morphology (Table 4, Table 5)."*
>
> **Dịch:** Tiếng Anh khá đơn giản về mặt hình thái, nên nhóm kết quả tiếp theo của chúng tôi (và có thể nói là đóng góp chính của bài báo này) tập trung vào các ngôn ngữ giàu hình thái hơn (Bảng 4, Bảng 5).

Bảng 4 (bộ dữ liệu nhỏ DATA-S, mô hình cỡ nhỏ; số là PPL, thấp là tốt):

| Ngôn ngữ | Từ (Word) | Hình vị (Morph) | **Ký tự (Char)** |
|---|---|---|---|
| Czech (CS) | 503 | 414 | **401** |
| German (DE) | 305 | 278 | **260** |
| Spanish (ES) | 212 | 197 | **182** |
| French (FR) | 229 | 216 | **189** |
| Russian (RU) | 352 | 290 | **278** |
| Arabic (AR) | 216 | 230 | **196** |

**Hai điều dễ bỏ sót (nên nói cho đúng):**
- Ở **Arabic**, mô hình hình vị (230) lại **tệ hơn** mô hình từ (216). Ở Bảng 5 (bộ dữ liệu lớn DATA-L, mô hình cỡ nhỏ) cũng vậy với Spanish (186 so với 189) và French (202 so với 209). Bài báo nhận xét:
  > *"Interestingly we do not observe significant differences going from word to morpheme LSTMs on Spanish, French, and English."*
  >
  > **Dịch:** Điều thú vị là chúng tôi không thấy khác biệt đáng kể khi đi từ LSTM mức từ sang LSTM mức hình vị ở tiếng Tây Ban Nha, Pháp và Anh.

  Tức là thêm thông tin hình vị không phải lúc nào cũng giúp; mô hình ký tự vẫn tốt nhất.
- Ở Bảng 4 với mô hình **cỡ lớn**, hàng Arabic cho **Hình vị 148 = Ký tự 148 (hòa)**. Do đó "mô hình ký tự đạt PPL thấp nhất **hoặc bằng thấp nhất**" chính xác hơn "thấp nhất ở mọi trường hợp".

**Ngay cả tiếng Anh cũng hưởng lợi khi từ vựng lớn:**
> *"We also observe significant perplexity reductions even on English when V is large."*
>
> **Dịch:** Chúng tôi cũng thấy perplexity giảm đáng kể ngay cả ở tiếng Anh khi V lớn.

(Bảng 5, tiếng Anh DATA-L, cỡ nhỏ: Từ 236, Hình vị 233, Ký tự 216.)

**Một điểm mạnh nữa: không cần chỉnh riêng cho từng ngôn ngữ:**
> *"We conclude this section by noting that we used the same architecture for all languages and did not perform any language-specific tuning of hyperparameters."*
>
> **Dịch:** Chúng tôi kết thúc phần này bằng việc lưu ý rằng chúng tôi dùng cùng một kiến trúc cho mọi ngôn ngữ và không thực hiện bất kỳ việc chỉnh siêu tham số riêng cho ngôn ngữ nào.

Ví dụ thực tế: một vận động viên chạy **cùng một cự ly ở 6 giải đấu khác nhau** và đều về nhất (hoặc đồng hạng nhất), mà không phải thay giày hay chiến thuật cho từng giải. Điều này thuyết phục hơn thắng một giải.

**Cách nói đúng:** "Mô hình ký tự đạt PPL thấp nhất hoặc bằng thấp nhất trong các mô hình so sánh ở cả 6 ngôn ngữ, với ít tham số hơn mô hình từ khi từ vựng lớn."

### Đóng góp phụ 3: Đầu vào ký tự là đủ cho nhiều ngôn ngữ

> *"The results suggest that on many languages, character inputs are sufficient for language modeling."*
>
> **Dịch:** Các kết quả gợi ý rằng trên nhiều ngôn ngữ, đầu vào là ký tự là đủ cho mô hình hóa ngôn ngữ.

> *"Our work questions the necessity of word embeddings (as inputs) for neural language modeling."*
>
> **Dịch:** Công trình của chúng tôi đặt câu hỏi về sự cần thiết của word embedding (làm đầu vào) đối với mô hình ngôn ngữ nơ-ron.

**Bằng chứng bổ sung (Discussion):** ghép word embedding **cùng với** đầu ra CharCNN cho kết quả **hơi tệ hơn** (PPL 81 với mô hình lớn trên PTB), không tốt hơn:
> *"While this could be due to insufficient experimentation on our part, it suggests that for some tasks, word embeddings are superfluous--character inputs are good enough."*
>
> **Dịch:** Dù điều này có thể do chúng tôi thử nghiệm chưa đủ, nó gợi ý rằng với một số tác vụ, word embedding là thừa; đầu vào ký tự là đủ tốt.

**Lưu ý:** đây là kết luận **dè dặt** (tác giả tự thừa nhận có thể thử nghiệm chưa đủ), nên báo cáo dùng "**gợi ý**", không dùng "chứng minh". Cũng nhớ rằng mô hình vẫn dùng bảng theo từ ở **đầu ra**; "không cần word embedding" chỉ nói về **đầu vào**.

### Đóng góp phụ 4: Mô hình mã hóa cả chính tả lẫn ngữ nghĩa từ ký tự

> *"Analysis of word representations obtained from the character composition part of the model reveals that the model is able to encode, from characters only, both semantic and orthographic information."*
>
> **Dịch:** Phân tích các biểu diễn từ thu được từ phần ghép ký tự của mô hình cho thấy mô hình có thể mã hóa, chỉ từ các ký tự, cả thông tin ngữ nghĩa lẫn thông tin chính tả.

Bằng chứng: Bảng 6 (từ "you": trước Highway gần *your, young*, sau Highway gần *we*) và Hình 2 (PCA: tiền tố, hậu tố, dấu gạch nối). Đã học ở 1.4.

### Đóng góp thứ năm (thực tế): công bố mã nguồn
> *"We have released all the code for the models described in this paper."*
>
> **Dịch:** Chúng tôi đã công bố toàn bộ mã nguồn của các mô hình được mô tả trong bài báo này.

Địa chỉ (chú thích 1): github.com/yoonkim/lstm-char-cnn. Ý nghĩa: người khác có thể **chạy lại và kiểm chứng**.

### Hướng nghiên cứu tiếp theo (Future work)
> *"Using the CharCNN and highway layers for representation learning (e.g. as input into word2vec) remains an avenue for future work. ...it would be interesting to see if the architecture introduced in this paper is viable for other tasks--for example, as an encoder/decoder in neural machine translation."*
>
> **Dịch:** Dùng CharCNN và các lớp highway để học biểu diễn (ví dụ làm đầu vào cho word2vec) vẫn là một hướng cho công việc tương lai. ...sẽ thú vị nếu xem kiến trúc giới thiệu trong bài báo này có khả thi cho các tác vụ khác không, ví dụ làm bộ mã hóa/giải mã trong dịch máy nơ-ron.

### Nên nói gì và tránh nói gì khi báo cáo

| Chủ đề | **Nên nói** | **Tránh nói** |
|---|---|---|
| Tiếng Anh (PTB) | "Ngang bằng mức tốt nhất, ít hơn khoảng 60% tham số (so với LSTM-2)" | "Tốt hơn mô hình tốt nhất" (78,9 so với 78,4) |
| 6 ngôn ngữ | "PPL thấp nhất hoặc bằng thấp nhất trong các mô hình so sánh, ít tham số hơn khi từ vựng lớn" | "Thắng tuyệt đối ở mọi trường hợp" (có ô hòa: Arabic cỡ lớn 148 = 148) |
| Ký tự là đủ | "Gợi ý rằng đầu vào ký tự là đủ" | "Chứng minh word embedding là thừa" |
| OOV | "Minh họa định tính ở Bảng 6" | "Đo được lợi thế OOV bằng số liệu" |
| Hình vị | "Học được biểu diễn mang thông tin tiền tố, hậu tố" | "Mỗi filter học đúng một hình vị" |

### Bài báo nói gì / người học tự thêm gì (mục 1.5)

**Là của bài báo:** danh sách đóng góp (Introduction), hai đóng góp phụ (Abstract, Discussion), công bố mã nguồn, hướng nghiên cứu tiếp theo, mọi con số trong Bảng 3, 4, 5.

**Là của người học (diễn giải):** ví dụ hai chiếc xe, vận động viên 6 giải; bảng "nên nói / tránh nói"; việc nhận ra các ô mô hình hình vị tệ hơn mô hình từ (Arabic Bảng 4; Spanish, French Bảng 5) và ô hòa 148 = 148 (đọc trực tiếp từ bảng, bài báo không nêu riêng); cách đánh số "đóng góp phụ 3, 4, thứ năm".

### Tóm tắt 1.5 (bản nháp chép vào slide báo cáo)

> **Đóng góp của bài báo**
> 1. **Tiếng Anh (PTB):** PPL 78,9 ngang mô hình tốt nhất (78,4) với 19 triệu tham số so với 52 triệu (ít hơn khoảng 60%).
> 2. **6 ngôn ngữ giàu hình thái** (Ả Rập, Czech, Pháp, Đức, Tây Ban Nha, Nga): PPL thấp hơn hoặc bằng mô hình từ và mô hình hình vị, ít tham số hơn khi từ vựng lớn; cùng một kiến trúc cho mọi ngôn ngữ.
> 3. Gợi ý **đầu vào ký tự là đủ** cho mô hình ngôn ngữ.
> 4. Mô hình **mã hóa cả chính tả và ngữ nghĩa** chỉ từ ký tự (Bảng 6, Hình 2).
> 5. **Công khai mã nguồn.**

---

## Bảng thuật ngữ (cập nhật dần)

| Thuật ngữ | Giải thích đời thường | Học ở |
|---|---|---|
| Language model (LM) | Mô hình chấm "độ tự nhiên" của câu hoặc đoán từ kế tiếp | 1.1 |
| n-gram | Đoán từ kế tiếp dựa trên n−1 từ liền trước; học bằng cách đếm | 1.1 |
| Unigram / bigram / trigram | n-gram với n = 1 / 2 / 3 (nhìn 0 / 1 / 2 từ trước) | 1.1 |
| Data sparsity | Nhiều cụm từ không bao giờ xuất hiện trong dữ liệu nên xác suất bằng 0 | 1.1 |
| Làm mịn (smoothing) | Kỹ thuật để cụm chưa gặp không bị xác suất 0 (add-one, Kneser-Ney...) | 1.1 |
| Vocabulary (V) | Danh sách tất cả các từ mô hình biết | 1.2 |
| Token, T | Tổng số từ trong văn bản, mỗi lần xuất hiện đều đếm (quy mô dữ liệu) | 1.2 |
| \|V\| | Số từ khác nhau (kích thước từ vựng mức từ) | 1.2 |
| \|C\| | Số ký tự khác nhau (kích thước từ vựng mức ký tự) | 1.2 |
| PTB (Penn Treebank) | Kho ngữ liệu tiếng Anh ~1 triệu token, từ vựng 10.000 từ, bộ chuẩn để so sánh mô hình ngôn ngữ | 1.2 |
| Time step | Một bước đọc một từ trong chuỗi | 1.2 |
| Huấn luyện (training) | Mô hình đoán, so với đáp án thật, chỉnh tham số, lặp lại nhiều lần | 1.2 |
| Loss (NLL) | Độ lỗi: từ thật được cho xác suất càng thấp thì loss càng lớn | 1.2 |
| Tham số (parameters) | Các con số mô hình tự học (như nút vặn mixer, hệ số a, b, c của công thức giá nhà) | 1.2 |
| Siêu tham số (hyperparameters) | Lựa chọn thiết kế do con người đặt trước (như công thức nấu ăn) | 1.2 |
| Epoch | Một lượt đọc hết toàn bộ dữ liệu huấn luyện | 1.2 |
| Train / validation / test | Dữ liệu để học / để chọn mô hình / để chấm cuối cùng | 1.2 |
| SGD, backpropagation | Cách tự động chỉnh tham số cho loss giảm (học kỹ ở Bước 6) | 1.2 |
| Perplexity (PPL) | Thước đo độ "bối rối" của mô hình; thấp là tốt | 1.2 |
| Làm mịn add-one (Laplace) | Cộng 1 vào mọi số đếm: (c + 1) / (N + V); hết xác suất 0 nhưng chia đều cho cụm chưa gặp | 1.3 |
| Kneser-Ney (KN) | Kỹ thuật làm mịn n-gram tinh vi hơn add-one; bài báo dùng làm mốc so sánh | 1.3 |
| Neural LM (NLM) | Mô hình ngôn ngữ dùng mạng nơ-ron, biểu diễn từ bằng vector | 1.3 |
| Word embedding | Vector số đại diện cho một từ; từ gần nghĩa thì vector gần nhau | 1.3 |
| NLM thông thường | NLM tạo vector cho từ bằng cách tra bảng theo từ | 1.3 |
| Subword information | Thông tin bên trong từ (tiền tố, hậu tố, gốc từ, ký tự) | 1.3 |
| Morpheme (hình vị) | Đơn vị nhỏ nhất có nghĩa trong từ (un-, event, -ful) | 1.3 |
| Hình thái học (morphology) | Nghiên cứu cách từ được xây dựng; tách từ chỉ là một phần của nó | 1.3 |
| Morphologically rich | Ngôn ngữ mà một từ gốc có rất nhiều dạng biến đổi (Đức, Nga, Czech...); tiếng Việt không thuộc nhóm này | 1.3 |
| OOV (out-of-vocabulary) | Từ ngoài từ điển, từ chưa từng thấy; khác từ hiếm (từ hiếm có trong từ điển nhưng ít gặp) | 1.3 |
| `<unk>` | Ký hiệu chung gộp mọi từ lạ/từ hiếm; bài báo chỉ thay từ xuất hiện đúng 1 lần | 1.3 (cách bài báo dùng: 1.4) |
| Long-tailed distribution | Vài từ rất phổ biến, rất nhiều từ cực hiếm | 1.3 |
| Mô hình từ / hình vị / ký tự | NLM tạo vector của từ bằng tra bảng / bảng + hình vị / đọc ký tự | 1.4 |
| Mô hình thuần ký tự | Đầu vào **và đầu ra** đều là ký tự (khác mô hình bài báo) | 1.4 |
| CNN, filter | Mạng quét chuỗi để tìm mẫu; mỗi filter là một "máy quét" một mẫu ký tự | 1.4 (chi tiết Bước 3) |
| Max-over-time pooling | Chỉ giữ giá trị lớn nhất của mỗi filter trên cả từ | 1.4 (chi tiết Bước 3) |
| Highway network | Mạng nhỏ tinh chỉnh vector, có cổng giữ/biến đổi (như biên tập viên) | 1.4 (chi tiết Bước 4) |
| Chia sẻ tham số | Mọi từ dùng chung filter và bảng ký tự, nên các mảnh ký tự được học từ nhiều từ | 1.4 |
| Ablation study | Thí nghiệm bỏ từng thành phần để xem nó đóng góp bao nhiêu (ví dụ bỏ Highway, Bảng 7) | 1.4 |
| Morfessor | Công cụ tự động tách hình vị, chạy trước khi huấn luyện mô hình hình vị | 1.4 |
| MLBL | Mô hình hình thái log-bilinear của Botha (2014), mốc so sánh trong Bảng 4, 5 | 1.4 |
| Singleton | Từ chỉ xuất hiện đúng 1 lần trong dữ liệu; bài báo chỉ thay loại từ này bằng `<unk>` | 1.4 |
| PCA | Kỹ thuật thu gọn vector nhiều chiều xuống 2 chiều để vẽ biểu đồ (Hình 2) | 1.4 |
| Transform gate / carry gate | Cổng biến đổi (t) và cổng giữ nguyên (1 − t) của Highway, mỗi số trong khoảng 0 đến 1 | 1.4 (chi tiết Bước 4) |
| Sigmoid (σ) | Hàm biến mọi số thành một số trong khoảng 0 đến 1 | 1.4 (chi tiết Bước 4) |
| State-of-the-art (SOTA) | Kết quả tốt nhất đã được công bố tại thời điểm đó | 1.5 |
| Baseline (mô hình cơ sở) | Mô hình dùng làm mốc so sánh (Kneser-Ney, LSTM mức từ, LSTM mức hình vị) | 1.5 |
| On par | "Ngang bằng": kết quả gần như bằng, không phải tốt hơn | 1.5 |

> Còn sẽ bổ sung: RNN, LSTM, softmax, hàm mất mát... (ở các bước sau).

---

## Câu hỏi tự kiểm tra

**Bước 1.1 – 1.2**
1. Mô hình ngôn ngữ làm việc gì? Cho ví dụ từ điện thoại của bạn.
2. Bigram và trigram khác nhau chỗ nào? Vì sao không dùng n thật lớn?
3. Input và output của bài toán trong bài báo là gì? Điểm khác thường?
4. Huấn luyện gồm những bước nào? Loss lớn hay nhỏ khi mô hình cho từ thật xác suất thấp?
5. Tham số và siêu tham số khác nhau thế nào? Cho ví dụ.
6. Vì sao phải đo kết quả trên tập test chứ không phải tập train?
7. PPL = 10 nghĩa là gì? PPL 78,9 và 141,2, cái nào tốt hơn?

**Bước 1.3**
8. Add-one làm mịn giúp được gì và chưa đủ ở chỗ nào? (gợi ý: "uống trà" và "uống bàn")
9. NLM khắc phục lỗi thưa dữ liệu của n-gram như thế nào? Vì sao "trà" ở gần "cà phê" dù không ai gán tay?
10. "NLM thông thường" là gì? Nó tạo vector cho từ bằng cách nào?
11. Vì sao từ hiếm có vector tệ hơn từ phổ biến?
12. Giải thích: "từ hiếm có vector tệ → PPL cao cho từ đó và cả các từ nằm cạnh nó".
13. "Hình thái học" và "tách từ" khác nhau thế nào? Tiếng Việt có phải ngôn ngữ giàu hình thái theo nghĩa của bài báo không?
14. Vì sao bảng word embedding làm NLM nặng?
15. OOV là gì? Khác từ hiếm ở chỗ nào? NLM thông thường xử lý OOV ra sao (`<unk>`)?

**Bước 1.4**
16. Mô hình từ, mô hình hình vị, mô hình ký tự khác nhau ở phần nào, giống nhau ở phần nào? "Mô hình ký tự" của bài báo có đầu ra là ký tự hay từ?
17. Vì sao một từ chỉ xuất hiện 1 lần vẫn có vector tốt trong mô hình bài báo? (chia sẻ tham số)
18. Mô hình bài báo xử lý từ OOV như *looooook* thế nào? Vì sao nói đây mới là bằng chứng định tính, chưa phải số liệu đo?
19. Vấn đề A, vấn đề B và Highway: cái nào là vấn đề của NLM thông thường, cái nào không? Mỗi cái thuộc loại nào?
20. Vì sao không được nói "mô hình bài báo giảm 90% tham số"? (gợi ý: lớp đầu ra)
21. Vì sao từ dài 3 ký tự và từ dài 15 ký tự đều cho ra vector cùng kích thước sau Khối 1? Max-over-time pooling giữ lại gì và bỏ đi gì?
22. Cái giá phải trả của mô hình bài báo là gì?
23. Mô hình hình vị được xây thế nào (công thức (11))? Vì sao bài báo phải tự huấn luyện phiên bản LSTM của nó thay vì chỉ so với MLBL?
24. Trong Highway, cổng t = 0,8 và t = 0,1 khác nhau thế nào? Tính z khi y = (4, 8) và g(...) = (1, 2).
25. Vì sao bài báo không cho mô hình ký tự nhìn mặt chữ của `<unk>` dù có thể làm vậy? Nên nói gì và tránh nói gì khi báo cáo về lợi thế OOV?
26. Kết quả PCA (Hình 2) cho thấy điều gì? Vì sao nó không mâu thuẫn với việc "filter không khớp hình vị"?

**Bước 1.5**
27. Phân biệt T, |V|, |C| bằng ví dụ "the cat sat on the mat". Con số nào quyết định kích thước bảng word embedding?
28. PTB là gì? Vì sao bài báo dùng PTB?
29. Bài báo nêu những đóng góp nào? Đóng góp nào được tác giả gọi là "chính"?
30. Vì sao nói "ngang bằng" chứ không nói "tốt hơn" ở kết quả tiếng Anh? "Ít hơn khoảng 60% tham số" là so với mô hình nào?
31. Ở ngôn ngữ/bảng nào mô hình hình vị tệ hơn mô hình từ? Điều đó cho biết gì? Có ô nào mô hình ký tự chỉ hòa không?
32. Vì sao kết luận "đầu vào ký tự là đủ" nên nói là "gợi ý" chứ không phải "chứng minh"?

---

*Hết Bước 1. Tiếp theo: [ghi_chu_buoc_2.md](ghi_chu_buoc_2.md) (Bước 2: Nền tảng embedding, RNN, LSTM).*

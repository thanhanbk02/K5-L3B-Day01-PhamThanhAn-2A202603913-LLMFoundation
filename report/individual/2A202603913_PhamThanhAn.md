# Báo cáo cá nhân — Day 01: Lọc tin nhắn rác bằng ML, DL, Embedding và LLM

- **MSSV:** 2A202603913
- **Họ và tên:** Phạm Thành An
- **SEED:** 7951

## 1. Bằng chứng

| Tệp | Có? |
| --- | --- |
| [`day01_lab.ipynb`](day01_lab.ipynb) — notebook đã chạy, còn output | ☑ |
| [`lab1_report.json`](lab1_report.json) — do ô "Báo cáo cuối" sinh ra | ☑ |
| [`hand_calc.jpg`](hand_calc.jpg) — ảnh tính tay có các bước | ☐ chưa nộp |

## 2. Kết quả chính

LLM chạy bằng Ollama trên máy cá nhân (CPU): model lớn `qwen2.5:7b`, model nhỏ `qwen2.5:0.5b`.

| Phương án | F1 (test) | F1 (SUB 40) | p95 ms/tin | USD / 1k tin |
| --- | ---: | ---: | ---: | ---: |
| 1. BoW + LogReg | 0.916 | 0.947 | 0.05 | 0 |
| 2. BoW + MLP | 0.953 | 0.974 | 0.29 | 0 |
| 3a. Encoder + kNN | 0.900 | 0.974 | 55.2 | 0 |
| 3b. Encoder + LogReg | 0.933 | 0.974 | 19.7 | 0 |
| 3c. Encoder + MLP head | 0.920 | 0.974 | 18.8 | 0 |
| 4a. LLM nhỏ zero-shot (qwen2.5:0.5b) | — | 0.410 | 2446.6 | 0 (chạy local) |
| 4b. LLM lớn zero-shot (qwen2.5:7b) | — | 0.950 | 2626.7 | 0 (chạy local) |

## 3. Dự đoán và thực tế

Chưa hoàn thành trước deadline.

## 4. Phân tích 50 case khó

Chưa hoàn thành trước deadline.

## 5. Thử thách cá nhân

Đề #2 (theo SEED): giảm vocab còn 100 từ và tăng lên 5000 từ. Chưa hoàn thành trước deadline.

## 6. Phương án cho sản phẩm thật

Chưa hoàn thành trước deadline.

## 7. AI log và điều đã học

Khai báo trung thực việc dùng AI (Claude Code) trong bài này:

- **Phần 1–3 (vùng tự code):** em nhờ AI viết lời giải tham khảo cho các TODO 1.1 → 3.3, và AI đã ghi thẳng code đó vào notebook. Code Phần 1–3 trong notebook nộp là **code do AI viết**, em chưa tự viết lại.
- **Phần 4 (vùng được dùng AI):** AI viết `call_openai`, `build_classification_prompt`, `parse_label`, `llm_classify_batch`, sau đó sửa thêm để xử lý giới hạn request của gói free (nghỉ giữa các lần gọi, thử lại khi lỗi 429/503) và chuyển cấu hình sang Ollama (`qwen2.5:7b` / `qwen2.5:0.5b`) sau khi Gemini free hết hạn mức và tài khoản OpenAI hết credit.
- **Dự đoán `predict(...)`:** 7 dự đoán đã ghi phần lớn được chép từ các câu mẫu AI đưa, không phải hoàn toàn do em tự nghĩ. 3 dự đoán còn lại (`llm_fewshot`, `tradeoff`, `hard_eval`) chưa làm.
- **Hướng dẫn:** AI hướng dẫn cách chạy notebook trên Colab và Jupyter, cách đọc từng thí nghiệm, cách cấu hình API key và xử lý lỗi.

Điều đã học: _(chưa viết)_

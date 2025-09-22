# DACNTT
# 1. Tạo PROJECT.md
cat > PROJECT.md <<'MD'
# Project: RAG Multimodal — Giao thông · Văn hóa · Du lịch (PoC)

## 1. Tên dự án
Phát triển hệ thống Hỏi–Đáp Đa phương thức RAG trong lĩnh vực Giao thông, Văn hóa, Du lịch (TP. Hồ Chí Minh) — PoC

## 2. Mô tả ngắn
Hệ thống trả lời câu hỏi bằng văn bản/hình ảnh hoặc kết hợp. Trả về: câu trả lời ngắn, mẹo địa điểm, ảnh minh họa và link bản đồ.

## 3. Phạm vi khởi tạo
- Thành phố target: TP. Hồ Chí Minh.
- Dữ liệu thô: Wikipedia/Wikivoyage, Wikimedia Commons (ảnh CC), OSM extracts, trang du lịch công khai (crawled).
- Thời gian PoC: 10 tuần.

## 4. Success criteria (định lượng)
- Latency: text p95 < 3s; image p95 < 4.5s.
- Retrieval: Recall@1 ≥ 0.60; Recall@5 ≥ 0.85; nDCG@10 ≥ 0.90.
- Human-eval: ≥ 80% câu trả lời "đúng/đủ" trên sample 200 queries.
- Coverage POI: ≥ 80% top-500 POI.
- Compliance: mọi ảnh public phải có metadata license; PII được redacted.

## 5. KPIs & tệp liên quan
- `eval/testset.csv` — test queries có label.
- `monitor/latency_test.sh` — latency script.
- `eval/retrieval_eval.py` — tính Recall/nDCG.
- `eval/human_eval_instructions.md` — hướng dẫn annotator.

## 6. Cấu trúc repo (tối thiểu)
- /data/
- /scripts/
- /preprocess/
- /embeddings/
- /retrieval/
- /api/
- /app/
- /eval/
- PROJECT.md

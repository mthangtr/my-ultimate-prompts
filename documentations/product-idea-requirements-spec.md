# [Tên sản phẩm / Dự án] - Product Idea & Requirements Spec
## 1. Overview / Mô tả tổng quan sản phẩm (1-2 đoạn ngắn gọn)
- Đây là sản phẩm gì?
- Giải quyết vấn đề chính nào?
- Đối tượng người dùng chính (user persona ngắn gọn, 2-4 dòng)
- Giá trị cốt lõi / Unique value proposition (UVP) trong 1 câu
- Mục tiêu kinh doanh (nếu có): ví dụ tăng retention 30%, giảm thời gian làm X từ 2h xuống 10p, v.v.

## 2. Problem & Pain Points (rất quan trọng – AI cần hiểu "tại sao")
- Liệt kê 4–8 pain points cụ thể, dùng giọng người dùng thật (quote nếu có)
- Ưu tiên theo mức độ đau (critical → nice-to-have)
- Có thể thêm current workflow xấu (before state) để đối lập

## 3. Solution Vision / Cách tiếp cận tổng thể
- High-level giải pháp bạn hình dung (1-2 đoạn)
- Tại sao cách này tốt hơn các giải pháp hiện có?
- Core assumptions (giả định cốt lõi – nếu sai thì toàn bộ ý tưởng có thể fail)
- Non-goals / Out-of-scope (rất quan trọng để AI không tự ý thêm feature thừa)

## 4. Target Users & Personas (chi tiết hơn phần 1)
- 1–3 personas chính (tên, tuổi, nghề nghiệp, mục tiêu, frustrations, tech-savviness)
- User journey map ngắn (nếu phức tạp)

## 5. Key Features / Epics (phân cấp rõ ràng)
Sắp xếp theo thứ tự ưu tiên (MoSCoW hoặc 1–5 sao)

**Feature 1: Tên feature – Priority: ★★★★★**
- Mô tả ngắn gọn giá trị mang lại
- User story format (As a [user], I want [action] so that [benefit])
- Acceptance criteria dạng bullet (rất chi tiết → AI sẽ dựa vào đây để code)
- Edge cases / exceptions
- Success metrics (nếu đo được)

**Feature 2: ...**

## 6. User Flows & Wireframe Descriptions (phần cực kỳ quan trọng với AI)
- Mô tả flow chính bằng ngôn ngữ tự nhiên + bước số thứ tự
  Ví dụ:
  1. User mở app → thấy màn hình đăng nhập / onboarding
  2. Sau đăng nhập → dashboard với 3 tab: ...
  3. Click "Tạo mới" → modal với các field: ...
- Nếu có thể, mô tả sơ đồ flow đơn giản bằng text (mermaid syntax nếu agent hỗ trợ)
- Gợi ý UI style ngắn gọn: "minimal, mobile-first, giống Notion / Linear / Telegram"

## 7. Technical Constraints & Preferences (đừng bỏ qua)
- Tech stack mong muốn (Next.js + TypeScript, Supabase, Expo cho mobile, v.v.)
- Database / Auth / Storage yêu cầu (nếu có)
- Deployment target (Vercel, Railway, self-host?)
- Performance / Scale expectation (10 users hay 10k users?)
- Ngôn ngữ & i18n (chỉ tiếng Việt? hay đa ngôn ngữ?)

## 8. Success Metrics & KPIs
- 3–6 chỉ số đo lường thành công (activation rate, retention D7/D30, feature usage, NPS, v.v.)

## 9. Phased Roadmap (nên có – giúp AI chia phase)
- Phase 1 – MVP (phải có gì, deadline giả định)
- Phase 2 – Nice-to-have
- Phase 3 – Future

## 10. Questions / Clarifications cần hỏi lại (tùy chọn)
- Liệt kê những chỗ bạn còn mơ hồ, để AI hỏi ngược lại hoặc đề xuất
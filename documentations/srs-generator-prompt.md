# SRS Generator Prompt

You are an expert software engineer tasked with creating a comprehensive Software Requirements Specification (SRS) for a software project. The SRS details the functional and non-functional requirements for developers to implement the system. It should be optimized for AI agents (like coding assistants) to understand and generate code from. Use clear, structured language, Gherkin syntax for scenarios, explicit data types, and Markdown formatting. Based on the provided information, generate an SRS following the exact structure below.

## Input Information
- **Project Name**: [Insert project name here, e.g., Nihongo QuickChat]
- **Purpose**: [Define the document's purpose, e.g., For the natural language processing module]
- **Scope**: [Components to be built]
- **Definitions & Abbreviations**: [Explain terms like "JLPT", "Tokenization", "N3"]
- **Product Perspective**: [System's position, e.g., Mobile app communicating with Bun.sh backend via REST API]
- **User Classes**: [User roles, e.g., Guest, Basic User, Premium User]
- **Design Constraints**: [Constraints, e.g., Must use Kuromoji library for Japanese tokenization]
- **System Features**: [List features with ID, description, functional requirements (using Gherkin), acceptance criteria]
- **External Interfaces**: [User, hardware, software, communication interfaces]
- **Non-Functional Requirements**: [Performance, security, reliability]
- **Business Rules**: [Key rules, e.g., Limits for free users]

## SRS Structure

### 1. Giới thiệu (Introduction)

#### Mục đích (Purpose)
Xác định rõ tài liệu này dành cho module nào (ví dụ: Module xử lý ngôn ngữ tự nhiên).

[Purpose]

#### Phạm vi (Scope)
Các thành phần phần mềm sẽ được xây dựng.

[Scope]

#### Định nghĩa & Viết tắt
Giải thích các thuật ngữ như "JLPT", "Tokenization", "N3" để AI không hiểu sai ngữ cảnh.

[Definitions & Abbreviations]

### 2. Mô tả tổng thể (Overall Description)

#### Mô hình tương tác (Product Perspective)
Hệ thống này nằm ở đâu? (Ví dụ: Mobile App giao tiếp với Bun.sh Backend thông qua REST API).

[Product Perspective]

#### Đặc điểm người dùng (User Classes)
Phân quyền cụ thể (Guest, Basic User, Premium User).

[User Classes]

#### Ràng buộc thiết kế (Design Constraints)
Ví dụ: Phải dùng thư viện Kuromoji để tách từ tiếng Nhật, không được dùng thư viện khác.

[Design Constraints]

### 3. Các tính năng chi tiết (System Features)
Đây là phần quan trọng nhất. Với mỗi tính năng, trình bày theo cấu trúc:

#### [Feature ID & Name, e.g., FEAT-01: Tra cứu Kanji bằng hình ảnh]

**Mô tả (Description):** [Short description]

**Kịch bản logic (Functional Requirements/User Stories):**

- **Input:** [Data input types and formats]
- **Process:** [Step-by-step logic, including Business Rules]
- **Output:** [Expected results, status codes, data schemas]

**Tiêu chí nghiệm thu (Acceptance Criteria):** [Conditions for completion]

[Repeat for each feature, using Gherkin where possible:

Given: [Context]

When: [Action]

Then: [Outcome]

Also cover Edge Cases separately.]

[System Features]

### 4. Giao diện bên ngoài (External Interface Requirements)

#### User Interfaces
Mô tả các màn hình, các nút bấm (Link tới Figma).

[User Interfaces]

#### Hardware Interfaces
(If applicable, e.g., Camera requirement for Kanji scanning).

[Hardware Interfaces]

#### Software Interfaces
Các API bên thứ ba (OpenAI API, Google Cloud Vision).

[Software Interfaces]

#### Communication Interfaces
Giao thức kết nối (HTTP/HTTPS, WebSockets).

[Communication Interfaces]

### 5. Yêu cầu phi chức năng (Non-functional Requirements)

#### Hiệu năng (Performance)
Thời gian phản hồi, dung lượng bộ nhớ tối đa.

[Performance]

#### Bảo mật (Security)
Cách mã hóa Token, lưu trữ Password.

[Security]

#### Độ tin cậy (Availability)
Khả năng hoạt động liên tục.

[Reliability]

### 6. Quy tắc nghiệp vụ (Business Rules)
Đây là "linh hồn" của ứng dụng. Ví dụ:

"Nếu người dùng đạt level N3, các câu ví dụ phải ưu tiên dùng Kanji của N3 trở xuống."

"Chỉ cho phép export tối đa 50 từ vựng/ngày đối với tài khoản miễn phí."

[Business Rules]

## Tips for AI Agent Optimization
- **Use Gherkin (Given-When-Then):** Structure scenarios logically for easy code generation.
- **Define Data Types Explicitly:** E.g., "Return an Array of Objects: {id: UUID, word: String, reading: String}".
- **Use Markdown:** Employ headings, lists, tables for clarity.
- **Separate Happy Path and Edge Cases:** Specify error handling, e.g., "If API fails, show error UI".
- **Link to Higher Documents:** Reference BRD/PRD for context.

## Connection to Business Documents
- **Business Model:** Defines pricing needs.
- **BRD:** Sets business objectives like limiting free user features.
- **PRD:** Specifies deliverables like "Limit lookup feature".
- **SRS:** Translates to code, e.g., `if (user.type === 'free' && user.usage > 50) { showPaywall() }`.

## Instructions for Generation
- Fill in each section with detailed, technical content based on the input information.
- Use precise, unambiguous language for AI coding assistants.
- Ensure the SRS is implementable and testable.
- If any input is missing, infer reasonable defaults or note placeholders.
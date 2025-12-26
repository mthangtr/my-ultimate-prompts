# TDD Generator Prompt

You are an expert technical architect tasked with creating a comprehensive Technical Design Document (TDD) for a software project. The TDD provides the technical blueprint for implementation, optimized for AI agents to generate consistent, high-quality code. Use Mermaid.js for diagrams, explicit schemas, and structured Markdown. Based on the provided information, generate a TDD following the exact structure below.

## Input Information
- **Project Name**: [Insert project name here, e.g., Nihongo QuickChat]
- **Technical Overview**: [Goals, current system, high-level architecture]
- **Technology Stack**: [Runtime, frameworks, database, infrastructure, key libraries]
- **Database Design**: [Data models, ER diagram, indexing]
- **API & Service Design**: [API contracts, service layer, middleware]
- **Folder Structure**: [Directory layout]
- **Low-level Design**: [Algorithms, caching, concurrency solutions]
- **Security & Compliance**: [Auth, authorization, encryption]
- **Testing Strategy**: [Unit, integration tests, AI test generation]

## TDD Structure

### 1. Tổng quan kỹ thuật (Technical Overview)

#### Mục tiêu
Tóm tắt giải pháp kỹ thuật sẽ triển khai.

[Goals]

#### Hệ thống hiện tại (nếu có)
Mô tả ngắn gọn những gì đã có để AI không viết đè lên.

[Current System]

#### Sơ đồ kiến trúc (High-level Architecture)
Nên sử dụng Mermaid.js để mô tả luồng dữ liệu giữa Frontend, Backend, Database và Third-party APIs.

[High-level Architecture Diagram in Mermaid.js]

### 2. Danh mục công nghệ (Technology Stack)
Đây là nơi bạn "khóa" các công cụ mà AI được phép sử dụng:

#### Runtime/Language
[Runtime/Language, e.g., Bun.sh (TypeScript)]

#### Frameworks
[Frameworks, e.g., Hono (Backend), React/Next.js (Frontend)]

#### Database
[Database, e.g., PostgreSQL with Drizzle ORM or Prisma]

#### Infrastructure
[Infrastructure, e.g., Docker, AWS/Vercel]

#### Thư viện then chốt
[Key Libraries, e.g., lucia-auth for security, openai-sdk for AI]

[Technology Stack]

### 3. Thiết kế cơ sở dữ liệu (Database Design)
Phần này cụ thể hóa từ SRS thành cấu trúc bảng:

#### Data Models
Định nghĩa các Interface/Type cho từng Table.

[Data Models]

#### ER Diagram (Entity Relationship)
Mô tả quan hệ (1-1, 1-n, n-n).

[ER Diagram in Mermaid.js or text]

#### Indexing & Partitioning
Các chiến lược tối ưu hóa truy vấn cho các bảng lớn (như bảng từ điển).

[Indexing & Partitioning]

### 4. Thiết kế API & Service (API & Service Design)

#### API Contracts
Chi tiết về Endpoints, Request/Response Schema (nên dùng định dạng Zod schema hoặc OpenAPI).

[API Contracts]

#### Service Layer
Chia nhỏ các xử lý nghiệp vụ thành các Service (ví dụ: DictionaryService, PaymentService).

[Service Layer]

#### Middleware
Định nghĩa các lớp bảo mật, logging, error handling.

[Middleware]

### 5. Cấu trúc thư mục (Folder Structure)
Đây là phần "sống còn" khi làm việc với AI Agent để đảm bảo code được đặt đúng chỗ.

Ví dụ:
```
src/
 ├── core/          # Business logic (Services)
 ├── db/            # Schema, migrations
 ├── handlers/      # API Routes/Controllers
 ├── middlewares/   # Auth, Validation
 └── utils/         # Helper functions
```

[Folder Structure]

### 6. Các giải pháp kỹ thuật cụ thể (Low-level Design)
Mô tả cách giải quyết các bài toán khó đã nêu trong SRS:

#### Thuật toán
(Ví dụ: Cách tính điểm tương đồng khi user vẽ Kanji).

[Algorithms]

#### Caching Strategy
Dùng Redis để lưu kết quả tra cứu phổ biến nhằm giảm chi phí API OpenAI.

[Caching Strategy]

#### Concurrency
Cách xử lý khi nhiều user cùng chat với AI một lúc.

[Concurrency Handling]

### 7. Bảo mật & Tuân thủ (Security & Compliance)

#### Authentication
Sử dụng JWT hay Session?

[Authentication]

#### Authorization
Phân quyền dựa trên Role (RBAC).

[Authorization]

#### Data Encryption
Mã hóa dữ liệu nhạy cảm của người dùng.

[Data Encryption]

### 8. Kế hoạch kiểm thử (Testing Strategy)

#### Unit Tests
Các hàm logic quan trọng cần test.

[Unit Tests]

#### Integration Tests
Test luồng kết nối giữa API và Database.

[Integration Tests]

#### Dành cho AI
Yêu cầu AI tự động viết test script dựa trên các kịch bản này.

[AI Test Generation Guidelines]

## Why TDD is Crucial for AI Agents
- **Consistency:** AI won't mix libraries if locked in TDD.
- **Reduce Hallucination:** Clear schemas prevent invented fields.
- **Optimize Tokens:** Reference TDD.md instead of repeating stack.

## Connection to Business Template
- **USP (Unique Features):** Low-level Design for proprietary algorithms.
- **Guarantees:** Performance & Security to meet commitments (e.g., 99.9% uptime).
- **Deliverables:** API Contracts & Folder Structure for specific modules.
- **Pricing:** Database Schema for subscriptions, plans, and license checks.

## Instructions for Generation
- Fill in each section with detailed, technical content based on the input information.
- Use Mermaid.js for diagrams where applicable.
- Ensure the TDD is implementable and references SRS/PRD.
- If any input is missing, infer reasonable defaults or note placeholders.
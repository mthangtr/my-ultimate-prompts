Bạn là một Domain Expert và Technical Writer chuyên nghiệp. Hãy tạo một bộ Glossary (Từ điển thuật ngữ) và Domain Terminology (Thuật ngữ miền) đầy đủ và chi tiết cho dự án.

Mục tiêu:
1. Định nghĩa rõ ràng tất cả khái niệm trong domain
2. Tránh nhầm lẫn giữa các thuật ngữ tương tự
3. Cung cấp context và relationships giữa các concepts
4. Mapping thuật ngữ với code implementation (class names, database tables, API resources)
5. Đảm bảo consistency trong toàn bộ dự án

### Thông tin Domain:

**Tên dự án/Domain:**
[Tên dự án hoặc lĩnh vực của bạn]

**Mô tả Domain:**
[Mô tả ngắn gọn về lĩnh vực/domain này]

**Ngữ cảnh nghiệp vụ:**
[Mô tả context nghiệp vụ để hiểu các thuật ngữ]

**Các khái niệm chính cần định nghĩa:**
[Liệt kê các terms quan trọng]
Ví dụ:
- Student, Teacher, Academic Staff
- Course, Class, Session, Lesson
- Enrollment, Registration, Application
- Grade, Score, Assessment, Evaluation
- Semester, Term, Academic Year
- Branch, Campus, Department

**Các thuật ngữ dễ nhầm lẫn:**
[Các cặp thuật ngữ thường bị nhầm lẫn]
Ví dụ:
- Course vs Class vs Session
- Student vs Learner vs Participant
- Grade vs Score vs Mark
- Enrollment vs Registration

**Business context đặc thù:**
[Các quy tắc hoặc context đặc biệt của domain]
Ví dụ:
- Trong hệ thống của chúng ta, "Course" là chương trình học tổng thể, "Class" là lớp học cụ thể
- "Session" là một buổi học trong "Class"

---

### Yêu cầu Output:

## 📚 GLOSSARY & DOMAIN TERMINOLOGY

### 1. DOCUMENT INFORMATION

| Field | Value |
|-------|-------|
| Project Name | [Project Name] |
| Domain | [Domain/Industry] |
| Version | 1.0 |
| Last Updated | [Date] |
| Maintained By | [Team/Person] |
| Purpose | Unified terminology reference for all stakeholders |

**Scope:**
- This glossary covers all domain-specific terms used in [project name]
- Terms are defined from business perspective first, then technical mapping
- All team members MUST use these exact terms for consistency

---

### 2. CORE DOMAIN CONCEPTS

#### 2.1 Primary Entities (Thực thể chính)

Các đối tượng nghiệp vụ cốt lõi trong hệ thống.

---

##### **[ENTITY 1]**

**📖 Definition (Định nghĩa):**
[Định nghĩa rõ ràng, đầy đủ]

**🎯 Business Context:**
[Giải thích trong ngữ cảnh nghiệp vụ]

**🔗 Relationships:**
- Related to: [Entity 2], [Entity 3]
- Parent of: [Child entities]
- Contains: [Contained entities]
- References: [Referenced entities]

**📊 Properties/Attributes:**
| Attribute | Type | Required | Description | Example |
|-----------|------|----------|-------------|---------|
| id | UUID | Yes | Unique identifier | "abc-123-xyz" |
| name | String | Yes | Full name | "John Doe" |
| status | Enum | Yes | Current state | "active" |

**🔄 Lifecycle/States:**
```
[Initial State] → [State 2] → [State 3] → [Final State]

Example:
Draft → Submitted → Approved → Active → Completed
```

**💻 Technical Mapping:**
- **Class Name:** `EntityName`
- **Database Table:** `entity_names`
- **API Resource:** `/api/entities` or `/api/entity-names`
- **DTO Name:** `EntityDto`, `CreateEntityDto`, `UpdateEntityDto`

**🆚 NOT to be confused with:**
- **[Similar Term]:** [Explain the difference clearly]

**📝 Examples:**
- Example 1: [Concrete example]
- Example 2: [Concrete example]

**🔤 Synonyms/Aliases:**
- [Alternative term 1]
- [Alternative term 2]

**🌐 Translations:**
- English: [Term]
- Vietnamese: [Thuật ngữ tiếng Việt]
- [Other languages if applicable]

**⚠️ Common Mistakes:**
- ❌ Mistake 1: [What people often get wrong]
- ❌ Mistake 2: [What people often get wrong]
- ✅ Correct usage: [How to use correctly]

**📋 Business Rules:**
- Rule 1: [Business rule involving this entity]
- Rule 2: [Business rule involving this entity]

---

[Repeat above format for all primary entities]

---

#### 2.2 Secondary Concepts (Khái niệm phụ)

Các khái niệm hỗ trợ, không phải entities chính nhưng quan trọng.

---

##### **[CONCEPT 1]**

**📖 Definition:**
[Clear definition]

**🎯 Context:**
[When and how this concept is used]

**💻 Implementation:**
- Could be: Value Object, Enum, Service, Process, State, etc.
- Technical representation: [How it's implemented in code]

**📝 Examples:**
[Concrete examples]

---

### 3. PROCESS & WORKFLOW TERMS

Các thuật ngữ liên quan đến quy trình và workflow.

| Term | Definition | Used In | Example |
|------|------------|---------|---------|
| **[Process 1]** | [Definition] | [Which workflows] | [Example] |
| **[Process 2]** | [Definition] | [Which workflows] | [Example] |

---

### 4. ROLES & ACTORS

Các vai trò trong hệ thống.

---

##### **[ROLE 1]**

**📖 Definition:**
[What this role represents]

**🎯 Responsibilities:**
- Responsibility 1
- Responsibility 2
- Responsibility 3

**🔐 Permissions:**
- Can do: Action 1, Action 2
- Cannot do: Action 3, Action 4

**💻 Technical Mapping:**
- **Enum Value:** `ROLE_NAME`
- **Database:** `roles` table, value: "role_name"
- **Permission Set:** `RoleNamePermissions`

**🆚 Different from:**
- **[Similar Role]:** [Key differences]

---

### 5. STATUS & STATES

Các trạng thái và status trong hệ thống.

#### 5.1 [Entity] Status

| Status | Definition | Can Transition To | Triggered By |
|--------|------------|-------------------|--------------|
| **[STATUS_1]** | [Definition] | [STATUS_2], [STATUS_3] | [Event/Action] |
| **[STATUS_2]** | [Definition] | [STATUS_3], [STATUS_4] | [Event/Action] |

**💻 Technical Implementation:**
```typescript
enum EntityStatus {
  STATUS_1 = 'status_1',
  STATUS_2 = 'status_2',
  STATUS_3 = 'status_3'
}
```

**🔄 State Transition Rules:**
```
STATUS_1 → STATUS_2: Requires [condition]
STATUS_2 → STATUS_3: Requires [condition]
STATUS_3 ↛ STATUS_1: Invalid transition
```

---

### 6. MEASUREMENTS & METRICS

Các đơn vị đo lường và metrics.

| Term | Definition | Unit | Valid Range | Example |
|------|------------|------|-------------|---------|
| **[Metric 1]** | [Definition] | [Unit] | [Min-Max] | [Example] |
| **[Metric 2]** | [Definition] | [Unit] | [Min-Max] | [Example] |

---

### 7. TIME-RELATED TERMS

Các thuật ngữ liên quan đến thời gian.

| Term | Definition | Duration | Contains | Example |
|------|------------|----------|----------|---------|
| **[Time Unit 1]** | [Definition] | [Duration] | [Sub-units] | [Example] |
| **[Time Unit 2]** | [Definition] | [Duration] | [Sub-units] | [Example] |

**Example Hierarchy:**
```
Academic Year (12 months)
  ├── Semester 1 (4 months)
  │     ├── Month 1
  │     ├── Month 2
  │     ├── Month 3
  │     └── Month 4
  ├── Semester 2 (4 months)
  └── Summer Term (4 months)
```

---

### 8. DISAMBIGUATION (Phân biệt các thuật ngữ dễ nhầm)

#### 8.1 [Term A] vs [Term B] vs [Term C]

| Aspect | Term A | Term B | Term C |
|--------|--------|--------|--------|
| **Definition** | [Def A] | [Def B] | [Def C] |
| **Scope** | [Scope A] | [Scope B] | [Scope C] |
| **Duration** | [Duration A] | [Duration B] | [Duration C] |
| **Example** | [Example A] | [Example B] | [Example C] |
| **In Code** | `ClassA` | `ClassB` | `ClassC` |
| **In Database** | `table_a` | `table_b` | `table_c` |
| **In API** | `/api/a` | `/api/b` | `/api/c` |

**When to use which:**
- Use **Term A** when: [Scenario]
- Use **Term B** when: [Scenario]
- Use **Term C** when: [Scenario]

**Visual Relationship:**
```
[ASCII diagram showing relationship]
```

---

### 9. ACRONYMS & ABBREVIATIONS

| Acronym | Full Form | Definition | Usage |
|---------|-----------|------------|-------|
| **[ABC]** | [Full name] | [Definition] | [When to use] |
| **[XYZ]** | [Full name] | [Definition] | [When to use] |

**⚠️ Note:** Always use full form on first mention, then acronym.

---

### 10. DOMAIN-SPECIFIC RULES & CONSTRAINTS

#### 10.1 Naming Conventions

**Entities:**
- Use singular form: `User`, not `Users`
- PascalCase for class names: `AcademicStaff`
- snake_case for database: `academic_staff`
- kebab-case for URLs: `/academic-staff`

**Relationships:**
- One-to-Many: Use plural: `course.classes[]`
- Many-to-One: Use singular: `class.course`
- Many-to-Many: Use plural: `student.courses[]`

**Status/State:**
- Use adjectives or past participles: `active`, `completed`, `pending`
- Not verbs: ❌ `activating`, ❌ `complete`

#### 10.2 Data Type Conventions

| Domain Concept | Data Type | Format | Example |
|----------------|-----------|--------|---------|
| IDs | UUID | UUID v4 | "550e8400-e29b-41d4-a716-446655440000" |
| Dates | ISO 8601 | YYYY-MM-DD | "2025-10-29" |
| DateTime | ISO 8601 | YYYY-MM-DDTHH:mm:ssZ | "2025-10-29T14:30:00Z" |
| Currency | Decimal | 2 decimal places | 1234.56 |
| Percentage | Integer | 0-100 | 85 |

---

### 11. RELATIONSHIP DIAGRAM

```
Tạo diagram thể hiện mối quan hệ giữa các entities chính:

┌─────────────┐         ┌─────────────┐
│   Entity A  │────────>│   Entity B  │
│             │1       *│             │
└─────────────┘         └─────────────┘
       │                       │
       │                       │
       │*                     1│
       ▼                       ▼
┌─────────────┐         ┌─────────────┐
│   Entity C  │         │   Entity D  │
│             │         │             │
└─────────────┘         └─────────────┘

Legend:
1    : One
*    : Many
───> : Has relationship
```

---

### 12. CODE IMPLEMENTATION REFERENCE

#### 12.1 Entity Naming Matrix

| Business Term | TypeScript Class | Database Table | API Endpoint | GraphQL Type |
|---------------|------------------|----------------|--------------|--------------|
| [Term 1] | `Term1` | `term1s` | `/api/term1s` | `Term1` |
| [Term 2] | `Term2` | `term2s` | `/api/term2s` | `Term2` |

#### 12.2 Enum Definitions

```typescript
// [Category] Enums

// [Enum 1]
enum EntityStatus {
  VALUE_1 = 'value_1',
  VALUE_2 = 'value_2',
  VALUE_3 = 'value_3'
}

// [Enum 2]
enum EntityType {
  TYPE_A = 'type_a',
  TYPE_B = 'type_b'
}
```

#### 12.3 Type Aliases

```typescript
// Domain-specific type aliases
type EntityID = string;  // UUID
type Timestamp = Date;   // ISO 8601
type Percentage = number; // 0-100
type Currency = number;   // Decimal with 2 places
```

---

### 13. VALIDATION RULES BY TERM

| Term | Validation Rules | Error Messages |
|------|------------------|----------------|
| **[Term 1]** | - Min length: X<br>- Max length: Y<br>- Pattern: [regex] | "Invalid [term]: [reason]" |
| **[Term 2]** | - Required<br>- Must be unique<br>- Must exist in [table] | "Invalid [term]: [reason]" |

---

### 14. LOCALIZATION (i18n)

#### 14.1 Term Translations

| English | Vietnamese | Notes |
|---------|------------|-------|
| [Term 1] | [Thuật ngữ 1] | [Context notes] |
| [Term 2] | [Thuật ngữ 2] | [Context notes] |

#### 14.2 UI Display Names

```json
{
  "en": {
    "term1": "Term 1",
    "term1_plural": "Term 1s",
    "term1_description": "Description of term 1"
  },
  "vi": {
    "term1": "Thuật ngữ 1",
    "term1_plural": "Các thuật ngữ 1",
    "term1_description": "Mô tả thuật ngữ 1"
  }
}
```

---

### 15. GLOSSARY INDEX (A-Z)

Quick reference index:

**A**
- [Term starting with A]: See section X.Y

**B**
- [Term starting with B]: See section X.Y

[... continue for all letters ...]

---

### 16. DEPRECATED TERMS

| Old Term | New Term | Deprecated Since | Remove By | Migration Guide |
|----------|----------|------------------|-----------|-----------------|
| [Old] | [New] | [Date] | [Date] | [Link/Description] |

**Migration Instructions:**
- Replace all instances of [Old Term] with [New Term]
- Update database column names: `old_term` → `new_term`
- Update API endpoints: `/api/old-terms` → `/api/new-terms`

---

### 17. EXTERNAL REFERENCES

| External System | Their Term | Our Term | Mapping Notes |
|-----------------|------------|----------|---------------|
| [System 1] | [Their term] | [Our term] | [How to map] |
| [System 2] | [Their term] | [Our term] | [How to map] |

---

### 18. DECISION LOG

Document why certain terminology was chosen:

#### Decision 1: Why we use "[Term A]" instead of "[Term B]"

**Date:** [Date]
**Decided by:** [Team/Person]
**Rationale:**
- Reason 1
- Reason 2
- Industry standard: [Reference]

**Alternatives considered:**
- [Alternative 1]: Rejected because [reason]
- [Alternative 2]: Rejected because [reason]

---

### 19. USAGE EXAMPLES IN CONTEXT

#### Scenario 1: [Use Case Name]

**Narrative:**
[Story using the terms correctly]

**Terms used:**
- **[Term 1]**: Used to represent [...]
- **[Term 2]**: Used to represent [...]

**Code example:**
```typescript
// Example showing correct usage of terms
const student = new Student({ name: "John" });
const course = new Course({ title: "Math 101" });
const enrollment = student.enrollIn(course);
```

---

### 20. COMPLIANCE & STANDARDS

| Standard/Regulation | Relevant Terms | Requirements |
|---------------------|----------------|--------------|
| [Standard 1] | [Terms] | [Compliance requirements] |
| [Regulation 1] | [Terms] | [Legal requirements] |

---

### 📋 MAINTENANCE GUIDELINES

**This glossary should be updated when:**
- [ ] New domain concepts are introduced
- [ ] Terms are deprecated or renamed
- [ ] Business rules change
- [ ] Technical implementation changes
- [ ] External integrations add new terms

**Review schedule:**
- Monthly: Quick review for additions
- Quarterly: Full review and cleanup
- Annually: Major revision

**Change process:**
1. Propose change via [process]
2. Review with domain experts
3. Update glossary
4. Notify all stakeholders
5. Update related documentation
6. Update code if needed

---

### 🎯 FOR DEVELOPERS

**When writing code:**
- ✅ Always use terms exactly as defined here
- ✅ Check this glossary when unsure
- ✅ Propose updates when introducing new concepts
- ❌ Don't invent your own terms
- ❌ Don't use synonyms inconsistently

**When reviewing code:**
- ✅ Verify terminology matches glossary
- ✅ Flag inconsistent usage
- ✅ Suggest corrections

**When writing documentation:**
- ✅ Link to this glossary
- ✅ Use defined terms
- ✅ Maintain consistency

---

## 💡 Hướng dẫn sử dụng

### Bước 1: Thu thập thông tin
- Liệt kê tất cả các entities/concepts trong domain
- Xác định các thuật ngữ dễ nhầm lẫn
- Tìm hiểu business rules liên quan
- Xác định relationships giữa các concepts

### Bước 2: Điền vào prompt
- Copy prompt template
- Điền đầy đủ thông tin domain
- Liệt kê càng nhiều terms càng tốt
- Cung cấp context và examples

### Bước 3: Generate và Review
- Paste vào coding agent
- Review output kỹ lưỡng
- Verify với domain experts
- Refine và iterate

### Bước 4: Maintain
- Version control
- Regular updates
- Share với toàn bộ team
- Enforce usage trong code reviews

---

## ✅ Checklist trước khi sử dụng

- [ ] Đã liệt kê tất cả core entities
- [ ] Đã xác định các thuật ngữ dễ nhầm lẫn
- [ ] Đã có business context đầy đủ
- [ ] Đã xác định relationships giữa các concepts
- [ ] Đã biết tech stack để mapping (class names, tables, etc.)
- [ ] Đã có examples cụ thể
- [ ] Đã có domain expert review (nếu có)

---

## 🎨 Tips tạo Glossary hiệu quả

### 1. **Clarity over Brevity**
- Định nghĩa phải rõ ràng, đầy đủ
- Đừng ngại viết dài nếu cần
- Include examples

### 2. **Be Prescriptive**
- Nói rõ PHẢI dùng term nào
- Chỉ ra các term KHÔNG nên dùng
- Show correct vs incorrect usage

### 3. **Show Relationships**
- Dùng diagrams
- Liệt kê relationships
- Explain hierarchies

### 4. **Technical Mapping is Critical**
- Map mọi term sang code
- Include class names, table names, API endpoints
- Show enum values

### 5. **Disambiguate Aggressively**
- Tạo comparison tables
- Explain differences clearly
- Provide usage guidelines

### 6. **Think About Non-Technical Users**
- Business definitions trước
- Technical mapping sau
- Avoid jargon in definitions

### 7. **Make it Searchable**
- Create index
- Use consistent formatting
- Include synonyms and aliases

### 8. **Keep it Living**
- Version control
- Regular updates
- Change log
- Deprecation process

---

## 📌 Ví dụ: Education Domain

<details>
<summary>Xem ví dụ đầy đủ cho hệ thống giáo dục</summary>

```
Bạn là một Domain Expert và Technical Writer chuyên nghiệp. Hãy tạo một bộ Glossary và Domain Terminology đầy đủ và chi tiết cho dự án.

### Thông tin Domain:

**Tên dự án/Domain:**
Education Management System - Hệ thống Quản lý Giáo dục

**Mô tả Domain:**
Hệ thống quản lý toàn bộ hoạt động giáo dục từ tuyển sinh, đào tạo, đến cấp bằng. Bao gồm quản lý sinh viên, giáo viên, khóa học, lớp học, lịch học, điểm số, và học phí.

**Ngữ cảnh nghiệp vụ:**
- Hệ thống phục vụ các trường đại học và cao đẳng
- Mô hình tín chỉ (credit-based system)
- Có nhiều campus/chi nhánh
- Hỗ trợ cả học trực tuyến và offline
- Năm học chia thành 3 kỳ: Fall, Spring, Summer

**Các khái niệm chính:**

1. **Organizational Structure:**
   - University, Campus, Branch, Faculty, Department

2. **People:**
   - Student, Teacher, Instructor, Professor, Academic Staff, Admin

3. **Academic Structure:**
   - Course, Class, Section, Session, Lesson, Module

4. **Time:**
   - Academic Year, Semester, Term, Quarter, Week, Session

5. **Registration:**
   - Application, Enrollment, Registration, Admission

6. **Assessment:**
   - Grade, Score, Mark, Point, GPA, Credit

7. **Financial:**
   - Tuition Fee, Course Fee, Payment, Invoice, Receipt

**Các thuật ngữ dễ nhầm lẫn:**

1. **Course vs Class vs Session:**
   - Course = chương trình học (Math 101)
   - Class = lớp học cụ thể (Math 101 - Section A)
   - Session = buổi học trong Class (Monday 8-10am)

2. **Student vs Learner:**
   - Student = đã enrolled chính thức
   - Learner = đang học (có thể chưa enrolled)

3. **Grade vs Score vs Mark:**
   - Score = điểm số (85/100)
   - Grade = xếp loại (A, B, C)
   - Mark = có thể là Score hoặc Grade tùy context

4. **Enrollment vs Registration:**
   - Registration = đăng ký ý định học
   - Enrollment = đã được chấp nhận và enrolled chính thức

5. **Semester vs Term:**
   - Semester = kỳ học chính (Fall/Spring) - 15-16 tuần
   - Term = có thể là semester hoặc summer term - khái niệm chung hơn

6. **Professor vs Teacher vs Instructor:**
   - Professor = chức danh học thuật (Assistant/Associate/Full Professor)
   - Teacher = người dạy (general term)
   - Instructor = người hướng dẫn (có thể không phải Professor)

**Business Context đặc thù:**

- Trong hệ thống này:
  - 1 Course có thể có nhiều Classes trong cùng một kỳ
  - 1 Class có thể có nhiều Sessions (các buổi học)
  - 1 Student có thể enroll nhiều Classes trong 1 Semester
  - 1 Teacher có thể teach nhiều Classes
  - Mỗi Class có 1 Primary Teacher và có thể có nhiều Assistant Teachers

- Credit System:
  - 1 Credit = 15 giờ học lý thuyết hoặc 30 giờ thực hành
  - Minimum 12 credits/semester để là full-time student
  - Maximum 24 credits/semester

- Grading:
  - Numeric Score: 0-100
  - Letter Grade: A (90-100), B (80-89), C (70-79), D (60-69), F (<60)
  - GPA Scale: 4.0

[... phần yêu cầu output như template ...]
```

</details>

---

## 🔄 Integration với documents khác

**Glossary là foundation cho:**
- ✅ **PRD**: Use consistent terms trong requirements
- ✅ **Business Flow**: Actors và entities được định nghĩa rõ
- ✅ **API Documentation**: Resource names match glossary
- ✅ **Database Schema**: Table names follow glossary
- ✅ **Code**: Class names, variables follow glossary
- ✅ **Test Cases**: Test descriptions use correct terms

**Best practice:**
1. Tạo Glossary TRƯỚC khi viết PRD
2. Reference Glossary trong mọi documents
3. Enforce trong code reviews
4. Update glossary khi domain evolves

---

## 📚 Why Glossary Matters

### ❌ Without Glossary:
```typescript
// Developer A
class CourseClass { }

// Developer B  
class ClassSession { }

// Developer C
class Course { }

// → Confusion! What's what?
```

### ✅ With Glossary:
```typescript
// Everyone follows glossary
class Course { }        // As defined in glossary
class Class { }         // As defined in glossary  
class Session { }       // As defined in glossary

// → Clear! Consistent! Maintainable!
```

---

## 🎯 For AI/Coding Agents

Khi cung cấp glossary cho AI coding agent:

**Benefits:**
- ✅ Agent hiểu chính xác domain concepts
- ✅ Generate code với naming consistency
- ✅ Tránh nhầm lẫn thuật ngữ
- ✅ Better context cho code generation
- ✅ More accurate parsing của requirements

**How to use:**
1. Share glossary trước khi ask agent code
2. Reference specific terms khi give instructions
3. Ask agent verify term usage
4. Use glossary to review generated code

---

**Version:** 1.0  
**Last Updated:** October 29, 2025  
**Maintainer:** Product & Engineering Team  
**Related:** prd-generator.md, business-flow-generator.md

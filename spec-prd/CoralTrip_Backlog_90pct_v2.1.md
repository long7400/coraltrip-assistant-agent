# CoralTrip Assistant Agent — Full Backlog v2.1 (90% Coverage)

> **Model:** Không chia MVP. Delivery theo capability + user-story completion gate.  
> **Vai trò:** BA/Leader backlog pack để Product, Architect, Dev, QA, SRE, Security cùng dùng.  
> **Generated:** 2026-07-03 16:03 Asia/Ho_Chi_Minh.

## 1. Coverage summary

- **Capabilities:** 18
- **Epics:** 64
- **User stories:** 247
- **Tickets/tasks:** 1197
- **Coverage target:** khoảng 90% dự án full-scope; 10% còn lại sẽ phát sinh sau discovery, supplier contract, legal/payment review và UI prototype.

## 2. Priority model

| Priority | Meaning |
|---|---|
| P0 | Bắt buộc cho trust, money, legal, high-load, core flow. Không go-live nếu thiếu. |
| P1 | Hoàn thiện sản phẩm cốt lõi, B2B, supplier workflow, analytics cơ bản. |
| P2 | Optimization, growth, personalization, mobile/PWA, loyalty, reviews. |
| P3 | Optional hoặc phụ thuộc partner/contract. |

## 3. Completion gates

- **Product** — User story, flow, field list, UX states, copy, AC and edge cases are clear. Evidence: Story spec, wireframe, AC, examples.
- **Domain** — Aggregate, invariant, state transition, policy snapshot and domain event are defined. Evidence: Domain model, state machine, ADR if needed.
- **Technical** — API/schema/cache/concurrency/idempotency/migration/backward compatibility are designed. Evidence: OpenAPI, ERD, migration, sequence diagram.
- **Security/Privacy** — Auth/authz, PII, audit, consent, abuse, secrets and compliance risks are addressed. Evidence: Threat model, ASVS/Privacy checklist.
- **AI** — Prompt, tool schema, RAG source, eval dataset, hallucination and injection controls defined. Evidence: Eval run, golden set, tool policy.
- **Observability/Ops** — Metrics/logs/traces/alerts/runbook/manual override and rollback are ready. Evidence: Grafana/alert links, runbook.
- **QA** — Unit, integration, contract, E2E, negative, load/security/AI tests as relevant pass. Evidence: CI test report, test evidence.

## 4. Full hierarchy: capability → epic → user story → tickets


# CAP01 — Product Governance & Delivery Model

**Owner:** Product Lead / BA Lead

## CT-E001 — Product operating model

**Objective:** Thiết lập cách quản trị backlog không dùng MVP, release theo completion gate và user-story readiness.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0001 — Là BA Lead, tôi muốn quản lý backlog theo capability, epic, user story, ticket và dependency để team có thể giao việc mà không bị lẫn scope.

- **Priority:** P0
- **Tags:** BA, Governance
- **Acceptance criteria:** Given BA Lead có quyền hợp lệ; When quản lý backlog theo capability, epic, user story, ticket và dependency; Then kết quả giúp team có thể giao việc mà không bị lẫn scope; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0001` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — quản lý backlog theo capability, epic, user story, ticket và...  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0002` **QA** — QA: Test plan và automated tests — quản lý backlog theo capability, epic, user story, ticket và...  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0002 — Là Product Lead, tôi muốn định nghĩa completion gates thay cho phase MVP/v1/v2 để release chỉ diễn ra khi story đạt đủ product, tech, security, ops.

- **Priority:** P0
- **Tags:** BA, Governance, QA
- **Acceptance criteria:** Given Product Lead có quyền hợp lệ; When định nghĩa completion gates thay cho phase MVP/v1/v2; Then kết quả giúp release chỉ diễn ra khi story đạt đủ product, tech, security, ops; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0003` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — định nghĩa completion gates thay cho phase MVP/v1/v2  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0004` **QA** — QA: Test plan và automated tests — định nghĩa completion gates thay cho phase MVP/v1/v2  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0003 — Là Stakeholder, tôi muốn xem roadmap theo capability maturity để hiểu cái gì đã đủ để go-live từng mảng.

- **Priority:** P0
- **Tags:** BA, Roadmap
- **Acceptance criteria:** Given Stakeholder có quyền hợp lệ; When xem roadmap theo capability maturity; Then kết quả giúp hiểu cái gì đã đủ để go-live từng mảng; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0005` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem roadmap theo capability maturity  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0006` **QA** — QA: Test plan và automated tests — xem roadmap theo capability maturity  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0004 — Là BA Lead, tôi muốn chuẩn hóa DoR/DoD cho mọi ticket để ticket vào sprint rõ đầu vào và đầu ra.

- **Priority:** P0
- **Tags:** BA, QA
- **Acceptance criteria:** Given BA Lead có quyền hợp lệ; When chuẩn hóa DoR/DoD cho mọi ticket; Then kết quả giúp ticket vào sprint rõ đầu vào và đầu ra; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0007` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — chuẩn hóa DoR/DoD cho mọi ticket  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0008` **QA** — QA: Test plan và automated tests — chuẩn hóa DoR/DoD cho mọi ticket  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E002 — Research, verification & decision register

**Objective:** Bảo vệ các giả định sản phẩm/kỹ thuật bằng nguồn, ADR và assumption log.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0005 — Là Product Lead, tôi muốn duy trì source verification register cho market, API, legal và technical claims để không đưa claim thiếu nguồn vào tài liệu.

- **Priority:** P0
- **Tags:** BA, Research
- **Acceptance criteria:** Given Product Lead có quyền hợp lệ; When duy trì source verification register cho market, API, legal và technical claims; Then kết quả giúp không đưa claim thiếu nguồn vào tài liệu; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0009` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — duy trì source verification register cho market, API, legal và...  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0010` **QA** — QA: Test plan và automated tests — duy trì source verification register cho market, API, legal và...  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0006 — Là Architect, tôi muốn ghi ADR cho các quyết định lớn như supplier adapter, MCP, payment scope để quyết định có lý do và có lịch sử.

- **Priority:** P0
- **Tags:** Architecture, BA
- **Acceptance criteria:** Given Architect có quyền hợp lệ; When ghi ADR cho các quyết định lớn như supplier adapter, MCP, payment scope; Then kết quả giúp quyết định có lý do và có lịch sử; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0011` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — ghi ADR cho các quyết định lớn như supplier adapter, MCP, payment...  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0012` **QA** — QA: Test plan và automated tests — ghi ADR cho các quyết định lớn như supplier adapter, MCP, payment...  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0007 — Là Finance Lead, tôi muốn ghi assumption log cho take rate, gateway fee, CAC và refund rate để unit economics không bị ngầm định sai.

- **Priority:** P0
- **Tags:** Finance, BA
- **Acceptance criteria:** Given Finance Lead có quyền hợp lệ; When ghi assumption log cho take rate, gateway fee, CAC và refund rate; Then kết quả giúp unit economics không bị ngầm định sai; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0013` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — ghi assumption log cho take rate, gateway fee, CAC và refund rate  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0014` **Data** — Data: Event taxonomy/data model/dashboard metric — ghi assumption log cho take rate, gateway fee, CAC và refund rate  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0015` **QA** — QA: Test plan và automated tests — ghi assumption log cho take rate, gateway fee, CAC và refund rate  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP02 — Identity, Auth, Organization & Consent

**Owner:** Identity Lead

## CT-E003 — Consumer identity & account security

**Objective:** Cho phép traveller đăng ký/đăng nhập an toàn bằng email/phone/social và quản lý session.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0008 — Là Traveller, tôi muốn đăng ký bằng email hoặc số điện thoại với OTP để tạo tài khoản nhanh và an toàn.

- **Priority:** P0
- **Tags:** Auth, FE, BE, Security
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When đăng ký bằng email hoặc số điện thoại với OTP; Then kết quả giúp tạo tài khoản nhanh và an toàn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy. NFR: OTP rate limit; p95 auth API <300ms.
- **NFR/SLO:** OTP rate limit; p95 auth API <300ms
- **Tickets:**
  - `CT-T0016` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — đăng ký bằng email hoặc số điện thoại với OTP  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0017` **UX** — UX: Thiết kế wireframe/UI states — đăng ký bằng email hoặc số điện thoại với OTP  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0018` **FE** — FE: Implement UI và client integration — đăng ký bằng email hoặc số điện thoại với OTP  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0019` **BE** — BE: Thiết kế domain/API/schema và implement service — đăng ký bằng email hoặc số điện thoại với OTP  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0020` **Security** — Security: Threat model và security control — đăng ký bằng email hoặc số điện thoại với OTP  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0021` **QA** — QA: Test plan và automated tests — đăng ký bằng email hoặc số điện thoại với OTP  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0009 — Là Traveller, tôi muốn đăng nhập, refresh token và logout khỏi mọi thiết bị để kiểm soát session cá nhân.

- **Priority:** P0
- **Tags:** Auth, FE, BE, Security
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When đăng nhập, refresh token và logout khỏi mọi thiết bị; Then kết quả giúp kiểm soát session cá nhân; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0022` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — đăng nhập, refresh token và logout khỏi mọi thiết bị  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0023` **UX** — UX: Thiết kế wireframe/UI states — đăng nhập, refresh token và logout khỏi mọi thiết bị  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0024` **FE** — FE: Implement UI và client integration — đăng nhập, refresh token và logout khỏi mọi thiết bị  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0025` **BE** — BE: Thiết kế domain/API/schema và implement service — đăng nhập, refresh token và logout khỏi mọi thiết bị  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0026` **Security** — Security: Threat model và security control — đăng nhập, refresh token và logout khỏi mọi thiết bị  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0027` **QA** — QA: Test plan và automated tests — đăng nhập, refresh token và logout khỏi mọi thiết bị  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0010 — Là Traveller, tôi muốn khôi phục mật khẩu hoặc đổi phương thức xác thực để không mất quyền truy cập tài khoản.

- **Priority:** P1
- **Tags:** Auth, FE, BE, Security
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When khôi phục mật khẩu hoặc đổi phương thức xác thực; Then kết quả giúp không mất quyền truy cập tài khoản; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0028` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — khôi phục mật khẩu hoặc đổi phương thức xác thực  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0029` **UX** — UX: Thiết kế wireframe/UI states — khôi phục mật khẩu hoặc đổi phương thức xác thực  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0030` **FE** — FE: Implement UI và client integration — khôi phục mật khẩu hoặc đổi phương thức xác thực  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0031` **BE** — BE: Thiết kế domain/API/schema và implement service — khôi phục mật khẩu hoặc đổi phương thức xác thực  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0032` **Security** — Security: Threat model và security control — khôi phục mật khẩu hoặc đổi phương thức xác thực  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0033` **QA** — QA: Test plan và automated tests — khôi phục mật khẩu hoặc đổi phương thức xác thực  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0011 — Là Security Admin, tôi muốn áp dụng brute-force protection và risk-based throttling để giảm tấn công credential stuffing.

- **Priority:** P0
- **Tags:** Auth, Security, SRE
- **Acceptance criteria:** Given Security Admin có quyền hợp lệ; When áp dụng brute-force protection và risk-based throttling; Then kết quả giúp giảm tấn công credential stuffing; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0034` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — áp dụng brute-force protection và risk-based throttling  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0035` **BE** — BE: Thiết kế domain/API/schema và implement service — áp dụng brute-force protection và risk-based throttling  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0036` **Security** — Security: Threat model và security control — áp dụng brute-force protection và risk-based throttling  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0037` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — áp dụng brute-force protection và risk-based throttling  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0038` **QA** — QA: Test plan và automated tests — áp dụng brute-force protection và risk-based throttling  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E004 — Organization, roles & permissions

**Objective:** Quản lý nhiều loại chủ thể: traveller, agent org, tour operator, admin, finance, support.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0012 — Là Organization Admin, tôi muốn tạo tổ chức agent/operator và mời thành viên để team có workspace riêng.

- **Priority:** P0
- **Tags:** Org, RBAC, FE, BE
- **Acceptance criteria:** Given Organization Admin có quyền hợp lệ; When tạo tổ chức agent/operator và mời thành viên; Then kết quả giúp team có workspace riêng; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0039` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tạo tổ chức agent/operator và mời thành viên  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0040` **UX** — UX: Thiết kế wireframe/UI states — tạo tổ chức agent/operator và mời thành viên  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0041` **FE** — FE: Implement UI và client integration — tạo tổ chức agent/operator và mời thành viên  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0042` **BE** — BE: Thiết kế domain/API/schema và implement service — tạo tổ chức agent/operator và mời thành viên  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0043` **Security** — Security: Threat model và security control — tạo tổ chức agent/operator và mời thành viên  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0044` **QA** — QA: Test plan và automated tests — tạo tổ chức agent/operator và mời thành viên  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0013 — Là Organization Admin, tôi muốn phân quyền theo role và scope dữ liệu để nhân sự chỉ thấy dữ liệu được phép.

- **Priority:** P0
- **Tags:** RBAC, Security, BE
- **Acceptance criteria:** Given Organization Admin có quyền hợp lệ; When phân quyền theo role và scope dữ liệu; Then kết quả giúp nhân sự chỉ thấy dữ liệu được phép; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0045` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — phân quyền theo role và scope dữ liệu  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0046` **BE** — BE: Thiết kế domain/API/schema và implement service — phân quyền theo role và scope dữ liệu  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0047` **Security** — Security: Threat model và security control — phân quyền theo role và scope dữ liệu  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0048` **QA** — QA: Test plan và automated tests — phân quyền theo role và scope dữ liệu  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0014 — Là Admin, tôi muốn xem lịch sử thay đổi role/permission để truy vết khi có sự cố phân quyền.

- **Priority:** P0
- **Tags:** Audit, Security, BE
- **Acceptance criteria:** Given Admin có quyền hợp lệ; When xem lịch sử thay đổi role/permission; Then kết quả giúp truy vết khi có sự cố phân quyền; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0049` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem lịch sử thay đổi role/permission  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0050` **BE** — BE: Thiết kế domain/API/schema và implement service — xem lịch sử thay đổi role/permission  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0051` **Security** — Security: Threat model và security control — xem lịch sử thay đổi role/permission  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0052` **QA** — QA: Test plan và automated tests — xem lịch sử thay đổi role/permission  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0015 — Là Agent Manager, tôi muốn tạm khóa tài khoản nhân viên rời công ty để ngăn truy cập sau khi offboarding.

- **Priority:** P1
- **Tags:** RBAC, FE, BE
- **Acceptance criteria:** Given Agent Manager có quyền hợp lệ; When tạm khóa tài khoản nhân viên rời công ty; Then kết quả giúp ngăn truy cập sau khi offboarding; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0053` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tạm khóa tài khoản nhân viên rời công ty  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0054` **UX** — UX: Thiết kế wireframe/UI states — tạm khóa tài khoản nhân viên rời công ty  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0055` **FE** — FE: Implement UI và client integration — tạm khóa tài khoản nhân viên rời công ty  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0056` **BE** — BE: Thiết kế domain/API/schema và implement service — tạm khóa tài khoản nhân viên rời công ty  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0057` **Security** — Security: Threat model và security control — tạm khóa tài khoản nhân viên rời công ty  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0058` **QA** — QA: Test plan và automated tests — tạm khóa tài khoản nhân viên rời công ty  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E005 — Consent, privacy profile & data subject requests

**Objective:** Thu thập/thu hồi consent và xử lý yêu cầu dữ liệu cá nhân đúng luật.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0016 — Là Traveller, tôi muốn xem và chấp thuận consent theo từng purpose để biết dữ liệu dùng để làm gì.

- **Priority:** P0
- **Tags:** Privacy, Legal, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When xem và chấp thuận consent theo từng purpose; Then kết quả giúp biết dữ liệu dùng để làm gì; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0059` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem và chấp thuận consent theo từng purpose  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0060` **UX** — UX: Thiết kế wireframe/UI states — xem và chấp thuận consent theo từng purpose  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0061` **FE** — FE: Implement UI và client integration — xem và chấp thuận consent theo từng purpose  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0062` **BE** — BE: Thiết kế domain/API/schema và implement service — xem và chấp thuận consent theo từng purpose  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0063` **Security** — Security: Threat model và security control — xem và chấp thuận consent theo từng purpose  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0064` **QA** — QA: Test plan và automated tests — xem và chấp thuận consent theo từng purpose  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0017 — Là Traveller, tôi muốn thu hồi consent optional như personalization/marketing để kiểm soát quyền riêng tư.

- **Priority:** P0
- **Tags:** Privacy, Legal, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When thu hồi consent optional như personalization/marketing; Then kết quả giúp kiểm soát quyền riêng tư; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0065` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — thu hồi consent optional như personalization/marketing  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0066` **UX** — UX: Thiết kế wireframe/UI states — thu hồi consent optional như personalization/marketing  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0067` **FE** — FE: Implement UI và client integration — thu hồi consent optional như personalization/marketing  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0068` **BE** — BE: Thiết kế domain/API/schema và implement service — thu hồi consent optional như personalization/marketing  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0069` **Security** — Security: Threat model và security control — thu hồi consent optional như personalization/marketing  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0070` **QA** — QA: Test plan và automated tests — thu hồi consent optional như personalization/marketing  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0018 — Là Compliance Officer, tôi muốn xử lý yêu cầu access/correct/delete/anonymize để đáp ứng DSR có audit trail.

- **Priority:** P0
- **Tags:** Privacy, Legal, BE, Ops
- **Acceptance criteria:** Given Compliance Officer có quyền hợp lệ; When xử lý yêu cầu access/correct/delete/anonymize; Then kết quả giúp đáp ứng DSR có audit trail; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy. NFR: 72h handling workflow where legally applicable.
- **NFR/SLO:** 72h handling workflow where legally applicable
- **Tickets:**
  - `CT-T0071` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xử lý yêu cầu access/correct/delete/anonymize  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0072` **BE** — BE: Thiết kế domain/API/schema và implement service — xử lý yêu cầu access/correct/delete/anonymize  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0073` **Security** — Security: Threat model và security control — xử lý yêu cầu access/correct/delete/anonymize  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0074` **QA** — QA: Test plan và automated tests — xử lý yêu cầu access/correct/delete/anonymize  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0019 — Là Compliance Officer, tôi muốn phân loại PII và áp retention policy để dữ liệu không lưu quá mục đích.

- **Priority:** P0
- **Tags:** Privacy, Data, BE
- **Acceptance criteria:** Given Compliance Officer có quyền hợp lệ; When phân loại PII và áp retention policy; Then kết quả giúp dữ liệu không lưu quá mục đích; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0075` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — phân loại PII và áp retention policy  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0076` **BE** — BE: Thiết kế domain/API/schema và implement service — phân loại PII và áp retention policy  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0077` **Security** — Security: Threat model và security control — phân loại PII và áp retention policy  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0078` **Data** — Data: Event taxonomy/data model/dashboard metric — phân loại PII và áp retention policy  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0079` **QA** — QA: Test plan và automated tests — phân loại PII và áp retention policy  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP03 — Traveller Discovery, Search & Tour UX

**Owner:** Traveller Experience Lead

## CT-E006 — Explore homepage & destination discovery

**Objective:** Tạo entry point để người dùng khám phá tour, điểm đến và campaign.  
**Priority:** P1  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0020 — Là Traveller, tôi muốn xem trang chủ với tour nổi bật, điểm đến và campaign để bắt đầu hành trình tìm kiếm dễ dàng.

- **Priority:** P1
- **Tags:** FE, CMS, Analytics
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When xem trang chủ với tour nổi bật, điểm đến và campaign; Then kết quả giúp bắt đầu hành trình tìm kiếm dễ dàng; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0080` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem trang chủ với tour nổi bật, điểm đến và campaign  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0081` **UX** — UX: Thiết kế wireframe/UI states — xem trang chủ với tour nổi bật, điểm đến và campaign  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0082` **FE** — FE: Implement UI và client integration — xem trang chủ với tour nổi bật, điểm đến và campaign  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0083` **BE** — BE: Thiết kế domain/API/schema và implement service — xem trang chủ với tour nổi bật, điểm đến và campaign  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0084` **Data** — Data: Event taxonomy/data model/dashboard metric — xem trang chủ với tour nổi bật, điểm đến và campaign  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0085` **QA** — QA: Test plan và automated tests — xem trang chủ với tour nổi bật, điểm đến và campaign  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0021 — Là Traveller, tôi muốn lọc nhanh theo theme như gia đình, nghỉ dưỡng, mạo hiểm, cao tuổi để tìm đúng nhu cầu nhanh hơn.

- **Priority:** P1
- **Tags:** FE, Search, Analytics
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When lọc nhanh theo theme như gia đình, nghỉ dưỡng, mạo hiểm, cao tuổi; Then kết quả giúp tìm đúng nhu cầu nhanh hơn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0086` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — lọc nhanh theo theme như gia đình, nghỉ dưỡng, mạo hiểm, cao tuổi  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0087` **UX** — UX: Thiết kế wireframe/UI states — lọc nhanh theo theme như gia đình, nghỉ dưỡng, mạo hiểm, cao tuổi  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0088` **FE** — FE: Implement UI và client integration — lọc nhanh theo theme như gia đình, nghỉ dưỡng, mạo hiểm, cao tuổi  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0089` **BE** — BE: Thiết kế domain/API/schema và implement service — lọc nhanh theo theme như gia đình, nghỉ dưỡng, mạo hiểm, cao tuổi  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0090` **Data** — Data: Event taxonomy/data model/dashboard metric — lọc nhanh theo theme như gia đình, nghỉ dưỡng, mạo hiểm, cao tuổi  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0091` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — lọc nhanh theo theme như gia đình, nghỉ dưỡng, mạo hiểm, cao tuổi  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0092` **QA** — QA: Test plan và automated tests — lọc nhanh theo theme như gia đình, nghỉ dưỡng, mạo hiểm, cao tuổi  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0022 — Là Growth, tôi muốn cấu hình block nội dung homepage từ CMS để không cần deploy khi đổi campaign.

- **Priority:** P1
- **Tags:** CMS, FE, BE
- **Acceptance criteria:** Given Growth có quyền hợp lệ; When cấu hình block nội dung homepage từ CMS; Then kết quả giúp không cần deploy khi đổi campaign; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0093` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — cấu hình block nội dung homepage từ CMS  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0094` **UX** — UX: Thiết kế wireframe/UI states — cấu hình block nội dung homepage từ CMS  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0095` **FE** — FE: Implement UI và client integration — cấu hình block nội dung homepage từ CMS  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0096` **BE** — BE: Thiết kế domain/API/schema và implement service — cấu hình block nội dung homepage từ CMS  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0097` **QA** — QA: Test plan và automated tests — cấu hình block nội dung homepage từ CMS  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E007 — Advanced tour search

**Objective:** Search chịu tải cao theo destination, date, pax, budget, theme, duration, availability.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0023 — Là Traveller, tôi muốn search tour theo destination, ngày, số khách, ngân sách và theme để nhận kết quả phù hợp trong vài trăm ms.

- **Priority:** P0
- **Tags:** Search, FE, BE, SRE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When search tour theo destination, ngày, số khách, ngân sách và theme; Then kết quả giúp nhận kết quả phù hợp trong vài trăm ms; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy. NFR: warmed p99 <400ms; peak 1,000 QPS.
- **NFR/SLO:** warmed p99 <400ms; peak 1,000 QPS
- **Tickets:**
  - `CT-T0098` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — search tour theo destination, ngày, số khách, ngân sách và theme  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0099` **UX** — UX: Thiết kế wireframe/UI states — search tour theo destination, ngày, số khách, ngân sách và theme  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0100` **FE** — FE: Implement UI và client integration — search tour theo destination, ngày, số khách, ngân sách và theme  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0101` **BE** — BE: Thiết kế domain/API/schema và implement service — search tour theo destination, ngày, số khách, ngân sách và theme  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0102` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — search tour theo destination, ngày, số khách, ngân sách và theme  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0103` **QA** — QA: Test plan và automated tests — search tour theo destination, ngày, số khách, ngân sách và theme  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0024 — Là Traveller, tôi muốn sort/filter kết quả theo giá, đánh giá, thời lượng, còn chỗ, phù hợp AI để so sánh dễ hơn.

- **Priority:** P0
- **Tags:** Search, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When sort/filter kết quả theo giá, đánh giá, thời lượng, còn chỗ, phù hợp AI; Then kết quả giúp so sánh dễ hơn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0104` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — sort/filter kết quả theo giá, đánh giá, thời lượng, còn chỗ, phù...  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0105` **UX** — UX: Thiết kế wireframe/UI states — sort/filter kết quả theo giá, đánh giá, thời lượng, còn chỗ, phù...  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0106` **FE** — FE: Implement UI và client integration — sort/filter kết quả theo giá, đánh giá, thời lượng, còn chỗ, phù...  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0107` **BE** — BE: Thiết kế domain/API/schema và implement service — sort/filter kết quả theo giá, đánh giá, thời lượng, còn chỗ, phù...  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0108` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — sort/filter kết quả theo giá, đánh giá, thời lượng, còn chỗ, phù...  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0109` **QA** — QA: Test plan và automated tests — sort/filter kết quả theo giá, đánh giá, thời lượng, còn chỗ, phù...  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0025 — Là Traveller, tôi muốn chia sẻ URL giữ nguyên filter state để gửi lựa chọn cho bạn bè/gia đình.

- **Priority:** P1
- **Tags:** FE, Search
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When chia sẻ URL giữ nguyên filter state; Then kết quả giúp gửi lựa chọn cho bạn bè/gia đình; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0110` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — chia sẻ URL giữ nguyên filter state  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0111` **UX** — UX: Thiết kế wireframe/UI states — chia sẻ URL giữ nguyên filter state  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0112` **FE** — FE: Implement UI và client integration — chia sẻ URL giữ nguyên filter state  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0113` **BE** — BE: Thiết kế domain/API/schema và implement service — chia sẻ URL giữ nguyên filter state  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0114` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — chia sẻ URL giữ nguyên filter state  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0115` **QA** — QA: Test plan và automated tests — chia sẻ URL giữ nguyên filter state  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0026 — Là SRE, tôi muốn load test search ở 1,000 QPS peak để biết hệ thống chịu tải thật.

- **Priority:** P0
- **Tags:** SRE, QA, Search
- **Acceptance criteria:** Given SRE có quyền hợp lệ; When load test search ở 1,000 QPS peak; Then kết quả giúp biết hệ thống chịu tải thật; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0116` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — load test search ở 1,000 QPS peak  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0117` **BE** — BE: Thiết kế domain/API/schema và implement service — load test search ở 1,000 QPS peak  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0118` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — load test search ở 1,000 QPS peak  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0119` **QA** — QA: Test plan và automated tests — load test search ở 1,000 QPS peak  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E008 — Tour detail, policy snapshot & SEO

**Objective:** Trang chi tiết tour đầy đủ, cacheable, rõ chính sách và tối ưu SEO.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0027 — Là Traveller, tôi muốn xem tour detail với itinerary ngày-từng-ngày, ảnh, giá, inclusions/exclusions để ra quyết định đặt tour.

- **Priority:** P0
- **Tags:** FE, BE, CMS
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When xem tour detail với itinerary ngày-từng-ngày, ảnh, giá, inclusions/exclusions; Then kết quả giúp ra quyết định đặt tour; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0120` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem tour detail với itinerary ngày-từng-ngày, ảnh, giá,...  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0121` **UX** — UX: Thiết kế wireframe/UI states — xem tour detail với itinerary ngày-từng-ngày, ảnh, giá,...  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0122` **FE** — FE: Implement UI và client integration — xem tour detail với itinerary ngày-từng-ngày, ảnh, giá,...  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0123` **BE** — BE: Thiết kế domain/API/schema và implement service — xem tour detail với itinerary ngày-từng-ngày, ảnh, giá,...  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0124` **QA** — QA: Test plan và automated tests — xem tour detail với itinerary ngày-từng-ngày, ảnh, giá,...  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0028 — Là Traveller, tôi muốn xem cancellation policy, điều kiện trẻ em/người già và điều kiện visa để tránh hiểu sai trước khi đặt.

- **Priority:** P0
- **Tags:** Policy, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When xem cancellation policy, điều kiện trẻ em/người già và điều kiện visa; Then kết quả giúp tránh hiểu sai trước khi đặt; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0125` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem cancellation policy, điều kiện trẻ em/người già và điều kiện visa  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0126` **UX** — UX: Thiết kế wireframe/UI states — xem cancellation policy, điều kiện trẻ em/người già và điều kiện visa  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0127` **FE** — FE: Implement UI và client integration — xem cancellation policy, điều kiện trẻ em/người già và điều kiện visa  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0128` **BE** — BE: Thiết kế domain/API/schema và implement service — xem cancellation policy, điều kiện trẻ em/người già và điều kiện visa  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0129` **QA** — QA: Test plan và automated tests — xem cancellation policy, điều kiện trẻ em/người già và điều kiện visa  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0029 — Là Growth, tôi muốn tour detail có metadata SEO, schema.org và sitemap để tăng organic traffic.

- **Priority:** P1
- **Tags:** SEO, FE, CMS
- **Acceptance criteria:** Given Growth có quyền hợp lệ; When tour detail có metadata SEO, schema.org và sitemap; Then kết quả giúp tăng organic traffic; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0130` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tour detail có metadata SEO, schema.org và sitemap  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0131` **UX** — UX: Thiết kế wireframe/UI states — tour detail có metadata SEO, schema.org và sitemap  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0132` **FE** — FE: Implement UI và client integration — tour detail có metadata SEO, schema.org và sitemap  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0133` **BE** — BE: Thiết kế domain/API/schema và implement service — tour detail có metadata SEO, schema.org và sitemap  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0134` **QA** — QA: Test plan và automated tests — tour detail có metadata SEO, schema.org và sitemap  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0030 — Là BA, tôi muốn đảm bảo policy snapshot gắn vào quote/booking để booking sau này không bị thay đổi chính sách ngược.

- **Priority:** P0
- **Tags:** Policy, BE, QA
- **Acceptance criteria:** Given BA có quyền hợp lệ; When đảm bảo policy snapshot gắn vào quote/booking; Then kết quả giúp booking sau này không bị thay đổi chính sách ngược; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0135` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — đảm bảo policy snapshot gắn vào quote/booking  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0136` **BE** — BE: Thiết kế domain/API/schema và implement service — đảm bảo policy snapshot gắn vào quote/booking  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0137` **QA** — QA: Test plan và automated tests — đảm bảo policy snapshot gắn vào quote/booking  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E009 — Compare, wishlist & price alert

**Objective:** Giúp người dùng cân nhắc nhiều tour và quay lại khi có giá/chỗ tốt.  
**Priority:** P1  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0031 — Là Traveller, tôi muốn so sánh 2-4 tour theo giá, lịch trình, phù hợp nhu cầu để quyết định nhanh hơn.

- **Priority:** P1
- **Tags:** FE, Search, AI
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When so sánh 2-4 tour theo giá, lịch trình, phù hợp nhu cầu; Then kết quả giúp quyết định nhanh hơn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0138` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — so sánh 2-4 tour theo giá, lịch trình, phù hợp nhu cầu  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0139` **UX** — UX: Thiết kế wireframe/UI states — so sánh 2-4 tour theo giá, lịch trình, phù hợp nhu cầu  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0140` **FE** — FE: Implement UI và client integration — so sánh 2-4 tour theo giá, lịch trình, phù hợp nhu cầu  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0141` **BE** — BE: Thiết kế domain/API/schema và implement service — so sánh 2-4 tour theo giá, lịch trình, phù hợp nhu cầu  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0142` **AI** — AI: Thiết kế prompt/tool schema/eval cases — so sánh 2-4 tour theo giá, lịch trình, phù hợp nhu cầu  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0143` **Security** — Security: Threat model và security control — so sánh 2-4 tour theo giá, lịch trình, phù hợp nhu cầu  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0144` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — so sánh 2-4 tour theo giá, lịch trình, phù hợp nhu cầu  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0145` **QA** — QA: Test plan và automated tests — so sánh 2-4 tour theo giá, lịch trình, phù hợp nhu cầu  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0032 — Là Traveller, tôi muốn lưu wishlist tour yêu thích để theo dõi lại sau.

- **Priority:** P1
- **Tags:** FE, BE, Analytics
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When lưu wishlist tour yêu thích; Then kết quả giúp theo dõi lại sau; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0146` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — lưu wishlist tour yêu thích  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0147` **UX** — UX: Thiết kế wireframe/UI states — lưu wishlist tour yêu thích  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0148` **FE** — FE: Implement UI và client integration — lưu wishlist tour yêu thích  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0149` **BE** — BE: Thiết kế domain/API/schema và implement service — lưu wishlist tour yêu thích  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0150` **Data** — Data: Event taxonomy/data model/dashboard metric — lưu wishlist tour yêu thích  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0151` **QA** — QA: Test plan và automated tests — lưu wishlist tour yêu thích  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0033 — Là Traveller, tôi muốn nhận price/seat alert khi opt-in để không bỏ lỡ tour phù hợp.

- **Priority:** P2
- **Tags:** Notification, BE, Privacy
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When nhận price/seat alert khi opt-in; Then kết quả giúp không bỏ lỡ tour phù hợp; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0152` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — nhận price/seat alert khi opt-in  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0153` **BE** — BE: Thiết kế domain/API/schema và implement service — nhận price/seat alert khi opt-in  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0154` **Security** — Security: Threat model và security control — nhận price/seat alert khi opt-in  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0155` **QA** — QA: Test plan và automated tests — nhận price/seat alert khi opt-in  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP04 — AI Travel Assistant, RAG & MCP

**Owner:** AI Product Lead

## CT-E010 — Conversational travel assistant

**Objective:** AI chat đa lượt bằng tiếng Việt/Anh, hiểu ngữ cảnh và chỉ dùng dữ liệu có thật.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0034 — Là Traveller, tôi muốn chat với AI bằng tiếng Việt/Anh để mô tả chuyến đi để không cần tự filter phức tạp.

- **Priority:** P0
- **Tags:** AI, FE, BE, SRE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When chat với AI bằng tiếng Việt/Anh để mô tả chuyến đi; Then kết quả giúp không cần tự filter phức tạp; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy. NFR: first token p95 <1s; full simple answer <3s.
- **NFR/SLO:** first token p95 <1s; full simple answer <3s
- **Tickets:**
  - `CT-T0156` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — chat với AI bằng tiếng Việt/Anh để mô tả chuyến đi  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0157` **UX** — UX: Thiết kế wireframe/UI states — chat với AI bằng tiếng Việt/Anh để mô tả chuyến đi  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0158` **FE** — FE: Implement UI và client integration — chat với AI bằng tiếng Việt/Anh để mô tả chuyến đi  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0159` **BE** — BE: Thiết kế domain/API/schema và implement service — chat với AI bằng tiếng Việt/Anh để mô tả chuyến đi  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0160` **AI** — AI: Thiết kế prompt/tool schema/eval cases — chat với AI bằng tiếng Việt/Anh để mô tả chuyến đi  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0161` **Security** — Security: Threat model và security control — chat với AI bằng tiếng Việt/Anh để mô tả chuyến đi  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0162` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — chat với AI bằng tiếng Việt/Anh để mô tả chuyến đi  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0163` **QA** — QA: Test plan và automated tests — chat với AI bằng tiếng Việt/Anh để mô tả chuyến đi  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0035 — Là Traveller, tôi muốn AI nhớ context trong phiên như 'tour kia', 'ngày đó', '2 người lớn 1 trẻ em' để trò chuyện tự nhiên.

- **Priority:** P0
- **Tags:** AI, BE, Data
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When AI nhớ context trong phiên như 'tour kia', 'ngày đó', '2 người lớn 1 trẻ em'; Then kết quả giúp trò chuyện tự nhiên; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0164` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — AI nhớ context trong phiên như 'tour kia', 'ngày đó', '2 người lớn...  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0165` **BE** — BE: Thiết kế domain/API/schema và implement service — AI nhớ context trong phiên như 'tour kia', 'ngày đó', '2 người lớn...  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0166` **AI** — AI: Thiết kế prompt/tool schema/eval cases — AI nhớ context trong phiên như 'tour kia', 'ngày đó', '2 người lớn...  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0167` **Security** — Security: Threat model và security control — AI nhớ context trong phiên như 'tour kia', 'ngày đó', '2 người lớn...  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0168` **Data** — Data: Event taxonomy/data model/dashboard metric — AI nhớ context trong phiên như 'tour kia', 'ngày đó', '2 người lớn...  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0169` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — AI nhớ context trong phiên như 'tour kia', 'ngày đó', '2 người lớn...  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0170` **QA** — QA: Test plan và automated tests — AI nhớ context trong phiên như 'tour kia', 'ngày đó', '2 người lớn...  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0036 — Là Traveller, tôi muốn AI luôn gọi tool search_tour khi recommend tour để không bịa tour/giá/chỗ.

- **Priority:** P0
- **Tags:** AI, Tool, QA
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When AI luôn gọi tool search_tour khi recommend tour; Then kết quả giúp không bịa tour/giá/chỗ; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0171` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — AI luôn gọi tool search_tour khi recommend tour  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0172` **AI** — AI: Thiết kế prompt/tool schema/eval cases — AI luôn gọi tool search_tour khi recommend tour  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0173` **Security** — Security: Threat model và security control — AI luôn gọi tool search_tour khi recommend tour  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0174` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — AI luôn gọi tool search_tour khi recommend tour  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0175` **QA** — QA: Test plan và automated tests — AI luôn gọi tool search_tour khi recommend tour  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0037 — Là Support, tôi muốn escalate conversation sang người thật khi confidence thấp để xử lý tình huống AI không chắc.

- **Priority:** P1
- **Tags:** AI, Ops, FE
- **Acceptance criteria:** Given Support có quyền hợp lệ; When escalate conversation sang người thật khi confidence thấp; Then kết quả giúp xử lý tình huống AI không chắc; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0176` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — escalate conversation sang người thật khi confidence thấp  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0177` **UX** — UX: Thiết kế wireframe/UI states — escalate conversation sang người thật khi confidence thấp  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0178` **FE** — FE: Implement UI và client integration — escalate conversation sang người thật khi confidence thấp  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0179` **AI** — AI: Thiết kế prompt/tool schema/eval cases — escalate conversation sang người thật khi confidence thấp  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0180` **Security** — Security: Threat model và security control — escalate conversation sang người thật khi confidence thấp  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0181` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — escalate conversation sang người thật khi confidence thấp  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0182` **QA** — QA: Test plan và automated tests — escalate conversation sang người thật khi confidence thấp  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E011 — RAG knowledge base for policy/visa/FAQ

**Objective:** AI trả lời chính sách, visa, hoàn hủy, thủ tục bằng nguồn đã kiểm soát.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0038 — Là Content Admin, tôi muốn upload/version tài liệu FAQ, visa, refund, supplier policy để AI có nguồn đáng tin.

- **Priority:** P0
- **Tags:** RAG, CMS, BE
- **Acceptance criteria:** Given Content Admin có quyền hợp lệ; When upload/version tài liệu FAQ, visa, refund, supplier policy; Then kết quả giúp AI có nguồn đáng tin; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0183` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — upload/version tài liệu FAQ, visa, refund, supplier policy  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0184` **UX** — UX: Thiết kế wireframe/UI states — upload/version tài liệu FAQ, visa, refund, supplier policy  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0185` **FE** — FE: Implement UI và client integration — upload/version tài liệu FAQ, visa, refund, supplier policy  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0186` **BE** — BE: Thiết kế domain/API/schema và implement service — upload/version tài liệu FAQ, visa, refund, supplier policy  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0187` **AI** — AI: Thiết kế prompt/tool schema/eval cases — upload/version tài liệu FAQ, visa, refund, supplier policy  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0188` **Data** — Data: Chuẩn hóa ingestion, chunking, embedding và retrieval eval — upload/version tài liệu FAQ, visa, refund, supplier policy  
    AC: Nguồn có version; top-k retrieval được đo; stale/deprecated docs bị loại khỏi answer. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0189` **QA** — QA: Test plan và automated tests — upload/version tài liệu FAQ, visa, refund, supplier policy  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0039 — Là Traveller, tôi muốn nhận câu trả lời có trích source/version chính sách để tin tưởng và kiểm chứng được.

- **Priority:** P0
- **Tags:** RAG, AI, FE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When nhận câu trả lời có trích source/version chính sách; Then kết quả giúp tin tưởng và kiểm chứng được; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0190` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — nhận câu trả lời có trích source/version chính sách  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0191` **UX** — UX: Thiết kế wireframe/UI states — nhận câu trả lời có trích source/version chính sách  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0192` **FE** — FE: Implement UI và client integration — nhận câu trả lời có trích source/version chính sách  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0193` **AI** — AI: Thiết kế prompt/tool schema/eval cases — nhận câu trả lời có trích source/version chính sách  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0194` **Data** — Data: Chuẩn hóa ingestion, chunking, embedding và retrieval eval — nhận câu trả lời có trích source/version chính sách  
    AC: Nguồn có version; top-k retrieval được đo; stale/deprecated docs bị loại khỏi answer. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0195` **Security** — Security: Threat model và security control — nhận câu trả lời có trích source/version chính sách  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0196` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — nhận câu trả lời có trích source/version chính sách  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0197` **QA** — QA: Test plan và automated tests — nhận câu trả lời có trích source/version chính sách  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0040 — Là AI Lead, tôi muốn chạy retrieval eval cho top-k accuracy để biết RAG có tìm đúng tài liệu.

- **Priority:** P0
- **Tags:** AI, QA, Data
- **Acceptance criteria:** Given AI Lead có quyền hợp lệ; When chạy retrieval eval cho top-k accuracy; Then kết quả giúp biết RAG có tìm đúng tài liệu; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0198` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — chạy retrieval eval cho top-k accuracy  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0199` **AI** — AI: Thiết kế prompt/tool schema/eval cases — chạy retrieval eval cho top-k accuracy  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0200` **Security** — Security: Threat model và security control — chạy retrieval eval cho top-k accuracy  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0201` **Data** — Data: Event taxonomy/data model/dashboard metric — chạy retrieval eval cho top-k accuracy  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0202` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — chạy retrieval eval cho top-k accuracy  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0203` **QA** — QA: Test plan và automated tests — chạy retrieval eval cho top-k accuracy  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0041 — Là Compliance, tôi muốn ẩn/chặn câu trả lời pháp lý/y tế nhạy cảm ngoài phạm vi để giảm rủi ro tư vấn sai.

- **Priority:** P1
- **Tags:** AI, Legal, Security
- **Acceptance criteria:** Given Compliance có quyền hợp lệ; When ẩn/chặn câu trả lời pháp lý/y tế nhạy cảm ngoài phạm vi; Then kết quả giúp giảm rủi ro tư vấn sai; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0204` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — ẩn/chặn câu trả lời pháp lý/y tế nhạy cảm ngoài phạm vi  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0205` **AI** — AI: Thiết kế prompt/tool schema/eval cases — ẩn/chặn câu trả lời pháp lý/y tế nhạy cảm ngoài phạm vi  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0206` **Security** — Security: Threat model và security control — ẩn/chặn câu trả lời pháp lý/y tế nhạy cảm ngoài phạm vi  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0207` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — ẩn/chặn câu trả lời pháp lý/y tế nhạy cảm ngoài phạm vi  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0208` **QA** — QA: Test plan và automated tests — ẩn/chặn câu trả lời pháp lý/y tế nhạy cảm ngoài phạm vi  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E012 — Tool calling, tool gateway & action confirmation

**Objective:** AI thực hiện tác vụ qua tool gateway có quyền hạn, audit và confirm trước hành động tài chính.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0042 — Là Traveller, tôi muốn AI tạo draft quote/booking sau khi tôi xác nhận để tiện nhưng không tự ý charge.

- **Priority:** P0
- **Tags:** AI, Booking, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When AI tạo draft quote/booking sau khi tôi xác nhận; Then kết quả giúp tiện nhưng không tự ý charge; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0209` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — AI tạo draft quote/booking sau khi tôi xác nhận  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0210` **UX** — UX: Thiết kế wireframe/UI states — AI tạo draft quote/booking sau khi tôi xác nhận  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0211` **FE** — FE: Implement UI và client integration — AI tạo draft quote/booking sau khi tôi xác nhận  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0212` **BE** — BE: Thiết kế domain/API/schema và implement service — AI tạo draft quote/booking sau khi tôi xác nhận  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0213` **AI** — AI: Thiết kế prompt/tool schema/eval cases — AI tạo draft quote/booking sau khi tôi xác nhận  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0214` **Security** — Security: Threat model và security control — AI tạo draft quote/booking sau khi tôi xác nhận  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0215` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — AI tạo draft quote/booking sau khi tôi xác nhận  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0216` **QA** — QA: Test plan và automated tests — AI tạo draft quote/booking sau khi tôi xác nhận  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0043 — Là Security, tôi muốn mọi tool call có policy check, idempotency và audit để ngăn misuse/prompt injection.

- **Priority:** P0
- **Tags:** AI, Security, BE
- **Acceptance criteria:** Given Security có quyền hợp lệ; When mọi tool call có policy check, idempotency và audit; Then kết quả giúp ngăn misuse/prompt injection; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0217` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — mọi tool call có policy check, idempotency và audit  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0218` **BE** — BE: Thiết kế domain/API/schema và implement service — mọi tool call có policy check, idempotency và audit  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0219` **AI** — AI: Thiết kế prompt/tool schema/eval cases — mọi tool call có policy check, idempotency và audit  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0220` **Security** — Security: Threat model và security control — mọi tool call có policy check, idempotency và audit  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0221` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — mọi tool call có policy check, idempotency và audit  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0222` **QA** — QA: Test plan và automated tests — mọi tool call có policy check, idempotency và audit  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0044 — Là AI Lead, tôi muốn giới hạn max tool depth, timeout và retry budget để tránh agent loop và tốn chi phí.

- **Priority:** P0
- **Tags:** AI, SRE, BE
- **Acceptance criteria:** Given AI Lead có quyền hợp lệ; When giới hạn max tool depth, timeout và retry budget; Then kết quả giúp tránh agent loop và tốn chi phí; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0223` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — giới hạn max tool depth, timeout và retry budget  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0224` **BE** — BE: Thiết kế domain/API/schema và implement service — giới hạn max tool depth, timeout và retry budget  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0225` **AI** — AI: Thiết kế prompt/tool schema/eval cases — giới hạn max tool depth, timeout và retry budget  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0226` **Security** — Security: Threat model và security control — giới hạn max tool depth, timeout và retry budget  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0227` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — giới hạn max tool depth, timeout và retry budget  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0228` **QA** — QA: Test plan và automated tests — giới hạn max tool depth, timeout và retry budget  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0045 — Là Ops, tôi muốn replay/debug tool call từ trace khi có khiếu nại để điều tra được lỗi AI.

- **Priority:** P1
- **Tags:** AI, Observability, Ops
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When replay/debug tool call từ trace khi có khiếu nại; Then kết quả giúp điều tra được lỗi AI; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0229` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — replay/debug tool call từ trace khi có khiếu nại  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0230` **AI** — AI: Thiết kế prompt/tool schema/eval cases — replay/debug tool call từ trace khi có khiếu nại  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0231` **Security** — Security: Threat model và security control — replay/debug tool call từ trace khi có khiếu nại  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0232` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — replay/debug tool call từ trace khi có khiếu nại  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0233` **QA** — QA: Test plan và automated tests — replay/debug tool call từ trace khi có khiếu nại  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E013 — MCP server/client over Streamable HTTP

**Objective:** Expose CoralTrip tools và gọi external tools qua MCP Streamable HTTP an toàn.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0046 — Là Partner Agent, tôi muốn discover và gọi CoralTrip MCP tools qua Streamable HTTP để tích hợp agent bên ngoài.

- **Priority:** P0
- **Tags:** MCP, BE, Security
- **Acceptance criteria:** Given Partner Agent có quyền hợp lệ; When discover và gọi CoralTrip MCP tools qua Streamable HTTP; Then kết quả giúp tích hợp agent bên ngoài; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0234` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — discover và gọi CoralTrip MCP tools qua Streamable HTTP  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0235` **BE** — BE: Thiết kế domain/API/schema và implement service — discover và gọi CoralTrip MCP tools qua Streamable HTTP  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0236` **AI** — AI: Thiết kế prompt/tool schema/eval cases — discover và gọi CoralTrip MCP tools qua Streamable HTTP  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0237` **Security** — Security: Threat model và security control — discover và gọi CoralTrip MCP tools qua Streamable HTTP  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0238` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — discover và gọi CoralTrip MCP tools qua Streamable HTTP  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0239` **QA** — QA: Test plan và automated tests — discover và gọi CoralTrip MCP tools qua Streamable HTTP  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0047 — Là Security, tôi muốn MCP endpoint validate Origin, token, session và protocol version để chặn client không hợp lệ.

- **Priority:** P0
- **Tags:** MCP, Security, SRE
- **Acceptance criteria:** Given Security có quyền hợp lệ; When MCP endpoint validate Origin, token, session và protocol version; Then kết quả giúp chặn client không hợp lệ; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0240` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — MCP endpoint validate Origin, token, session và protocol version  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0241` **AI** — AI: Thiết kế prompt/tool schema/eval cases — MCP endpoint validate Origin, token, session và protocol version  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0242` **Security** — Security: Threat model và security control — MCP endpoint validate Origin, token, session và protocol version  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0243` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — MCP endpoint validate Origin, token, session và protocol version  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0244` **QA** — QA: Test plan và automated tests — MCP endpoint validate Origin, token, session và protocol version  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0048 — Là AI Agent, tôi muốn gọi external MCP suppliers qua allowlist để mở rộng flight/hotel khi đối tác sẵn sàng.

- **Priority:** P1
- **Tags:** MCP, SupplierAdapter, AI
- **Acceptance criteria:** Given AI Agent có quyền hợp lệ; When gọi external MCP suppliers qua allowlist; Then kết quả giúp mở rộng flight/hotel khi đối tác sẵn sàng; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0245` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — gọi external MCP suppliers qua allowlist  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0246` **BE** — BE: Thiết kế domain/API/schema và implement service — gọi external MCP suppliers qua allowlist  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0247` **AI** — AI: Thiết kế prompt/tool schema/eval cases — gọi external MCP suppliers qua allowlist  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0248` **Integration** — Integration: Implement adapter/contract test/mock — gọi external MCP suppliers qua allowlist  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0249` **Security** — Security: Threat model và security control — gọi external MCP suppliers qua allowlist  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0250` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — gọi external MCP suppliers qua allowlist  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0251` **QA** — QA: Test plan và automated tests — gọi external MCP suppliers qua allowlist  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0049 — Là SRE, tôi muốn rate-limit MCP theo tool, tenant và user để bảo vệ hệ thống khỏi abuse.

- **Priority:** P0
- **Tags:** MCP, SRE, Security
- **Acceptance criteria:** Given SRE có quyền hợp lệ; When rate-limit MCP theo tool, tenant và user; Then kết quả giúp bảo vệ hệ thống khỏi abuse; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0252` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — rate-limit MCP theo tool, tenant và user  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0253` **AI** — AI: Thiết kế prompt/tool schema/eval cases — rate-limit MCP theo tool, tenant và user  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0254` **Security** — Security: Threat model và security control — rate-limit MCP theo tool, tenant và user  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0255` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — rate-limit MCP theo tool, tenant và user  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0256` **QA** — QA: Test plan và automated tests — rate-limit MCP theo tool, tenant và user  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E014 — AI evaluation, safety & cost governance

**Objective:** Đo chất lượng, hallucination, prompt injection, tool misuse và chi phí AI liên tục.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0050 — Là AI Lead, tôi muốn quản lý golden dataset cho travel search/policy/booking để có regression test.

- **Priority:** P0
- **Tags:** AI, QA, Data
- **Acceptance criteria:** Given AI Lead có quyền hợp lệ; When quản lý golden dataset cho travel search/policy/booking; Then kết quả giúp có regression test; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0257` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — quản lý golden dataset cho travel search/policy/booking  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0258` **AI** — AI: Thiết kế prompt/tool schema/eval cases — quản lý golden dataset cho travel search/policy/booking  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0259` **Security** — Security: Threat model và security control — quản lý golden dataset cho travel search/policy/booking  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0260` **Data** — Data: Event taxonomy/data model/dashboard metric — quản lý golden dataset cho travel search/policy/booking  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0261` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — quản lý golden dataset cho travel search/policy/booking  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0262` **QA** — QA: Test plan và automated tests — quản lý golden dataset cho travel search/policy/booking  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0051 — Là AI Lead, tôi muốn xem dashboard hallucination, tool success, latency và token cost để quản trị chất lượng AI.

- **Priority:** P0
- **Tags:** AI, Analytics, SRE
- **Acceptance criteria:** Given AI Lead có quyền hợp lệ; When xem dashboard hallucination, tool success, latency và token cost; Then kết quả giúp quản trị chất lượng AI; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0263` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem dashboard hallucination, tool success, latency và token cost  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0264` **AI** — AI: Thiết kế prompt/tool schema/eval cases — xem dashboard hallucination, tool success, latency và token cost  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0265` **Security** — Security: Threat model và security control — xem dashboard hallucination, tool success, latency và token cost  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0266` **Data** — Data: Event taxonomy/data model/dashboard metric — xem dashboard hallucination, tool success, latency và token cost  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0267` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — xem dashboard hallucination, tool success, latency và token cost  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0268` **QA** — QA: Test plan và automated tests — xem dashboard hallucination, tool success, latency và token cost  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0052 — Là Security, tôi muốn test prompt injection và data exfiltration theo OWASP LLM để giảm rủi ro an toàn.

- **Priority:** P0
- **Tags:** AI, Security, QA
- **Acceptance criteria:** Given Security có quyền hợp lệ; When test prompt injection và data exfiltration theo OWASP LLM; Then kết quả giúp giảm rủi ro an toàn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0269` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — test prompt injection và data exfiltration theo OWASP LLM  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0270` **AI** — AI: Thiết kế prompt/tool schema/eval cases — test prompt injection và data exfiltration theo OWASP LLM  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0271` **Security** — Security: Threat model và security control — test prompt injection và data exfiltration theo OWASP LLM  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0272` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — test prompt injection và data exfiltration theo OWASP LLM  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0273` **QA** — QA: Test plan và automated tests — test prompt injection và data exfiltration theo OWASP LLM  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0053 — Là Finance, tôi muốn giới hạn cost AI theo user/session/tool để không mất kiểm soát chi phí.

- **Priority:** P1
- **Tags:** AI, Finance, SRE
- **Acceptance criteria:** Given Finance có quyền hợp lệ; When giới hạn cost AI theo user/session/tool; Then kết quả giúp không mất kiểm soát chi phí; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0274` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — giới hạn cost AI theo user/session/tool  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0275` **AI** — AI: Thiết kế prompt/tool schema/eval cases — giới hạn cost AI theo user/session/tool  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0276` **Security** — Security: Threat model và security control — giới hạn cost AI theo user/session/tool  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0277` **Data** — Data: Event taxonomy/data model/dashboard metric — giới hạn cost AI theo user/session/tool  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0278` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — giới hạn cost AI theo user/session/tool  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0279` **QA** — QA: Test plan và automated tests — giới hạn cost AI theo user/session/tool  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP05 — Catalog, Operator Portal & Product Content

**Owner:** Supplier Product Lead

## CT-E015 — Tour product management

**Objective:** Tour operator tạo/sửa/publish tour với dữ liệu chuẩn hóa và versioning.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0054 — Là Tour Operator, tôi muốn tạo tour với title, slug, destination, duration, itinerary, policy, images để đưa sản phẩm lên hệ thống.

- **Priority:** P0
- **Tags:** Catalog, FE, BE, Media
- **Acceptance criteria:** Given Tour Operator có quyền hợp lệ; When tạo tour với title, slug, destination, duration, itinerary, policy, images; Then kết quả giúp đưa sản phẩm lên hệ thống; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0280` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tạo tour với title, slug, destination, duration, itinerary, policy,...  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0281` **UX** — UX: Thiết kế wireframe/UI states — tạo tour với title, slug, destination, duration, itinerary, policy,...  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0282` **FE** — FE: Implement UI và client integration — tạo tour với title, slug, destination, duration, itinerary, policy,...  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0283` **BE** — BE: Thiết kế domain/API/schema và implement service — tạo tour với title, slug, destination, duration, itinerary, policy,...  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0284` **QA** — QA: Test plan và automated tests — tạo tour với title, slug, destination, duration, itinerary, policy,...  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0055 — Là Tour Operator, tôi muốn submit tour để admin review/publish để kiểm soát chất lượng catalogue.

- **Priority:** P0
- **Tags:** Workflow, FE, BE, Admin
- **Acceptance criteria:** Given Tour Operator có quyền hợp lệ; When submit tour để admin review/publish; Then kết quả giúp kiểm soát chất lượng catalogue; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0285` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — submit tour để admin review/publish  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0286` **UX** — UX: Thiết kế wireframe/UI states — submit tour để admin review/publish  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0287` **FE** — FE: Implement UI và client integration — submit tour để admin review/publish  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0288` **BE** — BE: Thiết kế domain/API/schema và implement service — submit tour để admin review/publish  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0289` **QA** — QA: Test plan và automated tests — submit tour để admin review/publish  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0056 — Là Admin, tôi muốn xem lịch sử version của tour và rollback để sửa lỗi nội dung an toàn.

- **Priority:** P1
- **Tags:** Catalog, Audit, BE
- **Acceptance criteria:** Given Admin có quyền hợp lệ; When xem lịch sử version của tour và rollback; Then kết quả giúp sửa lỗi nội dung an toàn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0290` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem lịch sử version của tour và rollback  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0291` **BE** — BE: Thiết kế domain/API/schema và implement service — xem lịch sử version của tour và rollback  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0292` **QA** — QA: Test plan và automated tests — xem lịch sử version của tour và rollback  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0057 — Là Content Admin, tôi muốn quản lý translation tiếng Việt/Anh cho tour để hỗ trợ đa ngôn ngữ.

- **Priority:** P2
- **Tags:** i18n, CMS, FE, BE
- **Acceptance criteria:** Given Content Admin có quyền hợp lệ; When quản lý translation tiếng Việt/Anh cho tour; Then kết quả giúp hỗ trợ đa ngôn ngữ; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0293` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — quản lý translation tiếng Việt/Anh cho tour  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0294` **UX** — UX: Thiết kế wireframe/UI states — quản lý translation tiếng Việt/Anh cho tour  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0295` **FE** — FE: Implement UI và client integration — quản lý translation tiếng Việt/Anh cho tour  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0296` **BE** — BE: Thiết kế domain/API/schema và implement service — quản lý translation tiếng Việt/Anh cho tour  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0297` **QA** — QA: Test plan và automated tests — quản lý translation tiếng Việt/Anh cho tour  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E016 — Departures, allotment & seasonal pricing

**Objective:** Quản lý ngày khởi hành, quota chỗ, phụ thu mùa, blackout date.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0058 — Là Tour Operator, tôi muốn tạo lịch khởi hành và số chỗ theo ngày để bán đúng inventory.

- **Priority:** P0
- **Tags:** Availability, FE, BE
- **Acceptance criteria:** Given Tour Operator có quyền hợp lệ; When tạo lịch khởi hành và số chỗ theo ngày; Then kết quả giúp bán đúng inventory; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0298` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tạo lịch khởi hành và số chỗ theo ngày  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0299` **UX** — UX: Thiết kế wireframe/UI states — tạo lịch khởi hành và số chỗ theo ngày  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0300` **FE** — FE: Implement UI và client integration — tạo lịch khởi hành và số chỗ theo ngày  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0301` **BE** — BE: Thiết kế domain/API/schema và implement service — tạo lịch khởi hành và số chỗ theo ngày  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0302` **QA** — QA: Test plan và automated tests — tạo lịch khởi hành và số chỗ theo ngày  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0059 — Là Tour Operator, tôi muốn batch update giá/chỗ theo mùa bằng calendar để giảm thao tác thủ công.

- **Priority:** P1
- **Tags:** Pricing, FE, BE
- **Acceptance criteria:** Given Tour Operator có quyền hợp lệ; When batch update giá/chỗ theo mùa bằng calendar; Then kết quả giúp giảm thao tác thủ công; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0303` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — batch update giá/chỗ theo mùa bằng calendar  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0304` **UX** — UX: Thiết kế wireframe/UI states — batch update giá/chỗ theo mùa bằng calendar  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0305` **FE** — FE: Implement UI và client integration — batch update giá/chỗ theo mùa bằng calendar  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0306` **BE** — BE: Thiết kế domain/API/schema và implement service — batch update giá/chỗ theo mùa bằng calendar  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0307` **QA** — QA: Test plan và automated tests — batch update giá/chỗ theo mùa bằng calendar  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0060 — Là System, tôi muốn không cho xóa departure đã có booking/hold để đảm bảo toàn vẹn booking.

- **Priority:** P0
- **Tags:** Availability, BE, QA
- **Acceptance criteria:** Given System có quyền hợp lệ; When không cho xóa departure đã có booking/hold; Then kết quả giúp đảm bảo toàn vẹn booking; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0308` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — không cho xóa departure đã có booking/hold  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0309` **BE** — BE: Thiết kế domain/API/schema và implement service — không cho xóa departure đã có booking/hold  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0310` **QA** — QA: Test plan và automated tests — không cho xóa departure đã có booking/hold  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0061 — Là Ops, tôi muốn audit mọi thay đổi giá/chỗ để truy vết dispute.

- **Priority:** P0
- **Tags:** Audit, BE, Admin
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When audit mọi thay đổi giá/chỗ; Then kết quả giúp truy vết dispute; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0311` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — audit mọi thay đổi giá/chỗ  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0312` **UX** — UX: Thiết kế wireframe/UI states — audit mọi thay đổi giá/chỗ  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0313` **FE** — FE: Implement UI và client integration — audit mọi thay đổi giá/chỗ  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0314` **BE** — BE: Thiết kế domain/API/schema và implement service — audit mọi thay đổi giá/chỗ  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0315` **QA** — QA: Test plan và automated tests — audit mọi thay đổi giá/chỗ  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E017 — Bulk import, media and validation

**Objective:** Import dữ liệu tour từ CSV/Excel/API với validation report rõ ràng.  
**Priority:** P1  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0062 — Là Tour Operator, tôi muốn upload CSV/Excel catalogue và xem lỗi từng dòng để onboard nhanh nhiều tour.

- **Priority:** P1
- **Tags:** Import, FE, BE, QA
- **Acceptance criteria:** Given Tour Operator có quyền hợp lệ; When upload CSV/Excel catalogue và xem lỗi từng dòng; Then kết quả giúp onboard nhanh nhiều tour; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0316` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — upload CSV/Excel catalogue và xem lỗi từng dòng  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0317` **UX** — UX: Thiết kế wireframe/UI states — upload CSV/Excel catalogue và xem lỗi từng dòng  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0318` **FE** — FE: Implement UI và client integration — upload CSV/Excel catalogue và xem lỗi từng dòng  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0319` **BE** — BE: Thiết kế domain/API/schema và implement service — upload CSV/Excel catalogue và xem lỗi từng dòng  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0320` **QA** — QA: Test plan và automated tests — upload CSV/Excel catalogue và xem lỗi từng dòng  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0063 — Là Tour Operator, tôi muốn upload media ảnh/video với size/type validation để tour detail đẹp và đúng chuẩn.

- **Priority:** P1
- **Tags:** Media, FE, BE
- **Acceptance criteria:** Given Tour Operator có quyền hợp lệ; When upload media ảnh/video với size/type validation; Then kết quả giúp tour detail đẹp và đúng chuẩn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0321` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — upload media ảnh/video với size/type validation  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0322` **UX** — UX: Thiết kế wireframe/UI states — upload media ảnh/video với size/type validation  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0323` **FE** — FE: Implement UI và client integration — upload media ảnh/video với size/type validation  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0324` **BE** — BE: Thiết kế domain/API/schema và implement service — upload media ảnh/video với size/type validation  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0325` **QA** — QA: Test plan và automated tests — upload media ảnh/video với size/type validation  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0064 — Là System, tôi muốn deduplicate tour theo operator+slug/external_id để tránh trùng sản phẩm.

- **Priority:** P1
- **Tags:** Catalog, BE, Data
- **Acceptance criteria:** Given System có quyền hợp lệ; When deduplicate tour theo operator+slug/external_id; Then kết quả giúp tránh trùng sản phẩm; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0326` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — deduplicate tour theo operator+slug/external_id  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0327` **BE** — BE: Thiết kế domain/API/schema và implement service — deduplicate tour theo operator+slug/external_id  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0328` **Data** — Data: Event taxonomy/data model/dashboard metric — deduplicate tour theo operator+slug/external_id  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0329` **QA** — QA: Test plan và automated tests — deduplicate tour theo operator+slug/external_id  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0065 — Là Admin, tôi muốn xem import job history và retry failed rows để hỗ trợ supplier tốt hơn.

- **Priority:** P1
- **Tags:** Import, Admin, BE
- **Acceptance criteria:** Given Admin có quyền hợp lệ; When xem import job history và retry failed rows; Then kết quả giúp hỗ trợ supplier tốt hơn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0330` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem import job history và retry failed rows  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0331` **UX** — UX: Thiết kế wireframe/UI states — xem import job history và retry failed rows  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0332` **FE** — FE: Implement UI và client integration — xem import job history và retry failed rows  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0333` **BE** — BE: Thiết kế domain/API/schema và implement service — xem import job history và retry failed rows  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0334` **QA** — QA: Test plan và automated tests — xem import job history và retry failed rows  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP06 — Supplier Adapter Platform

**Owner:** Integration Lead

## CT-E018 — Canonical supplier adapter contract

**Objective:** Tất cả supplier tour/flight/hotel/car đi qua adapter chuẩn, chịu tải cao và quan sát được.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0066 — Là Architect, tôi muốn định nghĩa canonical Search/Price/Hold/Confirm/Cancel/Refund ports để booking không phụ thuộc provider cụ thể.

- **Priority:** P0
- **Tags:** SupplierAdapter, Architecture, BE
- **Acceptance criteria:** Given Architect có quyền hợp lệ; When định nghĩa canonical Search/Price/Hold/Confirm/Cancel/Refund ports; Then kết quả giúp booking không phụ thuộc provider cụ thể; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0335` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — định nghĩa canonical Search/Price/Hold/Confirm/Cancel/Refund ports  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0336` **BE** — BE: Thiết kế domain/API/schema và implement service — định nghĩa canonical Search/Price/Hold/Confirm/Cancel/Refund ports  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0337` **Integration** — Integration: Implement adapter/contract test/mock — định nghĩa canonical Search/Price/Hold/Confirm/Cancel/Refund ports  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0338` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — định nghĩa canonical Search/Price/Hold/Confirm/Cancel/Refund ports  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0339` **QA** — QA: Test plan và automated tests — định nghĩa canonical Search/Price/Hold/Confirm/Cancel/Refund ports  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0067 — Là Integration Dev, tôi muốn implement adapter SDK base với retry, timeout, circuit breaker để mỗi adapter thống nhất resilience.

- **Priority:** P0
- **Tags:** SupplierAdapter, SRE, BE
- **Acceptance criteria:** Given Integration Dev có quyền hợp lệ; When implement adapter SDK base với retry, timeout, circuit breaker; Then kết quả giúp mỗi adapter thống nhất resilience; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0340` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — implement adapter SDK base với retry, timeout, circuit breaker  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0341` **BE** — BE: Thiết kế domain/API/schema và implement service — implement adapter SDK base với retry, timeout, circuit breaker  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0342` **Integration** — Integration: Implement adapter/contract test/mock — implement adapter SDK base với retry, timeout, circuit breaker  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0343` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — implement adapter SDK base với retry, timeout, circuit breaker  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0344` **QA** — QA: Test plan và automated tests — implement adapter SDK base với retry, timeout, circuit breaker  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0068 — Là QA, tôi muốn chạy contract test cho adapter bằng mock/sandbox để đảm bảo provider không phá flow.

- **Priority:** P0
- **Tags:** SupplierAdapter, QA, BE
- **Acceptance criteria:** Given QA có quyền hợp lệ; When chạy contract test cho adapter bằng mock/sandbox; Then kết quả giúp đảm bảo provider không phá flow; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0345` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — chạy contract test cho adapter bằng mock/sandbox  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0346` **BE** — BE: Thiết kế domain/API/schema và implement service — chạy contract test cho adapter bằng mock/sandbox  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0347` **Integration** — Integration: Implement adapter/contract test/mock — chạy contract test cho adapter bằng mock/sandbox  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0348` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — chạy contract test cho adapter bằng mock/sandbox  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0349` **QA** — QA: Test plan và automated tests — chạy contract test cho adapter bằng mock/sandbox  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0069 — Là SRE, tôi muốn theo dõi health/latency/error theo supplier để tự động degrade/fallback.

- **Priority:** P0
- **Tags:** SupplierAdapter, Observability, SRE
- **Acceptance criteria:** Given SRE có quyền hợp lệ; When theo dõi health/latency/error theo supplier; Then kết quả giúp tự động degrade/fallback; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0350` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — theo dõi health/latency/error theo supplier  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0351` **BE** — BE: Thiết kế domain/API/schema và implement service — theo dõi health/latency/error theo supplier  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0352` **Integration** — Integration: Implement adapter/contract test/mock — theo dõi health/latency/error theo supplier  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0353` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — theo dõi health/latency/error theo supplier  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0354` **QA** — QA: Test plan và automated tests — theo dõi health/latency/error theo supplier  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E019 — Tour supplier adapter

**Objective:** Kết nối tour operator nội bộ/local supplier qua API hoặc manual operations.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0070 — Là System, tôi muốn giữ tour nội bộ như một adapter first-class để không hard-code internal supplier.

- **Priority:** P0
- **Tags:** SupplierAdapter, Catalog, BE
- **Acceptance criteria:** Given System có quyền hợp lệ; When giữ tour nội bộ như một adapter first-class; Then kết quả giúp không hard-code internal supplier; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0355` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — giữ tour nội bộ như một adapter first-class  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0356` **BE** — BE: Thiết kế domain/API/schema và implement service — giữ tour nội bộ như một adapter first-class  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0357` **Integration** — Integration: Implement adapter/contract test/mock — giữ tour nội bộ như một adapter first-class  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0358` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — giữ tour nội bộ như một adapter first-class  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0359` **QA** — QA: Test plan và automated tests — giữ tour nội bộ như một adapter first-class  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0071 — Là Tour Operator, tôi muốn cung cấp availability/confirm/cancel qua portal nếu chưa có API để vẫn vận hành được supplier thủ công.

- **Priority:** P0
- **Tags:** SupplierAdapter, Admin, FE
- **Acceptance criteria:** Given Tour Operator có quyền hợp lệ; When cung cấp availability/confirm/cancel qua portal nếu chưa có API; Then kết quả giúp vẫn vận hành được supplier thủ công; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0360` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — cung cấp availability/confirm/cancel qua portal nếu chưa có API  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0361` **UX** — UX: Thiết kế wireframe/UI states — cung cấp availability/confirm/cancel qua portal nếu chưa có API  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0362` **FE** — FE: Implement UI và client integration — cung cấp availability/confirm/cancel qua portal nếu chưa có API  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0363` **BE** — BE: Thiết kế domain/API/schema và implement service — cung cấp availability/confirm/cancel qua portal nếu chưa có API  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0364` **Integration** — Integration: Implement adapter/contract test/mock — cung cấp availability/confirm/cancel qua portal nếu chưa có API  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0365` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — cung cấp availability/confirm/cancel qua portal nếu chưa có API  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0366` **QA** — QA: Test plan và automated tests — cung cấp availability/confirm/cancel qua portal nếu chưa có API  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0072 — Là Ops, tôi muốn theo dõi pending supplier confirmation SLA để không bỏ sót booking chờ xác nhận.

- **Priority:** P0
- **Tags:** Ops, SupplierAdapter, Notification
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When theo dõi pending supplier confirmation SLA; Then kết quả giúp không bỏ sót booking chờ xác nhận; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0367` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — theo dõi pending supplier confirmation SLA  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0368` **BE** — BE: Thiết kế domain/API/schema và implement service — theo dõi pending supplier confirmation SLA  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0369` **Integration** — Integration: Implement adapter/contract test/mock — theo dõi pending supplier confirmation SLA  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0370` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — theo dõi pending supplier confirmation SLA  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0371` **QA** — QA: Test plan và automated tests — theo dõi pending supplier confirmation SLA  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E020 — Flight adapter

**Objective:** Flight search/price/order thông qua adapter, không gắn chặt Amadeus/Skyscanner.  
**Priority:** P1  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0073 — Là Traveller, tôi muốn search flight offers từ provider adapter để cross-sell chuyến bay cho tour.

- **Priority:** P1
- **Tags:** Flight, SupplierAdapter, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When search flight offers từ provider adapter; Then kết quả giúp cross-sell chuyến bay cho tour; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0372` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — search flight offers từ provider adapter  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0373` **UX** — UX: Thiết kế wireframe/UI states — search flight offers từ provider adapter  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0374` **FE** — FE: Implement UI và client integration — search flight offers từ provider adapter  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0375` **BE** — BE: Thiết kế domain/API/schema và implement service — search flight offers từ provider adapter  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0376` **Integration** — Integration: Implement adapter/contract test/mock — search flight offers từ provider adapter  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0377` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — search flight offers từ provider adapter  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0378` **QA** — QA: Test plan và automated tests — search flight offers từ provider adapter  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0074 — Là Traveller, tôi muốn price flight offer và lock fare theo TTL nếu provider hỗ trợ để tránh giá thay đổi khi thanh toán.

- **Priority:** P1
- **Tags:** Flight, Pricing, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When price flight offer và lock fare theo TTL nếu provider hỗ trợ; Then kết quả giúp tránh giá thay đổi khi thanh toán; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0379` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — price flight offer và lock fare theo TTL nếu provider hỗ trợ  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0380` **BE** — BE: Thiết kế domain/API/schema và implement service — price flight offer và lock fare theo TTL nếu provider hỗ trợ  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0381` **Integration** — Integration: Implement adapter/contract test/mock — price flight offer và lock fare theo TTL nếu provider hỗ trợ  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0382` **QA** — QA: Test plan và automated tests — price flight offer và lock fare theo TTL nếu provider hỗ trợ  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0075 — Là System, tôi muốn lưu external flight order/ticketing status để đồng bộ đúng với supplier.

- **Priority:** P1
- **Tags:** Flight, Booking, BE
- **Acceptance criteria:** Given System có quyền hợp lệ; When lưu external flight order/ticketing status; Then kết quả giúp đồng bộ đúng với supplier; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0383` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — lưu external flight order/ticketing status  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0384` **BE** — BE: Thiết kế domain/API/schema và implement service — lưu external flight order/ticketing status  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0385` **Integration** — Integration: Implement adapter/contract test/mock — lưu external flight order/ticketing status  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0386` **QA** — QA: Test plan và automated tests — lưu external flight order/ticketing status  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0076 — Là QA, tôi muốn test sandbox Amadeus hoặc provider tương đương để giảm lỗi booking flight.

- **Priority:** P1
- **Tags:** Flight, QA, SupplierAdapter
- **Acceptance criteria:** Given QA có quyền hợp lệ; When test sandbox Amadeus hoặc provider tương đương; Then kết quả giúp giảm lỗi booking flight; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0387` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — test sandbox Amadeus hoặc provider tương đương  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0388` **BE** — BE: Thiết kế domain/API/schema và implement service — test sandbox Amadeus hoặc provider tương đương  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0389` **Integration** — Integration: Implement adapter/contract test/mock — test sandbox Amadeus hoặc provider tương đương  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0390` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — test sandbox Amadeus hoặc provider tương đương  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0391` **QA** — QA: Test plan và automated tests — test sandbox Amadeus hoặc provider tương đương  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E021 — Hotel adapter

**Objective:** Hotel search/rate/booking/cancel thông qua adapter và policy snapshot.  
**Priority:** P1  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0077 — Là Traveller, tôi muốn search hotel availability theo destination/date/guest để cross-sell hotel.

- **Priority:** P1
- **Tags:** Hotel, SupplierAdapter, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When search hotel availability theo destination/date/guest; Then kết quả giúp cross-sell hotel; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0392` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — search hotel availability theo destination/date/guest  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0393` **UX** — UX: Thiết kế wireframe/UI states — search hotel availability theo destination/date/guest  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0394` **FE** — FE: Implement UI và client integration — search hotel availability theo destination/date/guest  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0395` **BE** — BE: Thiết kế domain/API/schema và implement service — search hotel availability theo destination/date/guest  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0396` **Integration** — Integration: Implement adapter/contract test/mock — search hotel availability theo destination/date/guest  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0397` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — search hotel availability theo destination/date/guest  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0398` **QA** — QA: Test plan và automated tests — search hotel availability theo destination/date/guest  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0078 — Là Traveller, tôi muốn xem rate plan, taxes/fees và cancellation policy để đặt phòng không hiểu sai điều kiện.

- **Priority:** P1
- **Tags:** Hotel, Policy, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When xem rate plan, taxes/fees và cancellation policy; Then kết quả giúp đặt phòng không hiểu sai điều kiện; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0399` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem rate plan, taxes/fees và cancellation policy  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0400` **UX** — UX: Thiết kế wireframe/UI states — xem rate plan, taxes/fees và cancellation policy  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0401` **FE** — FE: Implement UI và client integration — xem rate plan, taxes/fees và cancellation policy  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0402` **BE** — BE: Thiết kế domain/API/schema và implement service — xem rate plan, taxes/fees và cancellation policy  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0403` **Integration** — Integration: Implement adapter/contract test/mock — xem rate plan, taxes/fees và cancellation policy  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0404` **QA** — QA: Test plan và automated tests — xem rate plan, taxes/fees và cancellation policy  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0079 — Là System, tôi muốn confirm hotel reservation và lưu supplier reference để trạng thái booking đồng bộ.

- **Priority:** P1
- **Tags:** Hotel, Booking, BE
- **Acceptance criteria:** Given System có quyền hợp lệ; When confirm hotel reservation và lưu supplier reference; Then kết quả giúp trạng thái booking đồng bộ; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0405` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — confirm hotel reservation và lưu supplier reference  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0406` **BE** — BE: Thiết kế domain/API/schema và implement service — confirm hotel reservation và lưu supplier reference  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0407` **Integration** — Integration: Implement adapter/contract test/mock — confirm hotel reservation và lưu supplier reference  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0408` **QA** — QA: Test plan và automated tests — confirm hotel reservation và lưu supplier reference  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0080 — Là Integration Lead, tôi muốn gating Booking.com/Agoda adapter theo partner readiness để không giả định có API production.

- **Priority:** P1
- **Tags:** Hotel, SupplierAdapter, BA
- **Acceptance criteria:** Given Integration Lead có quyền hợp lệ; When gating Booking.com/Agoda adapter theo partner readiness; Then kết quả giúp không giả định có API production; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0409` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — gating Booking.com/Agoda adapter theo partner readiness  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0410` **BE** — BE: Thiết kế domain/API/schema và implement service — gating Booking.com/Agoda adapter theo partner readiness  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0411` **Integration** — Integration: Implement adapter/contract test/mock — gating Booking.com/Agoda adapter theo partner readiness  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0412` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — gating Booking.com/Agoda adapter theo partner readiness  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0413` **QA** — QA: Test plan và automated tests — gating Booking.com/Agoda adapter theo partner readiness  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E022 — Car, transfer, activities and insurance adapters

**Objective:** Mở rộng sản phẩm phụ trợ qua cùng supplier contract.  
**Priority:** P2  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0081 — Là Traveller, tôi muốn book airport transfer với pickup/dropoff/vehicle type để hoàn thiện chuyến đi.

- **Priority:** P2
- **Tags:** Car, SupplierAdapter, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When book airport transfer với pickup/dropoff/vehicle type; Then kết quả giúp hoàn thiện chuyến đi; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0414` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — book airport transfer với pickup/dropoff/vehicle type  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0415` **UX** — UX: Thiết kế wireframe/UI states — book airport transfer với pickup/dropoff/vehicle type  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0416` **FE** — FE: Implement UI và client integration — book airport transfer với pickup/dropoff/vehicle type  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0417` **BE** — BE: Thiết kế domain/API/schema và implement service — book airport transfer với pickup/dropoff/vehicle type  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0418` **Integration** — Integration: Implement adapter/contract test/mock — book airport transfer với pickup/dropoff/vehicle type  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0419` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — book airport transfer với pickup/dropoff/vehicle type  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0420` **QA** — QA: Test plan và automated tests — book airport transfer với pickup/dropoff/vehicle type  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0082 — Là Traveller, tôi muốn book activity/ticket addon trong itinerary để tăng AOV.

- **Priority:** P2
- **Tags:** Activities, SupplierAdapter, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When book activity/ticket addon trong itinerary; Then kết quả giúp tăng AOV; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0421` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — book activity/ticket addon trong itinerary  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0422` **UX** — UX: Thiết kế wireframe/UI states — book activity/ticket addon trong itinerary  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0423` **FE** — FE: Implement UI và client integration — book activity/ticket addon trong itinerary  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0424` **BE** — BE: Thiết kế domain/API/schema và implement service — book activity/ticket addon trong itinerary  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0425` **Integration** — Integration: Implement adapter/contract test/mock — book activity/ticket addon trong itinerary  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0426` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — book activity/ticket addon trong itinerary  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0427` **QA** — QA: Test plan và automated tests — book activity/ticket addon trong itinerary  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0083 — Là Traveller, tôi muốn mua travel insurance addon nếu partner hỗ trợ để giảm rủi ro chuyến đi.

- **Priority:** P3
- **Tags:** Insurance, SupplierAdapter, Legal, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When mua travel insurance addon nếu partner hỗ trợ; Then kết quả giúp giảm rủi ro chuyến đi; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0428` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — mua travel insurance addon nếu partner hỗ trợ  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0429` **BE** — BE: Thiết kế domain/API/schema và implement service — mua travel insurance addon nếu partner hỗ trợ  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0430` **Integration** — Integration: Implement adapter/contract test/mock — mua travel insurance addon nếu partner hỗ trợ  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0431` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — mua travel insurance addon nếu partner hỗ trợ  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0432` **QA** — QA: Test plan và automated tests — mua travel insurance addon nếu partner hỗ trợ  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0084 — Là Ops, tôi muốn quản lý manual fallback khi supplier local chưa có API để vẫn đảm bảo fulfilment.

- **Priority:** P1
- **Tags:** Ops, SupplierAdapter, Admin
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When quản lý manual fallback khi supplier local chưa có API; Then kết quả giúp vẫn đảm bảo fulfilment; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0433` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — quản lý manual fallback khi supplier local chưa có API  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0434` **UX** — UX: Thiết kế wireframe/UI states — quản lý manual fallback khi supplier local chưa có API  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0435` **FE** — FE: Implement UI và client integration — quản lý manual fallback khi supplier local chưa có API  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0436` **BE** — BE: Thiết kế domain/API/schema và implement service — quản lý manual fallback khi supplier local chưa có API  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0437` **Integration** — Integration: Implement adapter/contract test/mock — quản lý manual fallback khi supplier local chưa có API  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0438` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — quản lý manual fallback khi supplier local chưa có API  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0439` **QA** — QA: Test plan và automated tests — quản lý manual fallback khi supplier local chưa có API  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP07 — Quote, Pricing, Availability & Policy Engine

**Owner:** Pricing Lead

## CT-E023 — Quote engine

**Objective:** Tạo quote snapshot bất biến, có TTL, breakdown và source rõ ràng.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0085 — Là Traveller, tôi muốn nhận quote tổng tiền theo pax, ngày đi, sản phẩm và addon để biết chính xác phải trả gì.

- **Priority:** P0
- **Tags:** Quote, Pricing, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When nhận quote tổng tiền theo pax, ngày đi, sản phẩm và addon; Then kết quả giúp biết chính xác phải trả gì; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0440` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — nhận quote tổng tiền theo pax, ngày đi, sản phẩm và addon  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0441` **UX** — UX: Thiết kế wireframe/UI states — nhận quote tổng tiền theo pax, ngày đi, sản phẩm và addon  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0442` **FE** — FE: Implement UI và client integration — nhận quote tổng tiền theo pax, ngày đi, sản phẩm và addon  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0443` **BE** — BE: Thiết kế domain/API/schema và implement service — nhận quote tổng tiền theo pax, ngày đi, sản phẩm và addon  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0444` **QA** — QA: Test plan và automated tests — nhận quote tổng tiền theo pax, ngày đi, sản phẩm và addon  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0086 — Là System, tôi muốn quote có TTL và policy snapshot để tránh tranh chấp giá/chính sách.

- **Priority:** P0
- **Tags:** Quote, Policy, BE
- **Acceptance criteria:** Given System có quyền hợp lệ; When quote có TTL và policy snapshot; Then kết quả giúp tránh tranh chấp giá/chính sách; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0445` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — quote có TTL và policy snapshot  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0446` **BE** — BE: Thiết kế domain/API/schema và implement service — quote có TTL và policy snapshot  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0447` **QA** — QA: Test plan và automated tests — quote có TTL và policy snapshot  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0087 — Là AI Assistant, tôi muốn dùng quote tool thay vì tự tính giá để AI không tính sai tiền.

- **Priority:** P0
- **Tags:** Quote, AI, Tool
- **Acceptance criteria:** Given AI Assistant có quyền hợp lệ; When dùng quote tool thay vì tự tính giá; Then kết quả giúp AI không tính sai tiền; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0448` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — dùng quote tool thay vì tự tính giá  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0449` **BE** — BE: Thiết kế domain/API/schema và implement service — dùng quote tool thay vì tự tính giá  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0450` **AI** — AI: Thiết kế prompt/tool schema/eval cases — dùng quote tool thay vì tự tính giá  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0451` **Security** — Security: Threat model và security control — dùng quote tool thay vì tự tính giá  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0452` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — dùng quote tool thay vì tự tính giá  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0453` **QA** — QA: Test plan và automated tests — dùng quote tool thay vì tự tính giá  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0088 — Là QA, tôi muốn test quote deterministic cho cùng input để tránh sai lệch giá.

- **Priority:** P0
- **Tags:** Quote, QA, BE
- **Acceptance criteria:** Given QA có quyền hợp lệ; When test quote deterministic cho cùng input; Then kết quả giúp tránh sai lệch giá; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0454` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — test quote deterministic cho cùng input  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0455` **BE** — BE: Thiết kế domain/API/schema và implement service — test quote deterministic cho cùng input  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0456` **QA** — QA: Test plan và automated tests — test quote deterministic cho cùng input  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E024 — Availability and inventory ledger

**Objective:** Không oversell khi nhiều user/agent/supplier thao tác đồng thời.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0089 — Là Traveller, tôi muốn xem trạng thái còn chỗ/sắp hết/hết chỗ real-time enough để ra quyết định nhanh.

- **Priority:** P0
- **Tags:** Availability, FE, BE, SRE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When xem trạng thái còn chỗ/sắp hết/hết chỗ real-time enough; Then kết quả giúp ra quyết định nhanh; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0457` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem trạng thái còn chỗ/sắp hết/hết chỗ real-time enough  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0458` **UX** — UX: Thiết kế wireframe/UI states — xem trạng thái còn chỗ/sắp hết/hết chỗ real-time enough  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0459` **FE** — FE: Implement UI và client integration — xem trạng thái còn chỗ/sắp hết/hết chỗ real-time enough  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0460` **BE** — BE: Thiết kế domain/API/schema và implement service — xem trạng thái còn chỗ/sắp hết/hết chỗ real-time enough  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0461` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — xem trạng thái còn chỗ/sắp hết/hết chỗ real-time enough  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0462` **QA** — QA: Test plan và automated tests — xem trạng thái còn chỗ/sắp hết/hết chỗ real-time enough  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0090 — Là System, tôi muốn hold inventory theo quote/booking với expiry để bảo vệ chỗ trong thời gian thanh toán.

- **Priority:** P0
- **Tags:** Inventory, Booking, BE
- **Acceptance criteria:** Given System có quyền hợp lệ; When hold inventory theo quote/booking với expiry; Then kết quả giúp bảo vệ chỗ trong thời gian thanh toán; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0463` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — hold inventory theo quote/booking với expiry  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0464` **BE** — BE: Thiết kế domain/API/schema và implement service — hold inventory theo quote/booking với expiry  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0465` **QA** — QA: Test plan và automated tests — hold inventory theo quote/booking với expiry  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0091 — Là System, tôi muốn dùng ledger thay vì chỉ decrement counter để audit được mọi thay đổi chỗ.

- **Priority:** P0
- **Tags:** Inventory, BE, Data
- **Acceptance criteria:** Given System có quyền hợp lệ; When dùng ledger thay vì chỉ decrement counter; Then kết quả giúp audit được mọi thay đổi chỗ; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0466` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — dùng ledger thay vì chỉ decrement counter  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0467` **BE** — BE: Thiết kế domain/API/schema và implement service — dùng ledger thay vì chỉ decrement counter  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0468` **Data** — Data: Event taxonomy/data model/dashboard metric — dùng ledger thay vì chỉ decrement counter  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0469` **QA** — QA: Test plan và automated tests — dùng ledger thay vì chỉ decrement counter  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0092 — Là QA, tôi muốn chạy race test nhiều booking đồng thời để chứng minh no-oversell.

- **Priority:** P0
- **Tags:** Inventory, QA, SRE
- **Acceptance criteria:** Given QA có quyền hợp lệ; When chạy race test nhiều booking đồng thời; Then kết quả giúp chứng minh no-oversell; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy. NFR: concurrency test >=500 parallel attempts per hot departure.
- **NFR/SLO:** concurrency test >=500 parallel attempts per hot departure
- **Tickets:**
  - `CT-T0470` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — chạy race test nhiều booking đồng thời  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0471` **BE** — BE: Thiết kế domain/API/schema và implement service — chạy race test nhiều booking đồng thời  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0472` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — chạy race test nhiều booking đồng thời  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0473` **QA** — QA: Test plan và automated tests — chạy race test nhiều booking đồng thời  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E025 — Policy, fee, tax and commission rules

**Objective:** Chuẩn hóa rule tính phí, thuế, commission, cancellation và refund.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0093 — Là Finance, tôi muốn cấu hình commission theo supplier/product/channel để tính unit economics đúng.

- **Priority:** P0
- **Tags:** Pricing, Finance, BE
- **Acceptance criteria:** Given Finance có quyền hợp lệ; When cấu hình commission theo supplier/product/channel; Then kết quả giúp tính unit economics đúng; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0474` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — cấu hình commission theo supplier/product/channel  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0475` **BE** — BE: Thiết kế domain/API/schema và implement service — cấu hình commission theo supplier/product/channel  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0476` **Data** — Data: Event taxonomy/data model/dashboard metric — cấu hình commission theo supplier/product/channel  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0477` **QA** — QA: Test plan và automated tests — cấu hình commission theo supplier/product/channel  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0094 — Là Traveller, tôi muốn xem phí/tax/surcharge tách bạch trước khi trả tiền để minh bạch giá.

- **Priority:** P0
- **Tags:** Pricing, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When xem phí/tax/surcharge tách bạch trước khi trả tiền; Then kết quả giúp minh bạch giá; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0478` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem phí/tax/surcharge tách bạch trước khi trả tiền  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0479` **UX** — UX: Thiết kế wireframe/UI states — xem phí/tax/surcharge tách bạch trước khi trả tiền  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0480` **FE** — FE: Implement UI và client integration — xem phí/tax/surcharge tách bạch trước khi trả tiền  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0481` **BE** — BE: Thiết kế domain/API/schema và implement service — xem phí/tax/surcharge tách bạch trước khi trả tiền  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0482` **QA** — QA: Test plan và automated tests — xem phí/tax/surcharge tách bạch trước khi trả tiền  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0095 — Là Ops, tôi muốn áp chính sách cancellation/refund theo snapshot để xử lý tranh chấp công bằng.

- **Priority:** P0
- **Tags:** Policy, Ops, BE
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When áp chính sách cancellation/refund theo snapshot; Then kết quả giúp xử lý tranh chấp công bằng; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0483` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — áp chính sách cancellation/refund theo snapshot  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0484` **BE** — BE: Thiết kế domain/API/schema và implement service — áp chính sách cancellation/refund theo snapshot  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0485` **QA** — QA: Test plan và automated tests — áp chính sách cancellation/refund theo snapshot  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0096 — Là Admin, tôi muốn version và approve rule thay đổi để tránh sai rule production.

- **Priority:** P1
- **Tags:** Policy, Admin, Audit
- **Acceptance criteria:** Given Admin có quyền hợp lệ; When version và approve rule thay đổi; Then kết quả giúp tránh sai rule production; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0486` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — version và approve rule thay đổi  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0487` **UX** — UX: Thiết kế wireframe/UI states — version và approve rule thay đổi  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0488` **FE** — FE: Implement UI và client integration — version và approve rule thay đổi  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0489` **BE** — BE: Thiết kế domain/API/schema và implement service — version và approve rule thay đổi  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0490` **QA** — QA: Test plan và automated tests — version và approve rule thay đổi  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP08 — Booking, Reservation, Cancellation & Voucher

**Owner:** Booking Lead

## CT-E026 — Booking lifecycle state machine

**Objective:** Quản lý booking multi-product từ draft đến confirmed/completed/cancelled/refunded.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0097 — Là Traveller, tôi muốn tạo draft booking từ quote để giữ lựa chọn trước khi thanh toán.

- **Priority:** P0
- **Tags:** Booking, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When tạo draft booking từ quote; Then kết quả giúp giữ lựa chọn trước khi thanh toán; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0491` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tạo draft booking từ quote  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0492` **UX** — UX: Thiết kế wireframe/UI states — tạo draft booking từ quote  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0493` **FE** — FE: Implement UI và client integration — tạo draft booking từ quote  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0494` **BE** — BE: Thiết kế domain/API/schema và implement service — tạo draft booking từ quote  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0495` **QA** — QA: Test plan và automated tests — tạo draft booking từ quote  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0098 — Là System, tôi muốn chuyển trạng thái booking theo state machine hợp lệ để ngăn trạng thái sai.

- **Priority:** P0
- **Tags:** Booking, BE, QA
- **Acceptance criteria:** Given System có quyền hợp lệ; When chuyển trạng thái booking theo state machine hợp lệ; Then kết quả giúp ngăn trạng thái sai; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0496` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — chuyển trạng thái booking theo state machine hợp lệ  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0497` **BE** — BE: Thiết kế domain/API/schema và implement service — chuyển trạng thái booking theo state machine hợp lệ  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0498` **QA** — QA: Test plan và automated tests — chuyển trạng thái booking theo state machine hợp lệ  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0099 — Là System, tôi muốn xử lý saga confirm supplier + payment + voucher để đảm bảo booking đúng với nhà cung cấp.

- **Priority:** P0
- **Tags:** Booking, Saga, SupplierAdapter, Payment
- **Acceptance criteria:** Given System có quyền hợp lệ; When xử lý saga confirm supplier + payment + voucher; Then kết quả giúp đảm bảo booking đúng với nhà cung cấp; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0499` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xử lý saga confirm supplier + payment + voucher  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0500` **BE** — BE: Thiết kế domain/API/schema và implement service — xử lý saga confirm supplier + payment + voucher  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0501` **Integration** — Integration: Implement adapter/contract test/mock — xử lý saga confirm supplier + payment + voucher  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0502` **Security** — Security: Threat model và security control — xử lý saga confirm supplier + payment + voucher  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0503` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — xử lý saga confirm supplier + payment + voucher  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0504` **QA** — QA: Test plan và automated tests — xử lý saga confirm supplier + payment + voucher  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0100 — Là Ops, tôi muốn xem toàn bộ timeline trạng thái booking để debug và hỗ trợ khách.

- **Priority:** P0
- **Tags:** Booking, Ops, Admin
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When xem toàn bộ timeline trạng thái booking; Then kết quả giúp debug và hỗ trợ khách; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0505` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem toàn bộ timeline trạng thái booking  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0506` **UX** — UX: Thiết kế wireframe/UI states — xem toàn bộ timeline trạng thái booking  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0507` **FE** — FE: Implement UI và client integration — xem toàn bộ timeline trạng thái booking  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0508` **BE** — BE: Thiết kế domain/API/schema và implement service — xem toàn bộ timeline trạng thái booking  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0509` **QA** — QA: Test plan và automated tests — xem toàn bộ timeline trạng thái booking  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E027 — Traveller details, pax and documents

**Objective:** Thu thập thông tin hành khách phù hợp sản phẩm, có PII protection.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0101 — Là Traveller, tôi muốn nhập pax info theo yêu cầu tour/flight/hotel để đủ dữ liệu để supplier confirm.

- **Priority:** P0
- **Tags:** Booking, PII, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When nhập pax info theo yêu cầu tour/flight/hotel; Then kết quả giúp đủ dữ liệu để supplier confirm; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0510` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — nhập pax info theo yêu cầu tour/flight/hotel  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0511` **UX** — UX: Thiết kế wireframe/UI states — nhập pax info theo yêu cầu tour/flight/hotel  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0512` **FE** — FE: Implement UI và client integration — nhập pax info theo yêu cầu tour/flight/hotel  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0513` **BE** — BE: Thiết kế domain/API/schema và implement service — nhập pax info theo yêu cầu tour/flight/hotel  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0514` **Security** — Security: Threat model và security control — nhập pax info theo yêu cầu tour/flight/hotel  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0515` **QA** — QA: Test plan và automated tests — nhập pax info theo yêu cầu tour/flight/hotel  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0102 — Là Traveller, tôi muốn upload giấy tờ cần thiết nếu tour yêu cầu để hoàn thiện hồ sơ đặt tour.

- **Priority:** P1
- **Tags:** Booking, Media, PII, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When upload giấy tờ cần thiết nếu tour yêu cầu; Then kết quả giúp hoàn thiện hồ sơ đặt tour; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0516` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — upload giấy tờ cần thiết nếu tour yêu cầu  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0517` **UX** — UX: Thiết kế wireframe/UI states — upload giấy tờ cần thiết nếu tour yêu cầu  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0518` **FE** — FE: Implement UI và client integration — upload giấy tờ cần thiết nếu tour yêu cầu  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0519` **BE** — BE: Thiết kế domain/API/schema và implement service — upload giấy tờ cần thiết nếu tour yêu cầu  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0520` **Security** — Security: Threat model và security control — upload giấy tờ cần thiết nếu tour yêu cầu  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0521` **QA** — QA: Test plan và automated tests — upload giấy tờ cần thiết nếu tour yêu cầu  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0103 — Là System, tôi muốn mã hóa/ẩn PII trong log và audit để bảo vệ dữ liệu cá nhân.

- **Priority:** P0
- **Tags:** Security, PII, BE, SRE
- **Acceptance criteria:** Given System có quyền hợp lệ; When mã hóa/ẩn PII trong log và audit; Then kết quả giúp bảo vệ dữ liệu cá nhân; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0522` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — mã hóa/ẩn PII trong log và audit  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0523` **BE** — BE: Thiết kế domain/API/schema và implement service — mã hóa/ẩn PII trong log và audit  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0524` **Security** — Security: Threat model và security control — mã hóa/ẩn PII trong log và audit  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0525` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — mã hóa/ẩn PII trong log và audit  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0526` **QA** — QA: Test plan và automated tests — mã hóa/ẩn PII trong log và audit  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0104 — Là Support, tôi muốn xem PII theo permission và reason để hỗ trợ nhưng không lộ dữ liệu.

- **Priority:** P0
- **Tags:** RBAC, PII, Admin
- **Acceptance criteria:** Given Support có quyền hợp lệ; When xem PII theo permission và reason; Then kết quả giúp hỗ trợ nhưng không lộ dữ liệu; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0527` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem PII theo permission và reason  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0528` **UX** — UX: Thiết kế wireframe/UI states — xem PII theo permission và reason  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0529` **FE** — FE: Implement UI và client integration — xem PII theo permission và reason  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0530` **BE** — BE: Thiết kế domain/API/schema và implement service — xem PII theo permission và reason  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0531` **Security** — Security: Threat model và security control — xem PII theo permission và reason  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0532` **QA** — QA: Test plan và automated tests — xem PII theo permission và reason  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E028 — Multi-product trip cart and itinerary

**Objective:** Một trip có thể gồm tour, hotel, flight, transfer, activity với fulfillment riêng.  
**Priority:** P1  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0105 — Là Traveller, tôi muốn gom nhiều sản phẩm vào một trip plan để xem toàn bộ chuyến đi trong một chỗ.

- **Priority:** P1
- **Tags:** Booking, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When gom nhiều sản phẩm vào một trip plan; Then kết quả giúp xem toàn bộ chuyến đi trong một chỗ; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0533` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — gom nhiều sản phẩm vào một trip plan  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0534` **UX** — UX: Thiết kế wireframe/UI states — gom nhiều sản phẩm vào một trip plan  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0535` **FE** — FE: Implement UI và client integration — gom nhiều sản phẩm vào một trip plan  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0536` **BE** — BE: Thiết kế domain/API/schema và implement service — gom nhiều sản phẩm vào một trip plan  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0537` **QA** — QA: Test plan và automated tests — gom nhiều sản phẩm vào một trip plan  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0106 — Là System, tôi muốn theo dõi reservation status từng item để xử lý partial failure.

- **Priority:** P1
- **Tags:** Booking, Saga, BE
- **Acceptance criteria:** Given System có quyền hợp lệ; When theo dõi reservation status từng item; Then kết quả giúp xử lý partial failure; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0538` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — theo dõi reservation status từng item  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0539` **BE** — BE: Thiết kế domain/API/schema và implement service — theo dõi reservation status từng item  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0540` **QA** — QA: Test plan và automated tests — theo dõi reservation status từng item  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0107 — Là Ops, tôi muốn xử lý partial refund/rebook cho từng item để giảm thiệt hại khi lỗi supplier.

- **Priority:** P1
- **Tags:** Booking, Ops, Payment
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When xử lý partial refund/rebook cho từng item; Then kết quả giúp giảm thiệt hại khi lỗi supplier; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0541` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xử lý partial refund/rebook cho từng item  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0542` **BE** — BE: Thiết kế domain/API/schema và implement service — xử lý partial refund/rebook cho từng item  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0543` **Security** — Security: Threat model và security control — xử lý partial refund/rebook cho từng item  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0544` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — xử lý partial refund/rebook cho từng item  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0545` **QA** — QA: Test plan và automated tests — xử lý partial refund/rebook cho từng item  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0108 — Là AI Assistant, tôi muốn giải thích itinerary multi-product bằng ngôn ngữ tự nhiên để khách hiểu gói đã chọn.

- **Priority:** P2
- **Tags:** AI, Booking, FE
- **Acceptance criteria:** Given AI Assistant có quyền hợp lệ; When giải thích itinerary multi-product bằng ngôn ngữ tự nhiên; Then kết quả giúp khách hiểu gói đã chọn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0546` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — giải thích itinerary multi-product bằng ngôn ngữ tự nhiên  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0547` **UX** — UX: Thiết kế wireframe/UI states — giải thích itinerary multi-product bằng ngôn ngữ tự nhiên  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0548` **FE** — FE: Implement UI và client integration — giải thích itinerary multi-product bằng ngôn ngữ tự nhiên  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0549` **BE** — BE: Thiết kế domain/API/schema và implement service — giải thích itinerary multi-product bằng ngôn ngữ tự nhiên  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0550` **AI** — AI: Thiết kế prompt/tool schema/eval cases — giải thích itinerary multi-product bằng ngôn ngữ tự nhiên  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0551` **Security** — Security: Threat model và security control — giải thích itinerary multi-product bằng ngôn ngữ tự nhiên  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0552` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — giải thích itinerary multi-product bằng ngôn ngữ tự nhiên  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0553` **QA** — QA: Test plan và automated tests — giải thích itinerary multi-product bằng ngôn ngữ tự nhiên  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E029 — Cancellation, refund and change request

**Objective:** User tự xem refund quote, gửi hủy/đổi ngày, ops xử lý exception.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0109 — Là Traveller, tôi muốn preview refund amount trước khi cancel để không hủy nhầm.

- **Priority:** P0
- **Tags:** Refund, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When preview refund amount trước khi cancel; Then kết quả giúp không hủy nhầm; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0554` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — preview refund amount trước khi cancel  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0555` **UX** — UX: Thiết kế wireframe/UI states — preview refund amount trước khi cancel  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0556` **FE** — FE: Implement UI và client integration — preview refund amount trước khi cancel  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0557` **BE** — BE: Thiết kế domain/API/schema và implement service — preview refund amount trước khi cancel  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0558` **QA** — QA: Test plan và automated tests — preview refund amount trước khi cancel  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0110 — Là Traveller, tôi muốn gửi yêu cầu đổi ngày/đổi pax để linh hoạt sau khi đặt.

- **Priority:** P1
- **Tags:** Booking, Ops, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When gửi yêu cầu đổi ngày/đổi pax; Then kết quả giúp linh hoạt sau khi đặt; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0559` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — gửi yêu cầu đổi ngày/đổi pax  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0560` **UX** — UX: Thiết kế wireframe/UI states — gửi yêu cầu đổi ngày/đổi pax  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0561` **FE** — FE: Implement UI và client integration — gửi yêu cầu đổi ngày/đổi pax  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0562` **BE** — BE: Thiết kế domain/API/schema và implement service — gửi yêu cầu đổi ngày/đổi pax  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0563` **QA** — QA: Test plan và automated tests — gửi yêu cầu đổi ngày/đổi pax  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0111 — Là System, tôi muốn release inventory và gọi supplier cancel khi hủy để không giữ chỗ thừa.

- **Priority:** P0
- **Tags:** Booking, SupplierAdapter, BE
- **Acceptance criteria:** Given System có quyền hợp lệ; When release inventory và gọi supplier cancel khi hủy; Then kết quả giúp không giữ chỗ thừa; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0564` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — release inventory và gọi supplier cancel khi hủy  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0565` **BE** — BE: Thiết kế domain/API/schema và implement service — release inventory và gọi supplier cancel khi hủy  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0566` **Integration** — Integration: Implement adapter/contract test/mock — release inventory và gọi supplier cancel khi hủy  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0567` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — release inventory và gọi supplier cancel khi hủy  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0568` **QA** — QA: Test plan và automated tests — release inventory và gọi supplier cancel khi hủy  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0112 — Là Finance, tôi muốn tạo refund transaction và đối soát để khớp sổ tài chính.

- **Priority:** P0
- **Tags:** Payment, Finance, BE
- **Acceptance criteria:** Given Finance có quyền hợp lệ; When tạo refund transaction và đối soát; Then kết quả giúp khớp sổ tài chính; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0569` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tạo refund transaction và đối soát  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0570` **BE** — BE: Thiết kế domain/API/schema và implement service — tạo refund transaction và đối soát  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0571` **Security** — Security: Threat model và security control — tạo refund transaction và đối soát  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0572` **Data** — Data: Event taxonomy/data model/dashboard metric — tạo refund transaction và đối soát  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0573` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — tạo refund transaction và đối soát  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0574` **QA** — QA: Test plan và automated tests — tạo refund transaction và đối soát  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E030 — Voucher, QR verification and offline proof

**Objective:** Voucher điện tử có QR, verify được, chống giả mạo và hỗ trợ offline basic.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0113 — Là Traveller, tôi muốn nhận voucher PDF/QR sau khi confirmed để có bằng chứng đi tour.

- **Priority:** P0
- **Tags:** Voucher, Notification, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When nhận voucher PDF/QR sau khi confirmed; Then kết quả giúp có bằng chứng đi tour; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0575` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — nhận voucher PDF/QR sau khi confirmed  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0576` **UX** — UX: Thiết kế wireframe/UI states — nhận voucher PDF/QR sau khi confirmed  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0577` **FE** — FE: Implement UI và client integration — nhận voucher PDF/QR sau khi confirmed  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0578` **BE** — BE: Thiết kế domain/API/schema và implement service — nhận voucher PDF/QR sau khi confirmed  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0579` **QA** — QA: Test plan và automated tests — nhận voucher PDF/QR sau khi confirmed  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0114 — Là Supplier, tôi muốn scan QR để verify voucher để xác nhận khách hợp lệ.

- **Priority:** P1
- **Tags:** Voucher, FE, BE, Security
- **Acceptance criteria:** Given Supplier có quyền hợp lệ; When scan QR để verify voucher; Then kết quả giúp xác nhận khách hợp lệ; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0580` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — scan QR để verify voucher  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0581` **UX** — UX: Thiết kế wireframe/UI states — scan QR để verify voucher  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0582` **FE** — FE: Implement UI và client integration — scan QR để verify voucher  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0583` **BE** — BE: Thiết kế domain/API/schema và implement service — scan QR để verify voucher  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0584` **Security** — Security: Threat model và security control — scan QR để verify voucher  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0585` **QA** — QA: Test plan và automated tests — scan QR để verify voucher  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0115 — Là System, tôi muốn signed voucher token không chứa PII nhạy cảm để giảm rủi ro lộ dữ liệu.

- **Priority:** P0
- **Tags:** Voucher, Security, BE
- **Acceptance criteria:** Given System có quyền hợp lệ; When signed voucher token không chứa PII nhạy cảm; Then kết quả giúp giảm rủi ro lộ dữ liệu; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0586` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — signed voucher token không chứa PII nhạy cảm  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0587` **BE** — BE: Thiết kế domain/API/schema và implement service — signed voucher token không chứa PII nhạy cảm  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0588` **Security** — Security: Threat model và security control — signed voucher token không chứa PII nhạy cảm  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0589` **QA** — QA: Test plan và automated tests — signed voucher token không chứa PII nhạy cảm  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0116 — Là Traveller, tôi muốn download voucher trong My Trips để dễ tìm khi cần.

- **Priority:** P0
- **Tags:** Voucher, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When download voucher trong My Trips; Then kết quả giúp dễ tìm khi cần; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0590` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — download voucher trong My Trips  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0591` **UX** — UX: Thiết kế wireframe/UI states — download voucher trong My Trips  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0592` **FE** — FE: Implement UI và client integration — download voucher trong My Trips  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0593` **BE** — BE: Thiết kế domain/API/schema và implement service — download voucher trong My Trips  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0594` **QA** — QA: Test plan và automated tests — download voucher trong My Trips  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP09 — Payment, Ledger, Settlement & Fraud

**Owner:** Payment/Finance Lead

## CT-E031 — Payment intent and hosted payment

**Objective:** Tạo payment flow an toàn, idempotent, giảm PCI scope.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0117 — Là Traveller, tôi muốn thanh toán booking qua hosted payment/redirect để trả tiền an toàn.

- **Priority:** P0
- **Tags:** Payment, FE, BE, Security
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When thanh toán booking qua hosted payment/redirect; Then kết quả giúp trả tiền an toàn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0595` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — thanh toán booking qua hosted payment/redirect  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0596` **UX** — UX: Thiết kế wireframe/UI states — thanh toán booking qua hosted payment/redirect  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0597` **FE** — FE: Implement UI và client integration — thanh toán booking qua hosted payment/redirect  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0598` **BE** — BE: Thiết kế domain/API/schema và implement service — thanh toán booking qua hosted payment/redirect  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0599` **Security** — Security: Threat model và security control — thanh toán booking qua hosted payment/redirect  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0600` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — thanh toán booking qua hosted payment/redirect  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0601` **QA** — QA: Test plan và automated tests — thanh toán booking qua hosted payment/redirect  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0118 — Là System, tôi muốn xử lý payment webhook có signature và replay protection để tránh confirm sai.

- **Priority:** P0
- **Tags:** Payment, Security, BE
- **Acceptance criteria:** Given System có quyền hợp lệ; When xử lý payment webhook có signature và replay protection; Then kết quả giúp tránh confirm sai; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0602` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xử lý payment webhook có signature và replay protection  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0603` **BE** — BE: Thiết kế domain/API/schema và implement service — xử lý payment webhook có signature và replay protection  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0604` **Security** — Security: Threat model và security control — xử lý payment webhook có signature và replay protection  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0605` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — xử lý payment webhook có signature và replay protection  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0606` **QA** — QA: Test plan và automated tests — xử lý payment webhook có signature và replay protection  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0119 — Là System, tôi muốn idempotent payment confirm/fail để không nhân đôi giao dịch.

- **Priority:** P0
- **Tags:** Payment, BE, QA
- **Acceptance criteria:** Given System có quyền hợp lệ; When idempotent payment confirm/fail; Then kết quả giúp không nhân đôi giao dịch; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0607` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — idempotent payment confirm/fail  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0608` **BE** — BE: Thiết kế domain/API/schema và implement service — idempotent payment confirm/fail  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0609` **Security** — Security: Threat model và security control — idempotent payment confirm/fail  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0610` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — idempotent payment confirm/fail  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0611` **QA** — QA: Test plan và automated tests — idempotent payment confirm/fail  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0120 — Là QA, tôi muốn test success/fail/timeout/duplicate webhook để payment flow ổn định.

- **Priority:** P0
- **Tags:** Payment, QA, BE
- **Acceptance criteria:** Given QA có quyền hợp lệ; When test success/fail/timeout/duplicate webhook; Then kết quả giúp payment flow ổn định; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0612` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — test success/fail/timeout/duplicate webhook  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0613` **BE** — BE: Thiết kế domain/API/schema và implement service — test success/fail/timeout/duplicate webhook  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0614` **Security** — Security: Threat model và security control — test success/fail/timeout/duplicate webhook  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0615` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — test success/fail/timeout/duplicate webhook  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0616` **QA** — QA: Test plan và automated tests — test success/fail/timeout/duplicate webhook  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E032 — Refund, settlement and reconciliation

**Objective:** Quản lý refund, đối soát cổng thanh toán và exception queue.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0121 — Là Finance, tôi muốn tạo refund theo refund quote đã approve để hoàn tiền đúng chính sách.

- **Priority:** P0
- **Tags:** Refund, Finance, BE
- **Acceptance criteria:** Given Finance có quyền hợp lệ; When tạo refund theo refund quote đã approve; Then kết quả giúp hoàn tiền đúng chính sách; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0617` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tạo refund theo refund quote đã approve  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0618` **BE** — BE: Thiết kế domain/API/schema và implement service — tạo refund theo refund quote đã approve  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0619` **Data** — Data: Event taxonomy/data model/dashboard metric — tạo refund theo refund quote đã approve  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0620` **QA** — QA: Test plan và automated tests — tạo refund theo refund quote đã approve  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0122 — Là Finance, tôi muốn import settlement file/API và match với ledger để đối soát tự động.

- **Priority:** P0
- **Tags:** Settlement, Data, BE
- **Acceptance criteria:** Given Finance có quyền hợp lệ; When import settlement file/API và match với ledger; Then kết quả giúp đối soát tự động; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0621` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — import settlement file/API và match với ledger  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0622` **BE** — BE: Thiết kế domain/API/schema và implement service — import settlement file/API và match với ledger  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0623` **Data** — Data: Event taxonomy/data model/dashboard metric — import settlement file/API và match với ledger  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0624` **QA** — QA: Test plan và automated tests — import settlement file/API và match với ledger  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0123 — Là Finance, tôi muốn xem exception queue cho giao dịch lệch để xử lý tiền sai nhanh.

- **Priority:** P0
- **Tags:** Settlement, Admin, FE, BE
- **Acceptance criteria:** Given Finance có quyền hợp lệ; When xem exception queue cho giao dịch lệch; Then kết quả giúp xử lý tiền sai nhanh; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0625` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem exception queue cho giao dịch lệch  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0626` **UX** — UX: Thiết kế wireframe/UI states — xem exception queue cho giao dịch lệch  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0627` **FE** — FE: Implement UI và client integration — xem exception queue cho giao dịch lệch  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0628` **BE** — BE: Thiết kế domain/API/schema và implement service — xem exception queue cho giao dịch lệch  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0629` **Data** — Data: Event taxonomy/data model/dashboard metric — xem exception queue cho giao dịch lệch  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0630` **QA** — QA: Test plan và automated tests — xem exception queue cho giao dịch lệch  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0124 — Là Ops, tôi muốn manual mark/payment adjustment cần approval để kiểm soát gian lận nội bộ.

- **Priority:** P1
- **Tags:** Finance, Security, Admin
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When manual mark/payment adjustment cần approval; Then kết quả giúp kiểm soát gian lận nội bộ; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0631` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — manual mark/payment adjustment cần approval  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0632` **UX** — UX: Thiết kế wireframe/UI states — manual mark/payment adjustment cần approval  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0633` **FE** — FE: Implement UI và client integration — manual mark/payment adjustment cần approval  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0634` **Security** — Security: Threat model và security control — manual mark/payment adjustment cần approval  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0635` **Data** — Data: Event taxonomy/data model/dashboard metric — manual mark/payment adjustment cần approval  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0636` **QA** — QA: Test plan và automated tests — manual mark/payment adjustment cần approval  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E033 — Immutable ledger, invoice and commission

**Objective:** Ghi nhận tiền, refund, commission, supplier payable bằng ledger bất biến.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0125 — Là Finance, tôi muốn xem ledger entry cho từng booking/payment/refund để kiểm tra dòng tiền.

- **Priority:** P0
- **Tags:** Ledger, Finance, FE, BE
- **Acceptance criteria:** Given Finance có quyền hợp lệ; When xem ledger entry cho từng booking/payment/refund; Then kết quả giúp kiểm tra dòng tiền; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0637` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem ledger entry cho từng booking/payment/refund  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0638` **UX** — UX: Thiết kế wireframe/UI states — xem ledger entry cho từng booking/payment/refund  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0639` **FE** — FE: Implement UI và client integration — xem ledger entry cho từng booking/payment/refund  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0640` **BE** — BE: Thiết kế domain/API/schema và implement service — xem ledger entry cho từng booking/payment/refund  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0641` **Data** — Data: Event taxonomy/data model/dashboard metric — xem ledger entry cho từng booking/payment/refund  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0642` **QA** — QA: Test plan và automated tests — xem ledger entry cho từng booking/payment/refund  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0126 — Là System, tôi muốn balance check double-entry ledger để không lệch sổ.

- **Priority:** P0
- **Tags:** Ledger, BE, QA
- **Acceptance criteria:** Given System có quyền hợp lệ; When balance check double-entry ledger; Then kết quả giúp không lệch sổ; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0643` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — balance check double-entry ledger  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0644` **BE** — BE: Thiết kế domain/API/schema và implement service — balance check double-entry ledger  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0645` **Data** — Data: Event taxonomy/data model/dashboard metric — balance check double-entry ledger  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0646` **QA** — QA: Test plan và automated tests — balance check double-entry ledger  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0127 — Là Agent, tôi muốn xem commission dự kiến và earned để biết doanh thu.

- **Priority:** P1
- **Tags:** Commission, B2B, FE, BE
- **Acceptance criteria:** Given Agent có quyền hợp lệ; When xem commission dự kiến và earned; Then kết quả giúp biết doanh thu; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0647` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem commission dự kiến và earned  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0648` **UX** — UX: Thiết kế wireframe/UI states — xem commission dự kiến và earned  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0649` **FE** — FE: Implement UI và client integration — xem commission dự kiến và earned  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0650` **BE** — BE: Thiết kế domain/API/schema và implement service — xem commission dự kiến và earned  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0651` **Data** — Data: Event taxonomy/data model/dashboard metric — xem commission dự kiến và earned  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0652` **QA** — QA: Test plan và automated tests — xem commission dự kiến và earned  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0128 — Là Finance, tôi muốn xuất receipt/invoice/tax document theo cấu hình để phục vụ kế toán.

- **Priority:** P1
- **Tags:** Finance, Document, BE
- **Acceptance criteria:** Given Finance có quyền hợp lệ; When xuất receipt/invoice/tax document theo cấu hình; Then kết quả giúp phục vụ kế toán; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0653` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xuất receipt/invoice/tax document theo cấu hình  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0654` **BE** — BE: Thiết kế domain/API/schema và implement service — xuất receipt/invoice/tax document theo cấu hình  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0655` **Data** — Data: Event taxonomy/data model/dashboard metric — xuất receipt/invoice/tax document theo cấu hình  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0656` **QA** — QA: Test plan và automated tests — xuất receipt/invoice/tax document theo cấu hình  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E034 — Fraud, abuse and payment risk

**Objective:** Phát hiện booking/payment rủi ro trước khi fulfilment.  
**Priority:** P1  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0129 — Là Risk Ops, tôi muốn flag booking rủi ro theo rule velocity, mismatch, high-value để giảm fraud.

- **Priority:** P1
- **Tags:** Fraud, Security, BE
- **Acceptance criteria:** Given Risk Ops có quyền hợp lệ; When flag booking rủi ro theo rule velocity, mismatch, high-value; Then kết quả giúp giảm fraud; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0657` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — flag booking rủi ro theo rule velocity, mismatch, high-value  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0658` **BE** — BE: Thiết kế domain/API/schema và implement service — flag booking rủi ro theo rule velocity, mismatch, high-value  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0659` **Security** — Security: Threat model và security control — flag booking rủi ro theo rule velocity, mismatch, high-value  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0660` **QA** — QA: Test plan và automated tests — flag booking rủi ro theo rule velocity, mismatch, high-value  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0130 — Là Ops, tôi muốn review risk queue trước khi confirm supplier để ngăn fulfill booking đáng ngờ.

- **Priority:** P1
- **Tags:** Fraud, Admin, Ops
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When review risk queue trước khi confirm supplier; Then kết quả giúp ngăn fulfill booking đáng ngờ; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0661` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — review risk queue trước khi confirm supplier  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0662` **UX** — UX: Thiết kế wireframe/UI states — review risk queue trước khi confirm supplier  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0663` **FE** — FE: Implement UI và client integration — review risk queue trước khi confirm supplier  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0664` **BE** — BE: Thiết kế domain/API/schema và implement service — review risk queue trước khi confirm supplier  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0665` **Security** — Security: Threat model và security control — review risk queue trước khi confirm supplier  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0666` **QA** — QA: Test plan và automated tests — review risk queue trước khi confirm supplier  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0131 — Là System, tôi muốn rate limit payment attempts và quote scraping để bảo vệ cổng và supplier.

- **Priority:** P0
- **Tags:** Fraud, SRE, Security
- **Acceptance criteria:** Given System có quyền hợp lệ; When rate limit payment attempts và quote scraping; Then kết quả giúp bảo vệ cổng và supplier; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0667` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — rate limit payment attempts và quote scraping  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0668` **BE** — BE: Thiết kế domain/API/schema và implement service — rate limit payment attempts và quote scraping  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0669` **Security** — Security: Threat model và security control — rate limit payment attempts và quote scraping  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0670` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — rate limit payment attempts và quote scraping  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0671` **QA** — QA: Test plan và automated tests — rate limit payment attempts và quote scraping  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP10 — B2B Agent Workspace

**Owner:** B2B Product Lead

## CT-E035 — Agent CRM and customer profile

**Objective:** Agent quản lý khách hàng, nhu cầu, lịch sử quote/booking.  
**Priority:** P1  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0132 — Là Travel Agent, tôi muốn tạo customer profile và lưu nhu cầu chuyến đi để tư vấn lại nhanh hơn.

- **Priority:** P1
- **Tags:** B2B, CRM, FE, BE
- **Acceptance criteria:** Given Travel Agent có quyền hợp lệ; When tạo customer profile và lưu nhu cầu chuyến đi; Then kết quả giúp tư vấn lại nhanh hơn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0672` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tạo customer profile và lưu nhu cầu chuyến đi  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0673` **UX** — UX: Thiết kế wireframe/UI states — tạo customer profile và lưu nhu cầu chuyến đi  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0674` **FE** — FE: Implement UI và client integration — tạo customer profile và lưu nhu cầu chuyến đi  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0675` **BE** — BE: Thiết kế domain/API/schema và implement service — tạo customer profile và lưu nhu cầu chuyến đi  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0676` **QA** — QA: Test plan và automated tests — tạo customer profile và lưu nhu cầu chuyến đi  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0133 — Là Travel Agent, tôi muốn xem timeline quote/booking/conversation của customer để nắm lịch sử chăm sóc.

- **Priority:** P1
- **Tags:** B2B, CRM, FE, BE
- **Acceptance criteria:** Given Travel Agent có quyền hợp lệ; When xem timeline quote/booking/conversation của customer; Then kết quả giúp nắm lịch sử chăm sóc; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0677` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem timeline quote/booking/conversation của customer  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0678` **UX** — UX: Thiết kế wireframe/UI states — xem timeline quote/booking/conversation của customer  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0679` **FE** — FE: Implement UI và client integration — xem timeline quote/booking/conversation của customer  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0680` **BE** — BE: Thiết kế domain/API/schema và implement service — xem timeline quote/booking/conversation của customer  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0681` **QA** — QA: Test plan và automated tests — xem timeline quote/booking/conversation của customer  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0134 — Là Agent Manager, tôi muốn phân quyền customer theo team/owner để bảo vệ dữ liệu khách.

- **Priority:** P1
- **Tags:** B2B, RBAC, Security
- **Acceptance criteria:** Given Agent Manager có quyền hợp lệ; When phân quyền customer theo team/owner; Then kết quả giúp bảo vệ dữ liệu khách; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0682` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — phân quyền customer theo team/owner  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0683` **UX** — UX: Thiết kế wireframe/UI states — phân quyền customer theo team/owner  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0684` **FE** — FE: Implement UI và client integration — phân quyền customer theo team/owner  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0685` **BE** — BE: Thiết kế domain/API/schema và implement service — phân quyền customer theo team/owner  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0686` **Security** — Security: Threat model và security control — phân quyền customer theo team/owner  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0687` **QA** — QA: Test plan và automated tests — phân quyền customer theo team/owner  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E036 — Agent quote builder and share link

**Objective:** Agent tạo quote chuyên nghiệp, gắn commission, chia sẻ PDF/link cho khách.  
**Priority:** P1  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0135 — Là Travel Agent, tôi muốn tạo quote từ tour/hotel/flight và điều chỉnh markup được phép để bán gói linh hoạt.

- **Priority:** P1
- **Tags:** B2B, Quote, FE, BE
- **Acceptance criteria:** Given Travel Agent có quyền hợp lệ; When tạo quote từ tour/hotel/flight và điều chỉnh markup được phép; Then kết quả giúp bán gói linh hoạt; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0688` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tạo quote từ tour/hotel/flight và điều chỉnh markup được phép  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0689` **UX** — UX: Thiết kế wireframe/UI states — tạo quote từ tour/hotel/flight và điều chỉnh markup được phép  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0690` **FE** — FE: Implement UI và client integration — tạo quote từ tour/hotel/flight và điều chỉnh markup được phép  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0691` **BE** — BE: Thiết kế domain/API/schema và implement service — tạo quote từ tour/hotel/flight và điều chỉnh markup được phép  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0692` **QA** — QA: Test plan và automated tests — tạo quote từ tour/hotel/flight và điều chỉnh markup được phép  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0136 — Là Travel Agent, tôi muốn share quote link/PDF có expiry và tracking để khách duyệt nhanh.

- **Priority:** P1
- **Tags:** B2B, Document, Notification
- **Acceptance criteria:** Given Travel Agent có quyền hợp lệ; When share quote link/PDF có expiry và tracking; Then kết quả giúp khách duyệt nhanh; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0693` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — share quote link/PDF có expiry và tracking  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0694` **UX** — UX: Thiết kế wireframe/UI states — share quote link/PDF có expiry và tracking  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0695` **FE** — FE: Implement UI và client integration — share quote link/PDF có expiry và tracking  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0696` **BE** — BE: Thiết kế domain/API/schema và implement service — share quote link/PDF có expiry và tracking  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0697` **QA** — QA: Test plan và automated tests — share quote link/PDF có expiry và tracking  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0137 — Là Customer, tôi muốn accept quote từ link và chuyển sang booking/payment để rút ngắn chốt đơn.

- **Priority:** P1
- **Tags:** B2B, Booking, FE, BE
- **Acceptance criteria:** Given Customer có quyền hợp lệ; When accept quote từ link và chuyển sang booking/payment; Then kết quả giúp rút ngắn chốt đơn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0698` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — accept quote từ link và chuyển sang booking/payment  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0699` **UX** — UX: Thiết kế wireframe/UI states — accept quote từ link và chuyển sang booking/payment  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0700` **FE** — FE: Implement UI và client integration — accept quote từ link và chuyển sang booking/payment  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0701` **BE** — BE: Thiết kế domain/API/schema và implement service — accept quote từ link và chuyển sang booking/payment  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0702` **QA** — QA: Test plan và automated tests — accept quote từ link và chuyển sang booking/payment  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0138 — Là Manager, tôi muốn approve discount/markup ngoài ngưỡng để kiểm soát margin.

- **Priority:** P1
- **Tags:** B2B, Finance, Admin
- **Acceptance criteria:** Given Manager có quyền hợp lệ; When approve discount/markup ngoài ngưỡng; Then kết quả giúp kiểm soát margin; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0703` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — approve discount/markup ngoài ngưỡng  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0704` **UX** — UX: Thiết kế wireframe/UI states — approve discount/markup ngoài ngưỡng  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0705` **FE** — FE: Implement UI và client integration — approve discount/markup ngoài ngưỡng  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0706` **Data** — Data: Event taxonomy/data model/dashboard metric — approve discount/markup ngoài ngưỡng  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0707` **QA** — QA: Test plan và automated tests — approve discount/markup ngoài ngưỡng  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E037 — Agent dashboard, commission and operations

**Objective:** Theo dõi booking, doanh số, commission, SLA của từng agent/org.  
**Priority:** P1  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0139 — Là Travel Agent, tôi muốn xem dashboard booking theo status, departure date, value để quản lý pipeline.

- **Priority:** P1
- **Tags:** B2B, Dashboard, FE, BE
- **Acceptance criteria:** Given Travel Agent có quyền hợp lệ; When xem dashboard booking theo status, departure date, value; Then kết quả giúp quản lý pipeline; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0708` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem dashboard booking theo status, departure date, value  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0709` **UX** — UX: Thiết kế wireframe/UI states — xem dashboard booking theo status, departure date, value  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0710` **FE** — FE: Implement UI và client integration — xem dashboard booking theo status, departure date, value  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0711` **BE** — BE: Thiết kế domain/API/schema và implement service — xem dashboard booking theo status, departure date, value  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0712` **QA** — QA: Test plan và automated tests — xem dashboard booking theo status, departure date, value  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0140 — Là Agent Manager, tôi muốn xem performance theo nhân viên/team để quản trị doanh số.

- **Priority:** P1
- **Tags:** B2B, Analytics, FE, BE
- **Acceptance criteria:** Given Agent Manager có quyền hợp lệ; When xem performance theo nhân viên/team; Then kết quả giúp quản trị doanh số; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0713` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem performance theo nhân viên/team  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0714` **UX** — UX: Thiết kế wireframe/UI states — xem performance theo nhân viên/team  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0715` **FE** — FE: Implement UI và client integration — xem performance theo nhân viên/team  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0716` **BE** — BE: Thiết kế domain/API/schema và implement service — xem performance theo nhân viên/team  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0717` **Data** — Data: Event taxonomy/data model/dashboard metric — xem performance theo nhân viên/team  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0718` **QA** — QA: Test plan và automated tests — xem performance theo nhân viên/team  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0141 — Là Travel Agent, tôi muốn nhận commission statement để đối chiếu thu nhập.

- **Priority:** P1
- **Tags:** B2B, Commission, Finance
- **Acceptance criteria:** Given Travel Agent có quyền hợp lệ; When nhận commission statement; Then kết quả giúp đối chiếu thu nhập; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0719` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — nhận commission statement  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0720` **UX** — UX: Thiết kế wireframe/UI states — nhận commission statement  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0721` **FE** — FE: Implement UI và client integration — nhận commission statement  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0722` **Data** — Data: Event taxonomy/data model/dashboard metric — nhận commission statement  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0723` **QA** — QA: Test plan và automated tests — nhận commission statement  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0142 — Là Ops, tôi muốn escalate booking B2B theo SLA để giữ chất lượng phục vụ.

- **Priority:** P1
- **Tags:** B2B, Ops, Notification
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When escalate booking B2B theo SLA; Then kết quả giúp giữ chất lượng phục vụ; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0724` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — escalate booking B2B theo SLA  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0725` **UX** — UX: Thiết kế wireframe/UI states — escalate booking B2B theo SLA  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0726` **FE** — FE: Implement UI và client integration — escalate booking B2B theo SLA  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0727` **BE** — BE: Thiết kế domain/API/schema và implement service — escalate booking B2B theo SLA  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0728` **QA** — QA: Test plan và automated tests — escalate booking B2B theo SLA  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP11 — Admin, Operations & Customer Support

**Owner:** Ops Lead

## CT-E038 — Booking operations console

**Objective:** Ops xem, lọc, can thiệp booking với audit đầy đủ.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0143 — Là Ops, tôi muốn search booking theo mã, khách, supplier, payment ref, trạng thái để tìm case nhanh.

- **Priority:** P0
- **Tags:** Admin, Ops, Search, FE, BE
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When search booking theo mã, khách, supplier, payment ref, trạng thái; Then kết quả giúp tìm case nhanh; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0729` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — search booking theo mã, khách, supplier, payment ref, trạng thái  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0730` **UX** — UX: Thiết kế wireframe/UI states — search booking theo mã, khách, supplier, payment ref, trạng thái  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0731` **FE** — FE: Implement UI và client integration — search booking theo mã, khách, supplier, payment ref, trạng thái  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0732` **BE** — BE: Thiết kế domain/API/schema và implement service — search booking theo mã, khách, supplier, payment ref, trạng thái  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0733` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — search booking theo mã, khách, supplier, payment ref, trạng thái  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0734` **QA** — QA: Test plan và automated tests — search booking theo mã, khách, supplier, payment ref, trạng thái  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0144 — Là Ops, tôi muốn xem timeline event, payment, supplier, notification, AI tool call để debug end-to-end.

- **Priority:** P0
- **Tags:** Admin, Observability, FE, BE
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When xem timeline event, payment, supplier, notification, AI tool call; Then kết quả giúp debug end-to-end; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0735` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem timeline event, payment, supplier, notification, AI tool call  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0736` **UX** — UX: Thiết kế wireframe/UI states — xem timeline event, payment, supplier, notification, AI tool call  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0737` **FE** — FE: Implement UI và client integration — xem timeline event, payment, supplier, notification, AI tool call  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0738` **BE** — BE: Thiết kế domain/API/schema và implement service — xem timeline event, payment, supplier, notification, AI tool call  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0739` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — xem timeline event, payment, supplier, notification, AI tool call  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0740` **QA** — QA: Test plan và automated tests — xem timeline event, payment, supplier, notification, AI tool call  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0145 — Là Ops, tôi muốn manual override trạng thái có approval và reason để xử lý exception an toàn.

- **Priority:** P0
- **Tags:** Admin, Security, Audit
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When manual override trạng thái có approval và reason; Then kết quả giúp xử lý exception an toàn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0741` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — manual override trạng thái có approval và reason  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0742` **UX** — UX: Thiết kế wireframe/UI states — manual override trạng thái có approval và reason  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0743` **FE** — FE: Implement UI và client integration — manual override trạng thái có approval và reason  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0744` **Security** — Security: Threat model và security control — manual override trạng thái có approval và reason  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0745` **QA** — QA: Test plan và automated tests — manual override trạng thái có approval và reason  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0146 — Là Ops Manager, tôi muốn xem queue case cần xử lý theo SLA để không bỏ sót vấn đề.

- **Priority:** P1
- **Tags:** Admin, Ops, FE, BE
- **Acceptance criteria:** Given Ops Manager có quyền hợp lệ; When xem queue case cần xử lý theo SLA; Then kết quả giúp không bỏ sót vấn đề; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0746` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem queue case cần xử lý theo SLA  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0747` **UX** — UX: Thiết kế wireframe/UI states — xem queue case cần xử lý theo SLA  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0748` **FE** — FE: Implement UI và client integration — xem queue case cần xử lý theo SLA  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0749` **BE** — BE: Thiết kế domain/API/schema và implement service — xem queue case cần xử lý theo SLA  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0750` **QA** — QA: Test plan và automated tests — xem queue case cần xử lý theo SLA  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E039 — Case management and customer support

**Objective:** Quản lý ticket support, conversation, refund/cancel/change escalation.  
**Priority:** P1  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0147 — Là Support Agent, tôi muốn tạo case từ booking hoặc conversation để theo dõi yêu cầu khách.

- **Priority:** P1
- **Tags:** Support, Admin, FE, BE
- **Acceptance criteria:** Given Support Agent có quyền hợp lệ; When tạo case từ booking hoặc conversation; Then kết quả giúp theo dõi yêu cầu khách; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0751` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tạo case từ booking hoặc conversation  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0752` **UX** — UX: Thiết kế wireframe/UI states — tạo case từ booking hoặc conversation  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0753` **FE** — FE: Implement UI và client integration — tạo case từ booking hoặc conversation  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0754` **BE** — BE: Thiết kế domain/API/schema và implement service — tạo case từ booking hoặc conversation  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0755` **QA** — QA: Test plan và automated tests — tạo case từ booking hoặc conversation  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0148 — Là Support Agent, tôi muốn ghi note nội bộ và phân loại reason để phân tích vấn đề.

- **Priority:** P1
- **Tags:** Support, FE, BE, Analytics
- **Acceptance criteria:** Given Support Agent có quyền hợp lệ; When ghi note nội bộ và phân loại reason; Then kết quả giúp phân tích vấn đề; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0756` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — ghi note nội bộ và phân loại reason  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0757` **UX** — UX: Thiết kế wireframe/UI states — ghi note nội bộ và phân loại reason  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0758` **FE** — FE: Implement UI và client integration — ghi note nội bộ và phân loại reason  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0759` **BE** — BE: Thiết kế domain/API/schema và implement service — ghi note nội bộ và phân loại reason  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0760` **Data** — Data: Event taxonomy/data model/dashboard metric — ghi note nội bộ và phân loại reason  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0761` **QA** — QA: Test plan và automated tests — ghi note nội bộ và phân loại reason  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0149 — Là Support Manager, tôi muốn assign/escalate case theo SLA để xử lý đúng hạn.

- **Priority:** P1
- **Tags:** Support, Ops, Notification
- **Acceptance criteria:** Given Support Manager có quyền hợp lệ; When assign/escalate case theo SLA; Then kết quả giúp xử lý đúng hạn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0762` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — assign/escalate case theo SLA  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0763` **BE** — BE: Thiết kế domain/API/schema và implement service — assign/escalate case theo SLA  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0764` **QA** — QA: Test plan và automated tests — assign/escalate case theo SLA  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0150 — Là Compliance, tôi muốn mask PII trong case khi không có quyền để bảo vệ dữ liệu.

- **Priority:** P0
- **Tags:** Support, Security, Privacy
- **Acceptance criteria:** Given Compliance có quyền hợp lệ; When mask PII trong case khi không có quyền; Then kết quả giúp bảo vệ dữ liệu; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0765` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — mask PII trong case khi không có quyền  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0766` **BE** — BE: Thiết kế domain/API/schema và implement service — mask PII trong case khi không có quyền  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0767` **Security** — Security: Threat model và security control — mask PII trong case khi không có quyền  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0768` **QA** — QA: Test plan và automated tests — mask PII trong case khi không có quyền  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E040 — Supplier operations and quality control

**Objective:** Ops quản lý supplier confirmation, SLA, complaint, quality score.  
**Priority:** P1  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0151 — Là Ops, tôi muốn xem supplier pending confirmation queue để đẩy supplier phản hồi đúng hạn.

- **Priority:** P0
- **Tags:** SupplierOps, Admin, FE, BE
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When xem supplier pending confirmation queue; Then kết quả giúp đẩy supplier phản hồi đúng hạn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0769` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem supplier pending confirmation queue  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0770` **UX** — UX: Thiết kế wireframe/UI states — xem supplier pending confirmation queue  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0771` **FE** — FE: Implement UI và client integration — xem supplier pending confirmation queue  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0772` **BE** — BE: Thiết kế domain/API/schema và implement service — xem supplier pending confirmation queue  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0773` **QA** — QA: Test plan và automated tests — xem supplier pending confirmation queue  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0152 — Là Ops, tôi muốn ghi nhận complaint/refund reason theo supplier để cải thiện chất lượng.

- **Priority:** P1
- **Tags:** SupplierOps, Analytics, BE
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When ghi nhận complaint/refund reason theo supplier; Then kết quả giúp cải thiện chất lượng; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0774` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — ghi nhận complaint/refund reason theo supplier  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0775` **BE** — BE: Thiết kế domain/API/schema và implement service — ghi nhận complaint/refund reason theo supplier  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0776` **Data** — Data: Event taxonomy/data model/dashboard metric — ghi nhận complaint/refund reason theo supplier  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0777` **QA** — QA: Test plan và automated tests — ghi nhận complaint/refund reason theo supplier  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0153 — Là Supplier Manager, tôi muốn xem supplier scorecard để quyết định ưu tiên/loại supplier.

- **Priority:** P1
- **Tags:** SupplierOps, Analytics, FE
- **Acceptance criteria:** Given Supplier Manager có quyền hợp lệ; When xem supplier scorecard; Then kết quả giúp quyết định ưu tiên/loại supplier; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0778` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem supplier scorecard  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0779` **UX** — UX: Thiết kế wireframe/UI states — xem supplier scorecard  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0780` **FE** — FE: Implement UI và client integration — xem supplier scorecard  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0781` **Data** — Data: Event taxonomy/data model/dashboard metric — xem supplier scorecard  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0782` **QA** — QA: Test plan và automated tests — xem supplier scorecard  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0154 — Là Ops, tôi muốn manual fallback khi supplier API down để duy trì fulfilment.

- **Priority:** P0
- **Tags:** SupplierOps, SupplierAdapter, Admin
- **Acceptance criteria:** Given Ops có quyền hợp lệ; When manual fallback khi supplier API down; Then kết quả giúp duy trì fulfilment; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0783` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — manual fallback khi supplier API down  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0784` **UX** — UX: Thiết kế wireframe/UI states — manual fallback khi supplier API down  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0785` **FE** — FE: Implement UI và client integration — manual fallback khi supplier API down  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0786` **BE** — BE: Thiết kế domain/API/schema và implement service — manual fallback khi supplier API down  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0787` **Integration** — Integration: Implement adapter/contract test/mock — manual fallback khi supplier API down  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0788` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — manual fallback khi supplier API down  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0789` **QA** — QA: Test plan và automated tests — manual fallback khi supplier API down  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP12 — Notification & Communication Platform

**Owner:** Communication Lead

## CT-E041 — Notification template and event dispatch

**Objective:** Gửi đúng thông điệp cho booking/payment/refund/supplier/support qua nhiều kênh.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0155 — Là Content Admin, tôi muốn quản lý template email/SMS/Zalo/push theo ngôn ngữ để đổi copy không cần deploy.

- **Priority:** P1
- **Tags:** Notification, CMS, FE, BE
- **Acceptance criteria:** Given Content Admin có quyền hợp lệ; When quản lý template email/SMS/Zalo/push theo ngôn ngữ; Then kết quả giúp đổi copy không cần deploy; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0790` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — quản lý template email/SMS/Zalo/push theo ngôn ngữ  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0791` **UX** — UX: Thiết kế wireframe/UI states — quản lý template email/SMS/Zalo/push theo ngôn ngữ  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0792` **FE** — FE: Implement UI và client integration — quản lý template email/SMS/Zalo/push theo ngôn ngữ  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0793` **BE** — BE: Thiết kế domain/API/schema và implement service — quản lý template email/SMS/Zalo/push theo ngôn ngữ  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0794` **QA** — QA: Test plan và automated tests — quản lý template email/SMS/Zalo/push theo ngôn ngữ  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0156 — Là System, tôi muốn gửi notification idempotent từ domain event để không gửi trùng.

- **Priority:** P0
- **Tags:** Notification, BE, Event
- **Acceptance criteria:** Given System có quyền hợp lệ; When gửi notification idempotent từ domain event; Then kết quả giúp không gửi trùng; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0795` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — gửi notification idempotent từ domain event  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0796` **BE** — BE: Thiết kế domain/API/schema và implement service — gửi notification idempotent từ domain event  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0797` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — gửi notification idempotent từ domain event  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0798` **QA** — QA: Test plan và automated tests — gửi notification idempotent từ domain event  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0157 — Là SRE, tôi muốn theo dõi retry, DLQ, bounce/fail rate theo provider để không mất thông báo quan trọng.

- **Priority:** P0
- **Tags:** Notification, SRE, Observability
- **Acceptance criteria:** Given SRE có quyền hợp lệ; When theo dõi retry, DLQ, bounce/fail rate theo provider; Then kết quả giúp không mất thông báo quan trọng; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0799` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — theo dõi retry, DLQ, bounce/fail rate theo provider  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0800` **BE** — BE: Thiết kế domain/API/schema và implement service — theo dõi retry, DLQ, bounce/fail rate theo provider  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0801` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — theo dõi retry, DLQ, bounce/fail rate theo provider  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0802` **QA** — QA: Test plan và automated tests — theo dõi retry, DLQ, bounce/fail rate theo provider  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0158 — Là QA, tôi muốn test template rendering với dữ liệu thật/missing để không lỗi nội dung.

- **Priority:** P0
- **Tags:** Notification, QA
- **Acceptance criteria:** Given QA có quyền hợp lệ; When test template rendering với dữ liệu thật/missing; Then kết quả giúp không lỗi nội dung; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0803` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — test template rendering với dữ liệu thật/missing  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0804` **BE** — BE: Thiết kế domain/API/schema và implement service — test template rendering với dữ liệu thật/missing  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0805` **QA** — QA: Test plan và automated tests — test template rendering với dữ liệu thật/missing  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E042 — User communication preferences

**Objective:** Người dùng kiểm soát kênh nhận thông báo và marketing consent.  
**Priority:** P1  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0159 — Là Traveller, tôi muốn chọn kênh nhận booking updates để nhận đúng nơi mong muốn.

- **Priority:** P1
- **Tags:** Notification, Privacy, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When chọn kênh nhận booking updates; Then kết quả giúp nhận đúng nơi mong muốn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0806` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — chọn kênh nhận booking updates  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0807` **UX** — UX: Thiết kế wireframe/UI states — chọn kênh nhận booking updates  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0808` **FE** — FE: Implement UI và client integration — chọn kênh nhận booking updates  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0809` **BE** — BE: Thiết kế domain/API/schema và implement service — chọn kênh nhận booking updates  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0810` **Security** — Security: Threat model và security control — chọn kênh nhận booking updates  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0811` **QA** — QA: Test plan và automated tests — chọn kênh nhận booking updates  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0160 — Là Traveller, tôi muốn unsubscribe marketing một click để tôn trọng consent.

- **Priority:** P0
- **Tags:** Notification, Privacy, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When unsubscribe marketing một click; Then kết quả giúp tôn trọng consent; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0812` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — unsubscribe marketing một click  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0813` **UX** — UX: Thiết kế wireframe/UI states — unsubscribe marketing một click  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0814` **FE** — FE: Implement UI và client integration — unsubscribe marketing một click  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0815` **BE** — BE: Thiết kế domain/API/schema và implement service — unsubscribe marketing một click  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0816` **Security** — Security: Threat model và security control — unsubscribe marketing một click  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0817` **QA** — QA: Test plan và automated tests — unsubscribe marketing một click  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0161 — Là System, tôi muốn phân biệt transactional vs marketing messages để không vi phạm consent.

- **Priority:** P0
- **Tags:** Notification, Privacy, BE
- **Acceptance criteria:** Given System có quyền hợp lệ; When phân biệt transactional vs marketing messages; Then kết quả giúp không vi phạm consent; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0818` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — phân biệt transactional vs marketing messages  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0819` **BE** — BE: Thiết kế domain/API/schema và implement service — phân biệt transactional vs marketing messages  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0820` **Security** — Security: Threat model và security control — phân biệt transactional vs marketing messages  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0821` **QA** — QA: Test plan và automated tests — phân biệt transactional vs marketing messages  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E043 — Operational inbox and threaded messages

**Objective:** Lưu vết trao đổi giữa user-agent-ops-supplier trong context booking/case.  
**Priority:** P2  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0162 — Là Traveller, tôi muốn xem tin nhắn liên quan booking trong My Trips để không thất lạc thông tin.

- **Priority:** P2
- **Tags:** Messaging, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When xem tin nhắn liên quan booking trong My Trips; Then kết quả giúp không thất lạc thông tin; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0822` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem tin nhắn liên quan booking trong My Trips  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0823` **UX** — UX: Thiết kế wireframe/UI states — xem tin nhắn liên quan booking trong My Trips  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0824` **FE** — FE: Implement UI và client integration — xem tin nhắn liên quan booking trong My Trips  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0825` **BE** — BE: Thiết kế domain/API/schema và implement service — xem tin nhắn liên quan booking trong My Trips  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0826` **QA** — QA: Test plan và automated tests — xem tin nhắn liên quan booking trong My Trips  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0163 — Là Support, tôi muốn trả lời khách trong case thread để hỗ trợ tập trung.

- **Priority:** P2
- **Tags:** Messaging, Support, FE, BE
- **Acceptance criteria:** Given Support có quyền hợp lệ; When trả lời khách trong case thread; Then kết quả giúp hỗ trợ tập trung; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0827` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — trả lời khách trong case thread  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0828` **UX** — UX: Thiết kế wireframe/UI states — trả lời khách trong case thread  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0829` **FE** — FE: Implement UI và client integration — trả lời khách trong case thread  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0830` **BE** — BE: Thiết kế domain/API/schema và implement service — trả lời khách trong case thread  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0831` **QA** — QA: Test plan và automated tests — trả lời khách trong case thread  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0164 — Là Supplier, tôi muốn nhận/gửi clarification cho booking để xác nhận thông tin thiếu.

- **Priority:** P2
- **Tags:** Messaging, SupplierPortal, FE, BE
- **Acceptance criteria:** Given Supplier có quyền hợp lệ; When nhận/gửi clarification cho booking; Then kết quả giúp xác nhận thông tin thiếu; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0832` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — nhận/gửi clarification cho booking  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0833` **UX** — UX: Thiết kế wireframe/UI states — nhận/gửi clarification cho booking  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0834` **FE** — FE: Implement UI và client integration — nhận/gửi clarification cho booking  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0835` **BE** — BE: Thiết kế domain/API/schema và implement service — nhận/gửi clarification cho booking  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0836` **QA** — QA: Test plan và automated tests — nhận/gửi clarification cho booking  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP13 — Analytics, Unit Economics & BI

**Owner:** Data/Finance Lead

## CT-E044 — Event taxonomy and product funnel

**Objective:** Đo search, AI, quote, booking, payment, cancellation và support funnel.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0165 — Là Product, tôi muốn track funnel từ search → AI/chat → quote → draft → payment → confirmed để biết điểm rơi chuyển đổi.

- **Priority:** P0
- **Tags:** Analytics, Data, FE, BE
- **Acceptance criteria:** Given Product có quyền hợp lệ; When track funnel từ search → AI/chat → quote → draft → payment → confirmed; Then kết quả giúp biết điểm rơi chuyển đổi; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0837` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — track funnel từ search → AI/chat → quote → draft → payment → confirmed  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0838` **UX** — UX: Thiết kế wireframe/UI states — track funnel từ search → AI/chat → quote → draft → payment → confirmed  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0839` **FE** — FE: Implement UI và client integration — track funnel từ search → AI/chat → quote → draft → payment → confirmed  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0840` **BE** — BE: Thiết kế domain/API/schema và implement service — track funnel từ search → AI/chat → quote → draft → payment → confirmed  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0841` **Data** — Data: Event taxonomy/data model/dashboard metric — track funnel từ search → AI/chat → quote → draft → payment → confirmed  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0842` **QA** — QA: Test plan và automated tests — track funnel từ search → AI/chat → quote → draft → payment → confirmed  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0166 — Là Data Analyst, tôi muốn định nghĩa event taxonomy và naming convention để dữ liệu thống nhất.

- **Priority:** P0
- **Tags:** Analytics, Data, BA
- **Acceptance criteria:** Given Data Analyst có quyền hợp lệ; When định nghĩa event taxonomy và naming convention; Then kết quả giúp dữ liệu thống nhất; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0843` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — định nghĩa event taxonomy và naming convention  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0844` **Data** — Data: Event taxonomy/data model/dashboard metric — định nghĩa event taxonomy và naming convention  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0845` **QA** — QA: Test plan và automated tests — định nghĩa event taxonomy và naming convention  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0167 — Là Product, tôi muốn xem dashboard funnel theo channel/product/supplier để tối ưu sản phẩm.

- **Priority:** P1
- **Tags:** Analytics, BI, FE, Data
- **Acceptance criteria:** Given Product có quyền hợp lệ; When xem dashboard funnel theo channel/product/supplier; Then kết quả giúp tối ưu sản phẩm; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0846` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem dashboard funnel theo channel/product/supplier  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0847` **UX** — UX: Thiết kế wireframe/UI states — xem dashboard funnel theo channel/product/supplier  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0848` **FE** — FE: Implement UI và client integration — xem dashboard funnel theo channel/product/supplier  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0849` **Data** — Data: Event taxonomy/data model/dashboard metric — xem dashboard funnel theo channel/product/supplier  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0850` **QA** — QA: Test plan và automated tests — xem dashboard funnel theo channel/product/supplier  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0168 — Là QA, tôi muốn test event tracking accuracy để không đo sai.

- **Priority:** P0
- **Tags:** Analytics, QA, Data
- **Acceptance criteria:** Given QA có quyền hợp lệ; When test event tracking accuracy; Then kết quả giúp không đo sai; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0851` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — test event tracking accuracy  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0852` **Data** — Data: Event taxonomy/data model/dashboard metric — test event tracking accuracy  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0853` **QA** — QA: Test plan và automated tests — test event tracking accuracy  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E045 — Unit economics model

**Objective:** Theo dõi WCPCT, contribution margin, CAC ceiling, take rate, refund loss.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0169 — Là Leadership, tôi muốn xem North Star WCPCT theo tuần để biết tăng trưởng có lãi hay không.

- **Priority:** P0
- **Tags:** Finance, Analytics, BI
- **Acceptance criteria:** Given Leadership có quyền hợp lệ; When xem North Star WCPCT theo tuần; Then kết quả giúp biết tăng trưởng có lãi hay không; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0854` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem North Star WCPCT theo tuần  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0855` **Data** — Data: Event taxonomy/data model/dashboard metric — xem North Star WCPCT theo tuần  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0856` **QA** — QA: Test plan và automated tests — xem North Star WCPCT theo tuần  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0170 — Là Finance, tôi muốn tính contribution margin theo product/channel/supplier để ra quyết định scale đúng.

- **Priority:** P0
- **Tags:** Finance, Data, BE
- **Acceptance criteria:** Given Finance có quyền hợp lệ; When tính contribution margin theo product/channel/supplier; Then kết quả giúp ra quyết định scale đúng; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0857` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tính contribution margin theo product/channel/supplier  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0858` **BE** — BE: Thiết kế domain/API/schema và implement service — tính contribution margin theo product/channel/supplier  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0859` **Data** — Data: Event taxonomy/data model/dashboard metric — tính contribution margin theo product/channel/supplier  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0860` **QA** — QA: Test plan và automated tests — tính contribution margin theo product/channel/supplier  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0171 — Là Growth, tôi muốn xem CAC ceiling và payback theo channel để không mua traffic lỗ.

- **Priority:** P1
- **Tags:** Finance, Growth, Analytics
- **Acceptance criteria:** Given Growth có quyền hợp lệ; When xem CAC ceiling và payback theo channel; Then kết quả giúp không mua traffic lỗ; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0861` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem CAC ceiling và payback theo channel  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0862` **Data** — Data: Event taxonomy/data model/dashboard metric — xem CAC ceiling và payback theo channel  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0863` **QA** — QA: Test plan và automated tests — xem CAC ceiling và payback theo channel  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0172 — Là Finance, tôi muốn đưa assumption take rate/gateway fee/refund rate vào model để không hard-code unit economics.

- **Priority:** P0
- **Tags:** Finance, BE, Admin
- **Acceptance criteria:** Given Finance có quyền hợp lệ; When đưa assumption take rate/gateway fee/refund rate vào model; Then kết quả giúp không hard-code unit economics; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0864` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — đưa assumption take rate/gateway fee/refund rate vào model  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0865` **UX** — UX: Thiết kế wireframe/UI states — đưa assumption take rate/gateway fee/refund rate vào model  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0866` **FE** — FE: Implement UI và client integration — đưa assumption take rate/gateway fee/refund rate vào model  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0867` **BE** — BE: Thiết kế domain/API/schema và implement service — đưa assumption take rate/gateway fee/refund rate vào model  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0868` **Data** — Data: Event taxonomy/data model/dashboard metric — đưa assumption take rate/gateway fee/refund rate vào model  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0869` **QA** — QA: Test plan và automated tests — đưa assumption take rate/gateway fee/refund rate vào model  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E046 — Supplier, AI and operations analytics

**Objective:** Đo performance supplier, AI cost/quality, ops SLA và quality issues.  
**Priority:** P1  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0173 — Là Supplier Manager, tôi muốn xem supplier SLA, confirm success, cancel/refund success để quản trị đối tác.

- **Priority:** P1
- **Tags:** SupplierOps, Analytics, BI
- **Acceptance criteria:** Given Supplier Manager có quyền hợp lệ; When xem supplier SLA, confirm success, cancel/refund success; Then kết quả giúp quản trị đối tác; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0870` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem supplier SLA, confirm success, cancel/refund success  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0871` **Data** — Data: Event taxonomy/data model/dashboard metric — xem supplier SLA, confirm success, cancel/refund success  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0872` **QA** — QA: Test plan và automated tests — xem supplier SLA, confirm success, cancel/refund success  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0174 — Là AI Lead, tôi muốn xem AI cost, token, tool success, hallucination flags để quản trị AI.

- **Priority:** P0
- **Tags:** AI, Analytics, BI
- **Acceptance criteria:** Given AI Lead có quyền hợp lệ; When xem AI cost, token, tool success, hallucination flags; Then kết quả giúp quản trị AI; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0873` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem AI cost, token, tool success, hallucination flags  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0874` **AI** — AI: Thiết kế prompt/tool schema/eval cases — xem AI cost, token, tool success, hallucination flags  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0875` **Security** — Security: Threat model và security control — xem AI cost, token, tool success, hallucination flags  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0876` **Data** — Data: Event taxonomy/data model/dashboard metric — xem AI cost, token, tool success, hallucination flags  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0877` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — xem AI cost, token, tool success, hallucination flags  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0878` **QA** — QA: Test plan và automated tests — xem AI cost, token, tool success, hallucination flags  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0175 — Là Ops Manager, tôi muốn xem support SLA, top issue reason, refund reason để giảm chi phí vận hành.

- **Priority:** P1
- **Tags:** Ops, Analytics, BI
- **Acceptance criteria:** Given Ops Manager có quyền hợp lệ; When xem support SLA, top issue reason, refund reason; Then kết quả giúp giảm chi phí vận hành; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0879` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xem support SLA, top issue reason, refund reason  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0880` **Data** — Data: Event taxonomy/data model/dashboard metric — xem support SLA, top issue reason, refund reason  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0881` **QA** — QA: Test plan và automated tests — xem support SLA, top issue reason, refund reason  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0176 — Là Data Analyst, tôi muốn xuất data mart cho BI để phân tích sâu.

- **Priority:** P1
- **Tags:** Data, BI, Architecture
- **Acceptance criteria:** Given Data Analyst có quyền hợp lệ; When xuất data mart cho BI; Then kết quả giúp phân tích sâu; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0882` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xuất data mart cho BI  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0883` **Data** — Data: Event taxonomy/data model/dashboard metric — xuất data mart cho BI  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0884` **QA** — QA: Test plan và automated tests — xuất data mart cho BI  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP14 — Security, Privacy, Compliance & Risk

**Owner:** Security/Compliance Lead

## CT-E047 — Application security baseline

**Objective:** Áp dụng secure SDLC, OWASP ASVS, secrets, audit và vulnerability management.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0177 — Là Security, tôi muốn thiết lập ASVS control matrix cho web/API/admin để có baseline kiểm thử.

- **Priority:** P0
- **Tags:** Security, QA, BA
- **Acceptance criteria:** Given Security có quyền hợp lệ; When thiết lập ASVS control matrix cho web/API/admin; Then kết quả giúp có baseline kiểm thử; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0885` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — thiết lập ASVS control matrix cho web/API/admin  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0886` **Security** — Security: Threat model và security control — thiết lập ASVS control matrix cho web/API/admin  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0887` **QA** — QA: Test plan và automated tests — thiết lập ASVS control matrix cho web/API/admin  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0178 — Là Security, tôi muốn quét SAST/SCA/container/IaC trong CI để ngăn lỗ hổng vào production.

- **Priority:** P0
- **Tags:** Security, DevOps
- **Acceptance criteria:** Given Security có quyền hợp lệ; When quét SAST/SCA/container/IaC trong CI; Then kết quả giúp ngăn lỗ hổng vào production; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0888` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — quét SAST/SCA/container/IaC trong CI  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0889` **Security** — Security: Threat model và security control — quét SAST/SCA/container/IaC trong CI  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0890` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — quét SAST/SCA/container/IaC trong CI  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0891` **QA** — QA: Test plan và automated tests — quét SAST/SCA/container/IaC trong CI  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0179 — Là Security, tôi muốn quản lý secrets bằng vault/KMS và rotation để không lộ khóa.

- **Priority:** P0
- **Tags:** Security, DevOps, SRE
- **Acceptance criteria:** Given Security có quyền hợp lệ; When quản lý secrets bằng vault/KMS và rotation; Then kết quả giúp không lộ khóa; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0892` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — quản lý secrets bằng vault/KMS và rotation  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0893` **Security** — Security: Threat model và security control — quản lý secrets bằng vault/KMS và rotation  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0894` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — quản lý secrets bằng vault/KMS và rotation  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0895` **QA** — QA: Test plan và automated tests — quản lý secrets bằng vault/KMS và rotation  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0180 — Là Admin, tôi muốn mọi hành động sensitive có audit immutable để đáp ứng điều tra.

- **Priority:** P0
- **Tags:** Security, Audit, BE
- **Acceptance criteria:** Given Admin có quyền hợp lệ; When mọi hành động sensitive có audit immutable; Then kết quả giúp đáp ứng điều tra; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0896` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — mọi hành động sensitive có audit immutable  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0897` **BE** — BE: Thiết kế domain/API/schema và implement service — mọi hành động sensitive có audit immutable  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0898` **Security** — Security: Threat model và security control — mọi hành động sensitive có audit immutable  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0899` **QA** — QA: Test plan và automated tests — mọi hành động sensitive có audit immutable  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E048 — Data protection and retention

**Objective:** Phân loại dữ liệu, mã hóa PII, DSR, retention, breach response.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0181 — Là Compliance, tôi muốn phân loại dữ liệu theo PII/sensitive/payment/AI để áp kiểm soát đúng.

- **Priority:** P0
- **Tags:** Privacy, Data, Security
- **Acceptance criteria:** Given Compliance có quyền hợp lệ; When phân loại dữ liệu theo PII/sensitive/payment/AI; Then kết quả giúp áp kiểm soát đúng; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0900` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — phân loại dữ liệu theo PII/sensitive/payment/AI  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0901` **BE** — BE: Thiết kế domain/API/schema và implement service — phân loại dữ liệu theo PII/sensitive/payment/AI  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0902` **Security** — Security: Threat model và security control — phân loại dữ liệu theo PII/sensitive/payment/AI  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0903` **Data** — Data: Event taxonomy/data model/dashboard metric — phân loại dữ liệu theo PII/sensitive/payment/AI  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0904` **QA** — QA: Test plan và automated tests — phân loại dữ liệu theo PII/sensitive/payment/AI  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0182 — Là System, tôi muốn mã hóa field-level cho PII quan trọng để giảm rủi ro rò rỉ.

- **Priority:** P0
- **Tags:** Privacy, Security, BE
- **Acceptance criteria:** Given System có quyền hợp lệ; When mã hóa field-level cho PII quan trọng; Then kết quả giúp giảm rủi ro rò rỉ; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0905` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — mã hóa field-level cho PII quan trọng  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0906` **BE** — BE: Thiết kế domain/API/schema và implement service — mã hóa field-level cho PII quan trọng  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0907` **Security** — Security: Threat model và security control — mã hóa field-level cho PII quan trọng  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0908` **QA** — QA: Test plan và automated tests — mã hóa field-level cho PII quan trọng  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0183 — Là Compliance, tôi muốn chạy breach response workflow trong 72h khi cần để tuân thủ nghĩa vụ thông báo.

- **Priority:** P0
- **Tags:** Privacy, Ops, Security
- **Acceptance criteria:** Given Compliance có quyền hợp lệ; When chạy breach response workflow trong 72h khi cần; Then kết quả giúp tuân thủ nghĩa vụ thông báo; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0909` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — chạy breach response workflow trong 72h khi cần  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0910` **BE** — BE: Thiết kế domain/API/schema và implement service — chạy breach response workflow trong 72h khi cần  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0911` **Security** — Security: Threat model và security control — chạy breach response workflow trong 72h khi cần  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0912` **QA** — QA: Test plan và automated tests — chạy breach response workflow trong 72h khi cần  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0184 — Là Traveller, tôi muốn xóa/anonymize dữ liệu theo policy và legal hold để tôn trọng quyền dữ liệu.

- **Priority:** P0
- **Tags:** Privacy, BE, Ops
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When xóa/anonymize dữ liệu theo policy và legal hold; Then kết quả giúp tôn trọng quyền dữ liệu; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0913` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xóa/anonymize dữ liệu theo policy và legal hold  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0914` **BE** — BE: Thiết kế domain/API/schema và implement service — xóa/anonymize dữ liệu theo policy và legal hold  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0915` **Security** — Security: Threat model và security control — xóa/anonymize dữ liệu theo policy và legal hold  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0916` **QA** — QA: Test plan và automated tests — xóa/anonymize dữ liệu theo policy và legal hold  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E049 — Payment and PCI scope management

**Objective:** Giảm scope PCI bằng hosted/tokenized payment và không lưu card data.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0185 — Là Security, tôi muốn thiết kế payment flow không lưu PAN/CVV để giảm scope PCI.

- **Priority:** P0
- **Tags:** Payment, Security, Architecture
- **Acceptance criteria:** Given Security có quyền hợp lệ; When thiết kế payment flow không lưu PAN/CVV; Then kết quả giúp giảm scope PCI; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0917` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — thiết kế payment flow không lưu PAN/CVV  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0918` **BE** — BE: Thiết kế domain/API/schema và implement service — thiết kế payment flow không lưu PAN/CVV  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0919` **Security** — Security: Threat model và security control — thiết kế payment flow không lưu PAN/CVV  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0920` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — thiết kế payment flow không lưu PAN/CVV  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0921` **QA** — QA: Test plan và automated tests — thiết kế payment flow không lưu PAN/CVV  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0186 — Là QA, tôi muốn test không log payment secret/card data để ngăn leakage.

- **Priority:** P0
- **Tags:** Payment, Security, QA
- **Acceptance criteria:** Given QA có quyền hợp lệ; When test không log payment secret/card data; Then kết quả giúp ngăn leakage; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0922` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — test không log payment secret/card data  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0923` **BE** — BE: Thiết kế domain/API/schema và implement service — test không log payment secret/card data  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0924` **Security** — Security: Threat model và security control — test không log payment secret/card data  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0925` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — test không log payment secret/card data  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0926` **QA** — QA: Test plan và automated tests — test không log payment secret/card data  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0187 — Là Finance, tôi muốn theo dõi token/payment reference thay vì card data để đối soát vẫn đủ.

- **Priority:** P0
- **Tags:** Payment, Finance, BE
- **Acceptance criteria:** Given Finance có quyền hợp lệ; When theo dõi token/payment reference thay vì card data; Then kết quả giúp đối soát vẫn đủ; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0927` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — theo dõi token/payment reference thay vì card data  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0928` **BE** — BE: Thiết kế domain/API/schema và implement service — theo dõi token/payment reference thay vì card data  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0929` **Security** — Security: Threat model và security control — theo dõi token/payment reference thay vì card data  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0930` **Data** — Data: Event taxonomy/data model/dashboard metric — theo dõi token/payment reference thay vì card data  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0931` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — theo dõi token/payment reference thay vì card data  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0932` **QA** — QA: Test plan và automated tests — theo dõi token/payment reference thay vì card data  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E050 — AI and MCP security

**Objective:** Bảo vệ AI agent khỏi prompt injection, data exfiltration, unsafe tool call.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0188 — Là Security, tôi muốn threat model AI/MCP tools để hiểu attack surface.

- **Priority:** P0
- **Tags:** AI, MCP, Security
- **Acceptance criteria:** Given Security có quyền hợp lệ; When threat model AI/MCP tools; Then kết quả giúp hiểu attack surface; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0933` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — threat model AI/MCP tools  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0934` **AI** — AI: Thiết kế prompt/tool schema/eval cases — threat model AI/MCP tools  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0935` **Security** — Security: Threat model và security control — threat model AI/MCP tools  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0936` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — threat model AI/MCP tools  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0937` **QA** — QA: Test plan và automated tests — threat model AI/MCP tools  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0189 — Là System, tôi muốn sanitize retrieved documents và external tool output để giảm prompt injection gián tiếp.

- **Priority:** P0
- **Tags:** AI, Security, BE
- **Acceptance criteria:** Given System có quyền hợp lệ; When sanitize retrieved documents và external tool output; Then kết quả giúp giảm prompt injection gián tiếp; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0938` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — sanitize retrieved documents và external tool output  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0939` **BE** — BE: Thiết kế domain/API/schema và implement service — sanitize retrieved documents và external tool output  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0940` **AI** — AI: Thiết kế prompt/tool schema/eval cases — sanitize retrieved documents và external tool output  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0941` **Security** — Security: Threat model và security control — sanitize retrieved documents và external tool output  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0942` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — sanitize retrieved documents và external tool output  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0943` **QA** — QA: Test plan và automated tests — sanitize retrieved documents và external tool output  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0190 — Là System, tôi muốn tool ACL theo user/tenant/action risk để AI không vượt quyền.

- **Priority:** P0
- **Tags:** AI, MCP, RBAC
- **Acceptance criteria:** Given System có quyền hợp lệ; When tool ACL theo user/tenant/action risk; Then kết quả giúp AI không vượt quyền; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0944` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tool ACL theo user/tenant/action risk  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0945` **BE** — BE: Thiết kế domain/API/schema và implement service — tool ACL theo user/tenant/action risk  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0946` **AI** — AI: Thiết kế prompt/tool schema/eval cases — tool ACL theo user/tenant/action risk  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0947` **Security** — Security: Threat model và security control — tool ACL theo user/tenant/action risk  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0948` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — tool ACL theo user/tenant/action risk  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0949` **QA** — QA: Test plan và automated tests — tool ACL theo user/tenant/action risk  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0191 — Là QA, tôi muốn chạy adversarial test suite định kỳ để phát hiện regression.

- **Priority:** P0
- **Tags:** AI, Security, QA
- **Acceptance criteria:** Given QA có quyền hợp lệ; When chạy adversarial test suite định kỳ; Then kết quả giúp phát hiện regression; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0950` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — chạy adversarial test suite định kỳ  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0951` **AI** — AI: Thiết kế prompt/tool schema/eval cases — chạy adversarial test suite định kỳ  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0952` **Security** — Security: Threat model và security control — chạy adversarial test suite định kỳ  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0953` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — chạy adversarial test suite định kỳ  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0954` **QA** — QA: Test plan và automated tests — chạy adversarial test suite định kỳ  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP15 — Architecture, API, Data & Platform Core

**Owner:** Solution Architect

## CT-E051 — Modular architecture and bounded contexts

**Objective:** Tận dụng Spring ecosystem nhưng vẫn tách domain rõ để scale dài hạn.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0192 — Là Architect, tôi muốn định nghĩa bounded context và module boundaries để team làm song song không xung đột.

- **Priority:** P0
- **Tags:** Architecture, DDD, BE
- **Acceptance criteria:** Given Architect có quyền hợp lệ; When định nghĩa bounded context và module boundaries; Then kết quả giúp team làm song song không xung đột; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0955` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — định nghĩa bounded context và module boundaries  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0956` **BE** — BE: Thiết kế domain/API/schema và implement service — định nghĩa bounded context và module boundaries  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0957` **QA** — QA: Test plan và automated tests — định nghĩa bounded context và module boundaries  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0193 — Là Developer, tôi muốn dùng hexagonal architecture cho domain/application/infrastructure/interfaces để dễ thay adapter.

- **Priority:** P0
- **Tags:** Architecture, BE, QA
- **Acceptance criteria:** Given Developer có quyền hợp lệ; When dùng hexagonal architecture cho domain/application/infrastructure/interfaces; Then kết quả giúp dễ thay adapter; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0958` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — dùng hexagonal architecture cho...  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0959` **BE** — BE: Thiết kế domain/API/schema và implement service — dùng hexagonal architecture cho...  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0960` **QA** — QA: Test plan và automated tests — dùng hexagonal architecture cho...  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0194 — Là Architect, tôi muốn quản lý shared kernel và anti-corruption layer để tránh coupling sai.

- **Priority:** P0
- **Tags:** Architecture, DDD
- **Acceptance criteria:** Given Architect có quyền hợp lệ; When quản lý shared kernel và anti-corruption layer; Then kết quả giúp tránh coupling sai; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0961` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — quản lý shared kernel và anti-corruption layer  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0962` **QA** — QA: Test plan và automated tests — quản lý shared kernel và anti-corruption layer  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0195 — Là Tech Lead, tôi muốn đặt dependency rules và enforce bằng tests để không phá ranh giới module.

- **Priority:** P0
- **Tags:** Architecture, DevOps, QA
- **Acceptance criteria:** Given Tech Lead có quyền hợp lệ; When đặt dependency rules và enforce bằng tests; Then kết quả giúp không phá ranh giới module; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0963` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — đặt dependency rules và enforce bằng tests  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0964` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — đặt dependency rules và enforce bằng tests  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0965` **QA** — QA: Test plan và automated tests — đặt dependency rules và enforce bằng tests  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E052 — API gateway, REST contracts and API versioning

**Objective:** Tạo API nhất quán, versioned, documented, rate-limited.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0196 — Là Frontend Dev, tôi muốn dùng OpenAPI contract cho typed client để giảm lỗi tích hợp.

- **Priority:** P0
- **Tags:** API, FE, BE
- **Acceptance criteria:** Given Frontend Dev có quyền hợp lệ; When dùng OpenAPI contract cho typed client; Then kết quả giúp giảm lỗi tích hợp; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0966` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — dùng OpenAPI contract cho typed client  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0967` **UX** — UX: Thiết kế wireframe/UI states — dùng OpenAPI contract cho typed client  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0968` **FE** — FE: Implement UI và client integration — dùng OpenAPI contract cho typed client  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0969` **BE** — BE: Thiết kế domain/API/schema và implement service — dùng OpenAPI contract cho typed client  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0970` **QA** — QA: Test plan và automated tests — dùng OpenAPI contract cho typed client  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0197 — Là Partner, tôi muốn gọi public/partner API có auth, quota, versioning để tích hợp ổn định.

- **Priority:** P1
- **Tags:** API, Security, BE
- **Acceptance criteria:** Given Partner có quyền hợp lệ; When gọi public/partner API có auth, quota, versioning; Then kết quả giúp tích hợp ổn định; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0971` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — gọi public/partner API có auth, quota, versioning  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0972` **BE** — BE: Thiết kế domain/API/schema và implement service — gọi public/partner API có auth, quota, versioning  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0973` **Security** — Security: Threat model và security control — gọi public/partner API có auth, quota, versioning  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0974` **QA** — QA: Test plan và automated tests — gọi public/partner API có auth, quota, versioning  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0198 — Là SRE, tôi muốn rate-limit theo user/org/IP/tool/supplier để chịu tải và chống abuse.

- **Priority:** P0
- **Tags:** API, SRE, Security
- **Acceptance criteria:** Given SRE có quyền hợp lệ; When rate-limit theo user/org/IP/tool/supplier; Then kết quả giúp chịu tải và chống abuse; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0975` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — rate-limit theo user/org/IP/tool/supplier  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0976` **BE** — BE: Thiết kế domain/API/schema và implement service — rate-limit theo user/org/IP/tool/supplier  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0977` **Security** — Security: Threat model và security control — rate-limit theo user/org/IP/tool/supplier  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0978` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — rate-limit theo user/org/IP/tool/supplier  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0979` **QA** — QA: Test plan và automated tests — rate-limit theo user/org/IP/tool/supplier  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0199 — Là QA, tôi muốn contract test API trước release để không breaking change.

- **Priority:** P0
- **Tags:** API, QA, DevOps
- **Acceptance criteria:** Given QA có quyền hợp lệ; When contract test API trước release; Then kết quả giúp không breaking change; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0980` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — contract test API trước release  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0981` **BE** — BE: Thiết kế domain/API/schema và implement service — contract test API trước release  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0982` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — contract test API trước release  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0983` **QA** — QA: Test plan và automated tests — contract test API trước release  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E053 — Data model, migrations and JPA performance

**Objective:** Postgres/JPA schema chuẩn, query tốt, migration an toàn.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0200 — Là Backend Dev, tôi muốn quản lý schema bằng Flyway và rollback plan để deploy an toàn.

- **Priority:** P0
- **Tags:** Database, BE, DevOps
- **Acceptance criteria:** Given Backend Dev có quyền hợp lệ; When quản lý schema bằng Flyway và rollback plan; Then kết quả giúp deploy an toàn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0984` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — quản lý schema bằng Flyway và rollback plan  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0985` **BE** — BE: Thiết kế domain/API/schema và implement service — quản lý schema bằng Flyway và rollback plan  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0986` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — quản lý schema bằng Flyway và rollback plan  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0987` **QA** — QA: Test plan và automated tests — quản lý schema bằng Flyway và rollback plan  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0201 — Là Backend Dev, tôi muốn tối ưu JPA fetch plan để tránh N+1 để giữ latency ổn định.

- **Priority:** P0
- **Tags:** JPA, BE, QA
- **Acceptance criteria:** Given Backend Dev có quyền hợp lệ; When tối ưu JPA fetch plan để tránh N+1; Then kết quả giúp giữ latency ổn định; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0988` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tối ưu JPA fetch plan để tránh N+1  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0989` **BE** — BE: Thiết kế domain/API/schema và implement service — tối ưu JPA fetch plan để tránh N+1  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0990` **QA** — QA: Test plan và automated tests — tối ưu JPA fetch plan để tránh N+1  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0202 — Là DBA, tôi muốn thiết kế partition/index cho booking/payment/event lớn để chịu tải dài hạn.

- **Priority:** P0
- **Tags:** Database, SRE, BE
- **Acceptance criteria:** Given DBA có quyền hợp lệ; When thiết kế partition/index cho booking/payment/event lớn; Then kết quả giúp chịu tải dài hạn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0991` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — thiết kế partition/index cho booking/payment/event lớn  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0992` **BE** — BE: Thiết kế domain/API/schema và implement service — thiết kế partition/index cho booking/payment/event lớn  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0993` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — thiết kế partition/index cho booking/payment/event lớn  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0994` **QA** — QA: Test plan và automated tests — thiết kế partition/index cho booking/payment/event lớn  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0203 — Là QA, tôi muốn chạy migration test trên dataset lớn để phát hiện migration chậm/lỗi.

- **Priority:** P0
- **Tags:** Database, QA, SRE
- **Acceptance criteria:** Given QA có quyền hợp lệ; When chạy migration test trên dataset lớn; Then kết quả giúp phát hiện migration chậm/lỗi; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0995` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — chạy migration test trên dataset lớn  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0996` **BE** — BE: Thiết kế domain/API/schema và implement service — chạy migration test trên dataset lớn  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0997` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — chạy migration test trên dataset lớn  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T0998` **QA** — QA: Test plan và automated tests — chạy migration test trên dataset lớn  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E054 — Search, cache and event backbone

**Objective:** Dùng cache/search/event phù hợp để chịu tải cao nhưng không mất tính nhất quán booking.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0204 — Là System, tôi muốn đồng bộ search index từ catalog/availability events để search nhanh và tương đối mới.

- **Priority:** P0
- **Tags:** Search, Event, BE
- **Acceptance criteria:** Given System có quyền hợp lệ; When đồng bộ search index từ catalog/availability events; Then kết quả giúp search nhanh và tương đối mới; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T0999` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — đồng bộ search index từ catalog/availability events  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1000` **BE** — BE: Thiết kế domain/API/schema và implement service — đồng bộ search index từ catalog/availability events  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1001` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — đồng bộ search index từ catalog/availability events  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1002` **QA** — QA: Test plan và automated tests — đồng bộ search index từ catalog/availability events  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0205 — Là System, tôi muốn dùng Redis cache có invalidation rõ ràng để giảm tải DB/supplier.

- **Priority:** P0
- **Tags:** Cache, SRE, BE
- **Acceptance criteria:** Given System có quyền hợp lệ; When dùng Redis cache có invalidation rõ ràng; Then kết quả giúp giảm tải DB/supplier; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1003` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — dùng Redis cache có invalidation rõ ràng  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1004` **BE** — BE: Thiết kế domain/API/schema và implement service — dùng Redis cache có invalidation rõ ràng  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1005` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — dùng Redis cache có invalidation rõ ràng  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1006` **QA** — QA: Test plan và automated tests — dùng Redis cache có invalidation rõ ràng  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0206 — Là System, tôi muốn dùng transactional outbox cho booking/payment events để không mất event.

- **Priority:** P0
- **Tags:** Event, BE, SRE
- **Acceptance criteria:** Given System có quyền hợp lệ; When dùng transactional outbox cho booking/payment events; Then kết quả giúp không mất event; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1007` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — dùng transactional outbox cho booking/payment events  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1008` **BE** — BE: Thiết kế domain/API/schema và implement service — dùng transactional outbox cho booking/payment events  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1009` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — dùng transactional outbox cho booking/payment events  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1010` **QA** — QA: Test plan và automated tests — dùng transactional outbox cho booking/payment events  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0207 — Là SRE, tôi muốn quản lý DLQ/replay tools cho event failed để khôi phục sự cố.

- **Priority:** P0
- **Tags:** Event, SRE, Admin
- **Acceptance criteria:** Given SRE có quyền hợp lệ; When quản lý DLQ/replay tools cho event failed; Then kết quả giúp khôi phục sự cố; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1011` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — quản lý DLQ/replay tools cho event failed  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1012` **UX** — UX: Thiết kế wireframe/UI states — quản lý DLQ/replay tools cho event failed  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1013` **FE** — FE: Implement UI và client integration — quản lý DLQ/replay tools cho event failed  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1014` **BE** — BE: Thiết kế domain/API/schema và implement service — quản lý DLQ/replay tools cho event failed  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1015` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — quản lý DLQ/replay tools cho event failed  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1016` **QA** — QA: Test plan và automated tests — quản lý DLQ/replay tools cho event failed  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP16 — SRE, High Load, CI/CD & Quality Engineering

**Owner:** SRE/QA Lead

## CT-E055 — Kubernetes production topology and HA

**Objective:** Triển khai chịu tải cao với HPA, PDB, topology spread, backup/restore.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0208 — Là SRE, tôi muốn deploy stateless services với HPA/PDB/topology spread để chịu node failure và traffic spike.

- **Priority:** P0
- **Tags:** K8s, SRE, DevOps
- **Acceptance criteria:** Given SRE có quyền hợp lệ; When deploy stateless services với HPA/PDB/topology spread; Then kết quả giúp chịu node failure và traffic spike; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1017` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — deploy stateless services với HPA/PDB/topology spread  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1018` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — deploy stateless services với HPA/PDB/topology spread  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1019` **QA** — QA: Test plan và automated tests — deploy stateless services với HPA/PDB/topology spread  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0209 — Là SRE, tôi muốn thiết kế stateful layer HA và backup/restore để bảo vệ dữ liệu.

- **Priority:** P0
- **Tags:** K8s, Database, SRE
- **Acceptance criteria:** Given SRE có quyền hợp lệ; When thiết kế stateful layer HA và backup/restore; Then kết quả giúp bảo vệ dữ liệu; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1020` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — thiết kế stateful layer HA và backup/restore  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1021` **BE** — BE: Thiết kế domain/API/schema và implement service — thiết kế stateful layer HA và backup/restore  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1022` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — thiết kế stateful layer HA và backup/restore  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1023` **QA** — QA: Test plan và automated tests — thiết kế stateful layer HA và backup/restore  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0210 — Là SRE, tôi muốn quản lý config/secrets per environment để deploy an toàn.

- **Priority:** P0
- **Tags:** DevOps, Security, SRE
- **Acceptance criteria:** Given SRE có quyền hợp lệ; When quản lý config/secrets per environment; Then kết quả giúp deploy an toàn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1024` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — quản lý config/secrets per environment  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1025` **Security** — Security: Threat model và security control — quản lý config/secrets per environment  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1026` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — quản lý config/secrets per environment  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1027` **QA** — QA: Test plan và automated tests — quản lý config/secrets per environment  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0211 — Là SRE, tôi muốn diễn tập restore và failover để biết RTO/RPO thực tế.

- **Priority:** P0
- **Tags:** DR, SRE, QA
- **Acceptance criteria:** Given SRE có quyền hợp lệ; When diễn tập restore và failover; Then kết quả giúp biết RTO/RPO thực tế; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1028` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — diễn tập restore và failover  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1029` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — diễn tập restore và failover  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1030` **QA** — QA: Test plan và automated tests — diễn tập restore và failover  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E056 — Observability, SLO and incident response

**Objective:** Trace booking/AI/supplier/payment end-to-end bằng logs, metrics, traces.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0212 — Là SRE, tôi muốn instrument OpenTelemetry cho gateway/core/AI/supplier/payment để trace end-to-end.

- **Priority:** P0
- **Tags:** Observability, SRE, BE
- **Acceptance criteria:** Given SRE có quyền hợp lệ; When instrument OpenTelemetry cho gateway/core/AI/supplier/payment; Then kết quả giúp trace end-to-end; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1031` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — instrument OpenTelemetry cho gateway/core/AI/supplier/payment  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1032` **BE** — BE: Thiết kế domain/API/schema và implement service — instrument OpenTelemetry cho gateway/core/AI/supplier/payment  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1033` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — instrument OpenTelemetry cho gateway/core/AI/supplier/payment  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1034` **QA** — QA: Test plan và automated tests — instrument OpenTelemetry cho gateway/core/AI/supplier/payment  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0213 — Là SRE, tôi muốn tạo SLO dashboard cho search, booking, payment, AI, supplier để quản lý độ tin cậy.

- **Priority:** P0
- **Tags:** Observability, SRE, BI
- **Acceptance criteria:** Given SRE có quyền hợp lệ; When tạo SLO dashboard cho search, booking, payment, AI, supplier; Then kết quả giúp quản lý độ tin cậy; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1035` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tạo SLO dashboard cho search, booking, payment, AI, supplier  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1036` **Data** — Data: Event taxonomy/data model/dashboard metric — tạo SLO dashboard cho search, booking, payment, AI, supplier  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1037` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — tạo SLO dashboard cho search, booking, payment, AI, supplier  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1038` **QA** — QA: Test plan và automated tests — tạo SLO dashboard cho search, booking, payment, AI, supplier  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0214 — Là SRE, tôi muốn tạo alert và runbook theo incident type để phản ứng nhanh.

- **Priority:** P0
- **Tags:** Observability, SRE, Ops
- **Acceptance criteria:** Given SRE có quyền hợp lệ; When tạo alert và runbook theo incident type; Then kết quả giúp phản ứng nhanh; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1039` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tạo alert và runbook theo incident type  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1040` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — tạo alert và runbook theo incident type  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1041` **QA** — QA: Test plan và automated tests — tạo alert và runbook theo incident type  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0215 — Là Engineering Manager, tôi muốn postmortem template và error budget policy để học từ sự cố.

- **Priority:** P1
- **Tags:** SRE, Governance
- **Acceptance criteria:** Given Engineering Manager có quyền hợp lệ; When postmortem template và error budget policy; Then kết quả giúp học từ sự cố; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1042` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — postmortem template và error budget policy  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1043` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — postmortem template và error budget policy  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1044` **QA** — QA: Test plan và automated tests — postmortem template và error budget policy  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E057 — Load, performance and resilience testing

**Objective:** Chứng minh hệ thống đạt SLO dưới tải cao và supplier failure.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0216 — Là QA/SRE, tôi muốn chạy load test search 1,000 QPS peak để đạt target chịu tải.

- **Priority:** P0
- **Tags:** LoadTest, SRE, QA
- **Acceptance criteria:** Given QA/SRE có quyền hợp lệ; When chạy load test search 1,000 QPS peak; Then kết quả giúp đạt target chịu tải; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1045` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — chạy load test search 1,000 QPS peak  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1046` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — chạy load test search 1,000 QPS peak  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1047` **QA** — QA: Test plan và automated tests — chạy load test search 1,000 QPS peak  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0217 — Là QA/SRE, tôi muốn chạy booking race/no-oversell tests để đảm bảo inventory đúng.

- **Priority:** P0
- **Tags:** LoadTest, Booking, QA
- **Acceptance criteria:** Given QA/SRE có quyền hợp lệ; When chạy booking race/no-oversell tests; Then kết quả giúp đảm bảo inventory đúng; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1048` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — chạy booking race/no-oversell tests  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1049` **BE** — BE: Thiết kế domain/API/schema và implement service — chạy booking race/no-oversell tests  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1050` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — chạy booking race/no-oversell tests  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1051` **QA** — QA: Test plan và automated tests — chạy booking race/no-oversell tests  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0218 — Là QA/SRE, tôi muốn test supplier timeout/partial outage/circuit breaker để degrade an toàn.

- **Priority:** P0
- **Tags:** LoadTest, SupplierAdapter, SRE
- **Acceptance criteria:** Given QA/SRE có quyền hợp lệ; When test supplier timeout/partial outage/circuit breaker; Then kết quả giúp degrade an toàn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1052` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — test supplier timeout/partial outage/circuit breaker  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1053` **BE** — BE: Thiết kế domain/API/schema và implement service — test supplier timeout/partial outage/circuit breaker  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1054` **Integration** — Integration: Implement adapter/contract test/mock — test supplier timeout/partial outage/circuit breaker  
    AC: Adapter dùng canonical contract; timeout/retry/circuit breaker; sandbox/mock contract tests pass. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1055` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — test supplier timeout/partial outage/circuit breaker  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1056` **QA** — QA: Test plan và automated tests — test supplier timeout/partial outage/circuit breaker  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0219 — Là QA/SRE, tôi muốn test payment webhook duplicate/out-of-order để không confirm sai.

- **Priority:** P0
- **Tags:** LoadTest, Payment, QA
- **Acceptance criteria:** Given QA/SRE có quyền hợp lệ; When test payment webhook duplicate/out-of-order; Then kết quả giúp không confirm sai; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1057` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — test payment webhook duplicate/out-of-order  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1058` **BE** — BE: Thiết kế domain/API/schema và implement service — test payment webhook duplicate/out-of-order  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1059` **Security** — Security: Threat model và security control — test payment webhook duplicate/out-of-order  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1060` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — test payment webhook duplicate/out-of-order  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1061` **QA** — QA: Test plan và automated tests — test payment webhook duplicate/out-of-order  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E058 — CI/CD, test pyramid and release quality gates

**Objective:** Tự động hóa build/test/security/deploy với chất lượng cao.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0220 — Là Developer, tôi muốn CI chạy unit/integration/contract/security tests để phát hiện lỗi sớm.

- **Priority:** P0
- **Tags:** DevOps, QA, Security
- **Acceptance criteria:** Given Developer có quyền hợp lệ; When CI chạy unit/integration/contract/security tests; Then kết quả giúp phát hiện lỗi sớm; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1062` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — CI chạy unit/integration/contract/security tests  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1063` **Security** — Security: Threat model và security control — CI chạy unit/integration/contract/security tests  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1064` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — CI chạy unit/integration/contract/security tests  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1065` **QA** — QA: Test plan và automated tests — CI chạy unit/integration/contract/security tests  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0221 — Là QA, tôi muốn test pyramid có unit, integration, contract, E2E, load, AI eval để bao phủ rủi ro chính.

- **Priority:** P0
- **Tags:** QA, DevOps
- **Acceptance criteria:** Given QA có quyền hợp lệ; When test pyramid có unit, integration, contract, E2E, load, AI eval; Then kết quả giúp bao phủ rủi ro chính; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1066` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — test pyramid có unit, integration, contract, E2E, load, AI eval  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1067` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — test pyramid có unit, integration, contract, E2E, load, AI eval  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1068` **QA** — QA: Test plan và automated tests — test pyramid có unit, integration, contract, E2E, load, AI eval  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0222 — Là Release Manager, tôi muốn release gate dựa trên DoD, test, SLO, security scan để không release thiếu chất lượng.

- **Priority:** P0
- **Tags:** DevOps, Governance, QA
- **Acceptance criteria:** Given Release Manager có quyền hợp lệ; When release gate dựa trên DoD, test, SLO, security scan; Then kết quả giúp không release thiếu chất lượng; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1069` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — release gate dựa trên DoD, test, SLO, security scan  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1070` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — release gate dựa trên DoD, test, SLO, security scan  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1071` **QA** — QA: Test plan và automated tests — release gate dựa trên DoD, test, SLO, security scan  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0223 — Là DevOps, tôi muốn canary/blue-green deploy và rollback để giảm rủi ro deploy.

- **Priority:** P1
- **Tags:** DevOps, K8s, SRE
- **Acceptance criteria:** Given DevOps có quyền hợp lệ; When canary/blue-green deploy và rollback; Then kết quả giúp giảm rủi ro deploy; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1072` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — canary/blue-green deploy và rollback  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1073` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — canary/blue-green deploy và rollback  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1074` **QA** — QA: Test plan và automated tests — canary/blue-green deploy và rollback  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP17 — Frontend Web, Mobile/PWA, Design System & Accessibility

**Owner:** Frontend Lead

## CT-E059 — Design system and UX foundation

**Objective:** Một hệ thống UI nhất quán cho traveller, B2B, operator, admin.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0224 — Là Designer, tôi muốn tạo design tokens, components, form patterns, table patterns để UI đồng nhất.

- **Priority:** P0
- **Tags:** UX, FE
- **Acceptance criteria:** Given Designer có quyền hợp lệ; When tạo design tokens, components, form patterns, table patterns; Then kết quả giúp UI đồng nhất; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1075` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tạo design tokens, components, form patterns, table patterns  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1076` **UX** — UX: Thiết kế wireframe/UI states — tạo design tokens, components, form patterns, table patterns  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1077` **FE** — FE: Implement UI và client integration — tạo design tokens, components, form patterns, table patterns  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1078` **QA** — QA: Test plan và automated tests — tạo design tokens, components, form patterns, table patterns  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0225 — Là Frontend Dev, tôi muốn implement component library với Storybook để reuse nhanh.

- **Priority:** P0
- **Tags:** FE, QA
- **Acceptance criteria:** Given Frontend Dev có quyền hợp lệ; When implement component library với Storybook; Then kết quả giúp reuse nhanh; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1079` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — implement component library với Storybook  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1080` **UX** — UX: Thiết kế wireframe/UI states — implement component library với Storybook  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1081` **FE** — FE: Implement UI và client integration — implement component library với Storybook  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1082` **QA** — QA: Test plan và automated tests — implement component library với Storybook  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0226 — Là QA, tôi muốn visual regression test components để không vỡ giao diện.

- **Priority:** P1
- **Tags:** FE, QA, DevOps
- **Acceptance criteria:** Given QA có quyền hợp lệ; When visual regression test components; Then kết quả giúp không vỡ giao diện; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1083` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — visual regression test components  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1084` **UX** — UX: Thiết kế wireframe/UI states — visual regression test components  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1085` **FE** — FE: Implement UI và client integration — visual regression test components  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1086` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — visual regression test components  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1087` **QA** — QA: Test plan và automated tests — visual regression test components  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0227 — Là Accessibility, tôi muốn đạt WCAG 2.2 AA cho flow chính để mọi người dùng tiếp cận được.

- **Priority:** P0
- **Tags:** Accessibility, FE, QA
- **Acceptance criteria:** Given Accessibility có quyền hợp lệ; When đạt WCAG 2.2 AA cho flow chính; Then kết quả giúp mọi người dùng tiếp cận được; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1088` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — đạt WCAG 2.2 AA cho flow chính  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1089` **UX** — UX: Thiết kế wireframe/UI states — đạt WCAG 2.2 AA cho flow chính  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1090` **FE** — FE: Implement UI và client integration — đạt WCAG 2.2 AA cho flow chính  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1091` **QA** — QA: Test plan và automated tests — đạt WCAG 2.2 AA cho flow chính  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E060 — Traveller web application

**Objective:** Giao diện traveller cho search, detail, AI chat, quote, booking, payment, my trips.  
**Priority:** P0  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0228 — Là Traveller, tôi muốn dùng responsive web cho search/detail/booking để đặt tour trên mobile/desktop.

- **Priority:** P0
- **Tags:** FE, Traveller, QA
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When dùng responsive web cho search/detail/booking; Then kết quả giúp đặt tour trên mobile/desktop; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1092` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — dùng responsive web cho search/detail/booking  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1093` **UX** — UX: Thiết kế wireframe/UI states — dùng responsive web cho search/detail/booking  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1094` **FE** — FE: Implement UI và client integration — dùng responsive web cho search/detail/booking  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1095` **QA** — QA: Test plan và automated tests — dùng responsive web cho search/detail/booking  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0229 — Là Traveller, tôi muốn AI chat UI có streaming, tool result card và confirmation button để trải nghiệm rõ ràng.

- **Priority:** P0
- **Tags:** FE, AI, UX
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When AI chat UI có streaming, tool result card và confirmation button; Then kết quả giúp trải nghiệm rõ ràng; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1096` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — AI chat UI có streaming, tool result card và confirmation button  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1097` **UX** — UX: Thiết kế wireframe/UI states — AI chat UI có streaming, tool result card và confirmation button  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1098` **FE** — FE: Implement UI và client integration — AI chat UI có streaming, tool result card và confirmation button  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1099` **AI** — AI: Thiết kế prompt/tool schema/eval cases — AI chat UI có streaming, tool result card và confirmation button  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1100` **Security** — Security: Threat model và security control — AI chat UI có streaming, tool result card và confirmation button  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1101` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — AI chat UI có streaming, tool result card và confirmation button  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1102` **QA** — QA: Test plan và automated tests — AI chat UI có streaming, tool result card và confirmation button  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0230 — Là Traveller, tôi muốn My Trips hiển thị booking, voucher, cancel/refund actions để tự phục vụ sau đặt.

- **Priority:** P0
- **Tags:** FE, Booking, QA
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When My Trips hiển thị booking, voucher, cancel/refund actions; Then kết quả giúp tự phục vụ sau đặt; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1103` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — My Trips hiển thị booking, voucher, cancel/refund actions  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1104` **UX** — UX: Thiết kế wireframe/UI states — My Trips hiển thị booking, voucher, cancel/refund actions  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1105` **FE** — FE: Implement UI và client integration — My Trips hiển thị booking, voucher, cancel/refund actions  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1106` **BE** — BE: Thiết kế domain/API/schema và implement service — My Trips hiển thị booking, voucher, cancel/refund actions  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1107` **QA** — QA: Test plan và automated tests — My Trips hiển thị booking, voucher, cancel/refund actions  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0231 — Là Frontend Dev, tôi muốn xử lý loading/empty/error/offline states để UX không bị cụt.

- **Priority:** P0
- **Tags:** FE, QA
- **Acceptance criteria:** Given Frontend Dev có quyền hợp lệ; When xử lý loading/empty/error/offline states; Then kết quả giúp UX không bị cụt; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1108` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — xử lý loading/empty/error/offline states  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1109` **UX** — UX: Thiết kế wireframe/UI states — xử lý loading/empty/error/offline states  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1110` **FE** — FE: Implement UI và client integration — xử lý loading/empty/error/offline states  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1111` **QA** — QA: Test plan và automated tests — xử lý loading/empty/error/offline states  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E061 — Mobile/PWA and localization

**Objective:** PWA/mobile-ready, push notification, offline voucher, i18n.  
**Priority:** P2  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0232 — Là Traveller, tôi muốn cài PWA và mở voucher offline để dùng khi đi du lịch.

- **Priority:** P2
- **Tags:** PWA, FE, Voucher
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When cài PWA và mở voucher offline; Then kết quả giúp dùng khi đi du lịch; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1112` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — cài PWA và mở voucher offline  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1113` **UX** — UX: Thiết kế wireframe/UI states — cài PWA và mở voucher offline  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1114` **FE** — FE: Implement UI và client integration — cài PWA và mở voucher offline  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1115` **BE** — BE: Thiết kế domain/API/schema và implement service — cài PWA và mở voucher offline  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1116` **QA** — QA: Test plan và automated tests — cài PWA và mở voucher offline  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0233 — Là Traveller, tôi muốn nhận push notification booking updates để cập nhật kịp thời.

- **Priority:** P2
- **Tags:** PWA, Notification, FE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When nhận push notification booking updates; Then kết quả giúp cập nhật kịp thời; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1117` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — nhận push notification booking updates  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1118` **UX** — UX: Thiết kế wireframe/UI states — nhận push notification booking updates  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1119` **FE** — FE: Implement UI và client integration — nhận push notification booking updates  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1120` **BE** — BE: Thiết kế domain/API/schema và implement service — nhận push notification booking updates  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1121` **QA** — QA: Test plan và automated tests — nhận push notification booking updates  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0234 — Là Traveller, tôi muốn đổi ngôn ngữ Việt/Anh để phục vụ khách quốc tế.

- **Priority:** P2
- **Tags:** i18n, FE, AI
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When đổi ngôn ngữ Việt/Anh; Then kết quả giúp phục vụ khách quốc tế; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1122` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — đổi ngôn ngữ Việt/Anh  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1123` **UX** — UX: Thiết kế wireframe/UI states — đổi ngôn ngữ Việt/Anh  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1124` **FE** — FE: Implement UI và client integration — đổi ngôn ngữ Việt/Anh  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1125` **AI** — AI: Thiết kế prompt/tool schema/eval cases — đổi ngôn ngữ Việt/Anh  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1126` **Security** — Security: Threat model và security control — đổi ngôn ngữ Việt/Anh  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1127` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — đổi ngôn ngữ Việt/Anh  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1128` **QA** — QA: Test plan và automated tests — đổi ngôn ngữ Việt/Anh  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0235 — Là Product, tôi muốn quyết định native app vs PWA dựa trên metrics để không đầu tư sai.

- **Priority:** P2
- **Tags:** BA, Mobile, Analytics
- **Acceptance criteria:** Given Product có quyền hợp lệ; When quyết định native app vs PWA dựa trên metrics; Then kết quả giúp không đầu tư sai; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1129` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — quyết định native app vs PWA dựa trên metrics  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1130` **Data** — Data: Event taxonomy/data model/dashboard metric — quyết định native app vs PWA dựa trên metrics  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1131` **QA** — QA: Test plan và automated tests — quyết định native app vs PWA dựa trên metrics  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


# CAP18 — Content, Growth, Reviews, Loyalty & Marketplace Quality

**Owner:** Growth Lead

## CT-E062 — CMS, destination content and SEO growth

**Objective:** Quản lý nội dung destination, guide, campaign để tăng organic và trust.  
**Priority:** P1  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0236 — Là Content Admin, tôi muốn tạo destination guide/article liên kết tour để tăng discovery.

- **Priority:** P1
- **Tags:** CMS, SEO, FE, BE
- **Acceptance criteria:** Given Content Admin có quyền hợp lệ; When tạo destination guide/article liên kết tour; Then kết quả giúp tăng discovery; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1132` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tạo destination guide/article liên kết tour  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1133` **UX** — UX: Thiết kế wireframe/UI states — tạo destination guide/article liên kết tour  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1134` **FE** — FE: Implement UI và client integration — tạo destination guide/article liên kết tour  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1135` **BE** — BE: Thiết kế domain/API/schema và implement service — tạo destination guide/article liên kết tour  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1136` **QA** — QA: Test plan và automated tests — tạo destination guide/article liên kết tour  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0237 — Là Growth, tôi muốn quản lý campaign landing page để tối ưu chuyển đổi.

- **Priority:** P1
- **Tags:** CMS, Growth, FE
- **Acceptance criteria:** Given Growth có quyền hợp lệ; When quản lý campaign landing page; Then kết quả giúp tối ưu chuyển đổi; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1137` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — quản lý campaign landing page  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1138` **UX** — UX: Thiết kế wireframe/UI states — quản lý campaign landing page  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1139` **FE** — FE: Implement UI và client integration — quản lý campaign landing page  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1140` **BE** — BE: Thiết kế domain/API/schema và implement service — quản lý campaign landing page  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1141` **Data** — Data: Event taxonomy/data model/dashboard metric — quản lý campaign landing page  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1142` **QA** — QA: Test plan và automated tests — quản lý campaign landing page  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0238 — Là SEO, tôi muốn tạo sitemap, canonical, structured data cho content/tour để tăng organic traffic.

- **Priority:** P1
- **Tags:** SEO, FE, BE
- **Acceptance criteria:** Given SEO có quyền hợp lệ; When tạo sitemap, canonical, structured data cho content/tour; Then kết quả giúp tăng organic traffic; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1143` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — tạo sitemap, canonical, structured data cho content/tour  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1144` **UX** — UX: Thiết kế wireframe/UI states — tạo sitemap, canonical, structured data cho content/tour  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1145` **FE** — FE: Implement UI và client integration — tạo sitemap, canonical, structured data cho content/tour  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1146` **BE** — BE: Thiết kế domain/API/schema và implement service — tạo sitemap, canonical, structured data cho content/tour  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1147` **QA** — QA: Test plan và automated tests — tạo sitemap, canonical, structured data cho content/tour  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0239 — Là AI Assistant, tôi muốn dùng content approved trong RAG để trả lời có nguồn.

- **Priority:** P1
- **Tags:** CMS, RAG, AI
- **Acceptance criteria:** Given AI Assistant có quyền hợp lệ; When dùng content approved trong RAG; Then kết quả giúp trả lời có nguồn; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1148` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — dùng content approved trong RAG  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1149` **UX** — UX: Thiết kế wireframe/UI states — dùng content approved trong RAG  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1150` **FE** — FE: Implement UI và client integration — dùng content approved trong RAG  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1151` **BE** — BE: Thiết kế domain/API/schema và implement service — dùng content approved trong RAG  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1152` **AI** — AI: Thiết kế prompt/tool schema/eval cases — dùng content approved trong RAG  
    AC: Tool schema typed; no invented price/tour; eval cases pass; confidence/fallback defined. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1153` **Data** — Data: Chuẩn hóa ingestion, chunking, embedding và retrieval eval — dùng content approved trong RAG  
    AC: Nguồn có version; top-k retrieval được đo; stale/deprecated docs bị loại khỏi answer. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1154` **Security** — Security: Threat model và security control — dùng content approved trong RAG  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1155` **SRE** — SRE: Metrics/logs/traces/alerts/runbook — dùng content approved trong RAG  
    AC: OTel/correlation ID; dashboard; alert thresholds; runbook and rollback/degrade path. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1156` **QA** — QA: Test plan và automated tests — dùng content approved trong RAG  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E063 — Reviews, trust and marketplace quality

**Objective:** Thu thập review thật, xử lý moderation và phản hồi supplier.  
**Priority:** P2  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0240 — Là Traveller, tôi muốn đánh giá tour sau khi completed booking để chia sẻ trải nghiệm thật.

- **Priority:** P2
- **Tags:** Review, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When đánh giá tour sau khi completed booking; Then kết quả giúp chia sẻ trải nghiệm thật; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1157` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — đánh giá tour sau khi completed booking  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1158` **UX** — UX: Thiết kế wireframe/UI states — đánh giá tour sau khi completed booking  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1159` **FE** — FE: Implement UI và client integration — đánh giá tour sau khi completed booking  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1160` **BE** — BE: Thiết kế domain/API/schema và implement service — đánh giá tour sau khi completed booking  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1161` **QA** — QA: Test plan và automated tests — đánh giá tour sau khi completed booking  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0241 — Là System, tôi muốn chỉ cho verified booking review để giảm review giả.

- **Priority:** P2
- **Tags:** Review, Security, BE
- **Acceptance criteria:** Given System có quyền hợp lệ; When chỉ cho verified booking review; Then kết quả giúp giảm review giả; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1162` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — chỉ cho verified booking review  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1163` **UX** — UX: Thiết kế wireframe/UI states — chỉ cho verified booking review  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1164` **FE** — FE: Implement UI và client integration — chỉ cho verified booking review  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1165` **BE** — BE: Thiết kế domain/API/schema và implement service — chỉ cho verified booking review  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1166` **Security** — Security: Threat model và security control — chỉ cho verified booking review  
    AC: Authz, audit, masking, rate limit, abuse cases và secrets/logging review hoàn tất. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1167` **QA** — QA: Test plan và automated tests — chỉ cho verified booking review  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0242 — Là Admin, tôi muốn moderate review theo policy để giữ chất lượng nội dung.

- **Priority:** P2
- **Tags:** Review, Admin, FE, BE
- **Acceptance criteria:** Given Admin có quyền hợp lệ; When moderate review theo policy; Then kết quả giúp giữ chất lượng nội dung; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1168` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — moderate review theo policy  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1169` **UX** — UX: Thiết kế wireframe/UI states — moderate review theo policy  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1170` **FE** — FE: Implement UI và client integration — moderate review theo policy  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1171` **BE** — BE: Thiết kế domain/API/schema và implement service — moderate review theo policy  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1172` **QA** — QA: Test plan và automated tests — moderate review theo policy  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0243 — Là Supplier, tôi muốn phản hồi review được duyệt để cải thiện trust.

- **Priority:** P2
- **Tags:** Review, SupplierPortal, FE
- **Acceptance criteria:** Given Supplier có quyền hợp lệ; When phản hồi review được duyệt; Then kết quả giúp cải thiện trust; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1173` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — phản hồi review được duyệt  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1174` **UX** — UX: Thiết kế wireframe/UI states — phản hồi review được duyệt  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1175` **FE** — FE: Implement UI và client integration — phản hồi review được duyệt  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1176` **BE** — BE: Thiết kế domain/API/schema và implement service — phản hồi review được duyệt  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1177` **QA** — QA: Test plan và automated tests — phản hồi review được duyệt  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

## CT-E064 — Referral, loyalty and lifecycle growth

**Objective:** Tăng repeat booking bằng loyalty, referral, lifecycle campaigns.  
**Priority:** P2  
**Completion gate:** Product + Domain + Technical + Security/Privacy + Observability + QA evidence

### CT-US0244 — Là Traveller, tôi muốn nhận points/benefits sau booking completed để quay lại đặt tiếp.

- **Priority:** P2
- **Tags:** Loyalty, Finance, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When nhận points/benefits sau booking completed; Then kết quả giúp quay lại đặt tiếp; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1178` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — nhận points/benefits sau booking completed  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1179` **UX** — UX: Thiết kế wireframe/UI states — nhận points/benefits sau booking completed  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1180` **FE** — FE: Implement UI và client integration — nhận points/benefits sau booking completed  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1181` **BE** — BE: Thiết kế domain/API/schema và implement service — nhận points/benefits sau booking completed  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1182` **Data** — Data: Event taxonomy/data model/dashboard metric — nhận points/benefits sau booking completed  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1183` **QA** — QA: Test plan và automated tests — nhận points/benefits sau booking completed  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0245 — Là Traveller, tôi muốn gửi referral link cho bạn bè để tăng user mới.

- **Priority:** P2
- **Tags:** Growth, Referral, FE, BE
- **Acceptance criteria:** Given Traveller có quyền hợp lệ; When gửi referral link cho bạn bè; Then kết quả giúp tăng user mới; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1184` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — gửi referral link cho bạn bè  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1185` **UX** — UX: Thiết kế wireframe/UI states — gửi referral link cho bạn bè  
    AC: Có desktop/mobile states, empty/loading/error, permission states và copy chính. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1186` **FE** — FE: Implement UI và client integration — gửi referral link cho bạn bè  
    AC: UI dùng design system; validate input; xử lý loading/error; emit analytics event. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1187` **BE** — BE: Thiết kế domain/API/schema và implement service — gửi referral link cho bạn bè  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1188` **Data** — Data: Event taxonomy/data model/dashboard metric — gửi referral link cho bạn bè  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1189` **QA** — QA: Test plan và automated tests — gửi referral link cho bạn bè  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0246 — Là Growth, tôi muốn trigger lifecycle campaign theo hành vi để tăng conversion/retention.

- **Priority:** P2
- **Tags:** Growth, Notification, Analytics
- **Acceptance criteria:** Given Growth có quyền hợp lệ; When trigger lifecycle campaign theo hành vi; Then kết quả giúp tăng conversion/retention; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1190` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — trigger lifecycle campaign theo hành vi  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1191` **BE** — BE: Thiết kế domain/API/schema và implement service — trigger lifecycle campaign theo hành vi  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1192` **Data** — Data: Event taxonomy/data model/dashboard metric — trigger lifecycle campaign theo hành vi  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1193` **QA** — QA: Test plan và automated tests — trigger lifecycle campaign theo hành vi  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.

### CT-US0247 — Là Finance, tôi muốn theo dõi liability của loyalty points để không tạo nợ không kiểm soát.

- **Priority:** P2
- **Tags:** Loyalty, Finance, Data
- **Acceptance criteria:** Given Finance có quyền hợp lệ; When theo dõi liability của loyalty points; Then kết quả giúp không tạo nợ không kiểm soát; và hệ thống xử lý empty/error/permission states; và dữ liệu nhạy cảm được audit/mask theo policy.
- **Tickets:**
  - `CT-T1194` **BA** — BA: Làm rõ yêu cầu nghiệp vụ, edge cases và acceptance criteria — theo dõi liability của loyalty points  
    AC: Tạo flow, rule, field list, edge cases, error states; xác nhận với Product/Tech Lead. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1195` **BE** — BE: Thiết kế domain/API/schema và implement service — theo dõi liability của loyalty points  
    AC: API documented; domain invariant enforced; DB migration; idempotency/audit where relevant. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1196` **Data** — Data: Event taxonomy/data model/dashboard metric — theo dõi liability của loyalty points  
    AC: Event names, properties, source of truth, dashboard query và QA tracking được xác nhận. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.
  - `CT-T1197` **QA** — QA: Test plan và automated tests — theo dõi liability của loyalty points  
    AC: Unit/integration/contract/E2E; negative cases; regression suite updated; test evidence attached. Liên kết ticket với story; có evidence trong PR; không merge nếu thiếu test/evidence.


## 5. Source register

| Topic | URL | Use |
|---|---|---|
| MCP Streamable HTTP | https://modelcontextprotocol.io/specification/2025-11-25/basic/transports | Backlog requires MCP server/client over Streamable HTTP with POST/GET and optional SSE streaming. |
| MCP Streamable HTTP security | https://modelcontextprotocol.io/specification/2025-03-26/basic/transports | Origin validation, localhost binding for local servers, auth to prevent DNS rebinding. |
| Spring AI Streamable HTTP MCP server | https://docs.spring.io/spring-ai/reference/api/mcp/mcp-streamable-http-server-boot-starter-docs.html | Spring AI MCP server starter supports Streamable HTTP and replaces SSE transport. |
| Spring AI 2.0 GA | https://spring.io/blog/2026/06/12/spring-ai-2-0-0-GA-available-now | Spring AI 2.0.0 GA baseline; requires careful Spring Boot 4 compatibility planning. |
| Spring Data JPA | https://docs.spring.io/spring-data/jpa/reference/index.html | JPA repository support, specifications, projection and data access baseline. |
| Booking.com Demand API | https://developers.booking.com/demand | Hotel adapter is partner-dependent; Booking.com Demand API requires Managed Affiliate Partner. |
| Booking.com API auth | https://developers.booking.com/demand/docs/development-guide/authentication | Booking.com Demand API uses API key bearer token and X-Affiliate-Id. |
| Amadeus travel APIs | https://developers.amadeus.com/ | Flight/hotel/car adapter targets should be implemented through supplier adapter contracts. |
| PCI DSS v4.0.1 | https://blog.pcisecuritystandards.org/just-published-pci-dss-v4-0-1 | Payment backlog should treat card data scope carefully; use hosted payments/tokenization. |
| Vietnam Decree 13/2023 personal data deletion | https://thuvienphapluat.vn/van-ban/EN/Cong-nghe-thong-tin/Decree-No-13-2023-ND-CP-dated-April-17-2023-on-protection-of-personal-data/564343/tieng-anh.aspx | Data deletion workflow and DSR SLA use 72-hour legal-sensitive handling where applicable. |
| OWASP ASVS | https://owasp.org/www-project-application-security-verification-standard/ | Security backlog uses ASVS 5.0 as verification baseline. |
| OWASP Top 10 | https://owasp.org/www-project-top-ten/ | Application security backlog maps controls to OWASP Top 10 2025. |
| OpenTelemetry Signals | https://opentelemetry.io/docs/concepts/signals/ | Observability backlog covers traces, metrics, logs and baggage. |

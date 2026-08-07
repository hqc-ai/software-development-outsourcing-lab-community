# ARCHITECTURE DELTA PACK 07/08/2026

**Nguồn:** NousResearch Hermes Agent  
**Mục đích:** gói thay đổi chuẩn để đối chiếu và cập nhật kiến trúc từng dự án.

## 1. Pattern mới

### ADP-0708-01 — Deterministic Automation vs Agent Reasoning
Ưu tiên rule/script/SQL/cron cho tác vụ xác định; chỉ dùng AI khi cần hiểu ngữ cảnh, suy luận, tổng hợp, đánh giá hoặc tạo nội dung.

### ADP-0708-02 — Governed MCP / Tool Integration Layer
MCP/tool phải đi qua Tool/Integration Gateway với registry, owner, version, allowed agents, action scope, credential scope, approval policy, audit log và provenance.

### ADP-0708-03 — Risk-Based Action Approval
Phân loại hành động:
- L0: đọc dữ liệu công khai — tự động.
- L1: tạo draft/phân tích nội bộ — tự động.
- L2: cập nhật nội bộ có thể rollback — theo policy.
- L3: giao tiếp/commit với khách hàng hoặc bên ngoài — human approval.
- L4: production/xóa dữ liệu/thay đổi giá/quyền — explicit approval.
- L5: hành động nhạy cảm/bị cấm — agent không được thực hiện.

## 2. Pattern mở rộng cho software/development

### ADP-0708-X1 — AI-Assisted DevSecOps / Engineering Operations
PR review; CI/CD failure triage; dependency/security review; infrastructure diagnostics trong sandbox; checkpoint trước thay đổi; static validation → test → diff review → approval → commit/deploy.

## 3. Đã có — không thêm lại
Persistent memory; skill lifecycle; controlled learning; completion contract; verification evidence; sandbox/task-scoped credential; persistent workspace; long-running task; multi-agent gateway; Hermes Laboratory/optional worker; multi-channel gateway; HITL cơ bản.

## 4. Capability chưa cần nâng core architecture
Browser automation; voice note/STT; cron delivery; self-hosted/on-premise.

## 5. Mapping
- HQC AIMS Platform: ADP-0708-01, 02, 03.
- 5SOffice AI Agent/Webapp: ADP-0708-01, 02, 03.
- Office Agent Lab: ADP-0708-01, 02, 03 + capability thử nghiệm.
- Software Development & Outsourcing Lab: ADP-0708-01, 02, 03 + X1.
- Public/community repos: chỉ pattern/skeleton chọn lọc.
- Các AI Agent project khác: case-by-case.

## 6. Câu lệnh chuẩn
Áp dụng Architecture Delta Pack 07/08/2026 vào dự án này. Đọc architecture version hiện tại và đối chiếu từng Delta ID. Chỉ áp dụng phần phù hợp và chưa có; nội dung đã tương đương thì bỏ qua. Cập nhật Change Register, ADR, Backlog và sơ đồ kiến trúc nếu component/boundary thay đổi. Không đưa Hermes Agent thành production core; chỉ giữ nguyên tắc độc lập framework. Với dự án software/development thì xem thêm ADP-0708-X1.

## 7. Version impact
Delta Pack không tự động tạo version mới. Chỉ dự án thực sự nhận thay đổi kiến trúc mới tăng version theo ngày áp dụng.

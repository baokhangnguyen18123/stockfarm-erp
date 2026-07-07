# STOCKFARM ERP — ROADMAP

> Hệ thống quản lý cửa hàng thức ăn chăn nuôi và trang trại heo  
> Mục tiêu nghề nghiệp: **.NET Developer + Business Analyst**  
> Thời gian dự kiến: **10–12 tuần**  
> Cách làm việc: **Scrum 2 tuần/Sprint + bảng Kanban**

---

# 1. Mục tiêu dự án

Xây dựng một hệ thống web có thể:

- Quản lý sản phẩm, nhà cung cấp và khách hàng.
- Quản lý nhập, xuất và tồn kho.
- Theo dõi lô hàng và hạn sử dụng.
- Quản lý trang trại, chuồng và lứa heo.
- Ghi nhận thức ăn, thuốc và vật tư sử dụng cho từng lứa.
- Quản lý bán hàng và thanh toán.
- Ghi nhận thu chi nội bộ.
- Tổng hợp báo cáo tồn kho, doanh thu và chi phí chăn nuôi.
- Phân quyền người dùng và lưu lịch sử thao tác.
- Cung cấp một bản demo online để nhà tuyển dụng và stakeholder có thể truy cập trực tiếp.

---

# 2. Phạm vi MVP

## 2.1. Chức năng bắt buộc

1. Đăng nhập và phân quyền.
2. Danh mục sản phẩm, đơn vị tính, nhà cung cấp và khách hàng.
3. Nhập kho và theo dõi tồn kho.
4. Theo dõi lô hàng và hạn sử dụng.
5. Quản lý chuồng và lứa heo.
6. Ghi tiêu thụ thức ăn, thuốc và vật tư.
7. Quản lý đơn bán hàng.
8. Ghi nhận thanh toán, thu và chi.
9. Báo cáo tồn kho, doanh thu và chi phí theo lứa.
10. Audit Log cho các thao tác quan trọng.
11. Triển khai demo online bằng dữ liệu giả và tài khoản demo.

## 2.2. Chưa thực hiện trong MVP

- Kế toán tài chính đầy đủ.
- Hóa đơn điện tử.
- Tính thuế.
- Quản lý lương.
- Ứng dụng mobile native.
- IoT chuồng trại.
- Microservices.
- AI hoặc Machine Learning.
- Tích hợp ngân hàng.

---

# 3. Công nghệ và phương án triển khai

## 3.1. Công nghệ chính

- Backend: ASP.NET Core Web API.
- Frontend: Blazor Web App.
- UI framework: Bootstrap 5.3.x.
- Icon: Bootstrap Icons.
- Database local: SQL Server chạy trực tiếp hoặc bằng Docker.
- Database online: Azure SQL Database.
- ORM: Entity Framework Core.
- Authentication: ASP.NET Core Identity.
- API Documentation: OpenAPI/Swagger.
- Unit Test: xUnit.
- Integration Test: WebApplicationFactory.
- Source Control: GitHub.
- Project Board: GitHub Projects.
- CI/CD: GitHub Actions.
- Hosting demo: Azure App Service.
- Container: Docker dùng cho môi trường local và làm phương án triển khai dự phòng.
- Process Diagram: Draw.io hoặc Bizagi.
- Wireframe: Figma hoặc Penpot.

## 3.2. Kiến trúc demo online

```text
Người dùng
    ↓ HTTPS
Azure App Service
    ├── Blazor Web App
    ├── ASP.NET Core API
    └── Authentication
            ↓
     Azure SQL Database

GitHub Repository
    ↓ GitHub Actions
Build → Test → Publish → Deploy
```

Để giảm chi phí và độ phức tạp, frontend và backend được triển khai trong cùng một ứng dụng .NET. Đây vẫn là kiến trúc Modular Monolith, không cần tách thành nhiều dịch vụ hosting.

## 3.3. Yêu cầu đối với bản demo online

- Có URL công khai dùng HTTPS.
- Có trang giới thiệu ngắn về dự án.
- Có tài khoản demo cho từng role chính.
- Chỉ sử dụng dữ liệu giả hoặc dữ liệu đã ẩn danh.
- Không hiển thị secret, connection string hoặc thông tin gia đình.
- Database được seed sẵn dữ liệu mẫu.
- Có Health Check để kiểm tra trạng thái ứng dụng.
- Có logging lỗi nhưng không ghi password hoặc dữ liệu nhạy cảm.
- Có quy trình migration database khi deploy.
- Có thể khôi phục dữ liệu demo về trạng thái ban đầu.
- Có thông báo rõ đây là hệ thống demo, không phải phần mềm kế toán chính thức.

## 3.4. Quy tắc giao diện Bootstrap

- Thiết kế responsive theo hướng mobile-first.
- Dùng Bootstrap Grid cho layout.
- Dùng Navbar hoặc Sidebar cho menu chính.
- Dùng Card cho KPI và nội dung tổng quan.
- Dùng Table responsive cho danh sách nghiệp vụ.
- Dùng Form Control và Input Group cho nhập liệu.
- Dùng Modal cho xác nhận thao tác ngắn.
- Dùng Toast hoặc Alert cho thông báo.
- Dùng Badge thể hiện trạng thái chứng từ.
- Dùng Pagination cho danh sách lớn.
- Hạn chế viết CSS tùy chỉnh khi Bootstrap đã có component tương ứng.
- Giữ giao diện nhất quán giữa các module.
- Kiểm tra giao diện ít nhất trên desktop và màn hình điện thoại.

---

# 4. Tài liệu cần viết

Đây là bộ tài liệu tối thiểu. Không cần tạo quá nhiều tài liệu riêng nếu nội dung có thể gộp lại.

## 4.1. Tài liệu nghiệp vụ

| Tài liệu | Nội dung chính | Thời điểm tạo |
|---|---|---|
| Project Charter | Lý do làm dự án, mục tiêu, phạm vi, stakeholder, timeline | Giai đoạn 0 |
| Stakeholder Register | Danh sách người liên quan, vai trò và nhu cầu | Giai đoạn 0 |
| Interview Notes | Câu hỏi, câu trả lời, pain point và yêu cầu phát hiện được | Giai đoạn 1 |
| AS-IS BPMN | Quy trình hiện tại trước khi có phần mềm | Giai đoạn 1 |
| TO-BE BPMN | Quy trình sau khi áp dụng phần mềm | Giai đoạn 1–2 |
| BRD | Mục tiêu kinh doanh, scope và yêu cầu nghiệp vụ cấp cao | Giai đoạn 1 |
| Business Rule Catalogue | Danh sách quy tắc nghiệp vụ có mã định danh | Giai đoạn 1–2 |
| Product Backlog | Epic, User Story, độ ưu tiên và trạng thái | Cập nhật liên tục |
| Acceptance Criteria | Điều kiện để nghiệm thu từng User Story | Trước khi lập trình |
| RTM | Liên kết Requirement → User Story → API → Database → Test Case | Cập nhật mỗi Sprint |
| UAT Plan và UAT Report | Kịch bản người dùng kiểm thử và kết quả nghiệm thu | Giai đoạn 8 |

## 4.2. Tài liệu kỹ thuật

| Tài liệu | Nội dung chính | Thời điểm tạo |
|---|---|---|
| FSD | Mô tả chi tiết hệ thống phải hoạt động như thế nào | Giai đoạn 2 và cập nhật theo module |
| ERD | Các bảng dữ liệu và mối quan hệ | Giai đoạn 2 |
| Data Dictionary | Định nghĩa bảng, cột, kiểu dữ liệu và quy tắc dữ liệu | Giai đoạn 2 |
| Architecture Diagram | Kiến trúc tổng thể của hệ thống và các project | Giai đoạn 2 |
| API Specification | Endpoint, request, response, validation và quyền truy cập | Trước hoặc trong khi lập trình |
| Wireframe | Bố cục màn hình, trường nhập liệu và luồng thao tác | Trước khi làm frontend |
| UI Style Guide | Quy tắc Bootstrap, layout, component, trạng thái và responsive | Trước khi làm frontend |
| Deployment Architecture | Mô hình App Service, Azure SQL, CI/CD và môi trường | Trước khi triển khai |
| Sequence Diagram | Thứ tự xử lý của các luồng phức tạp | Chỉ dùng cho luồng quan trọng |
| Test Plan | Phạm vi, loại test và môi trường test | Trước giai đoạn kiểm thử |
| Test Cases | Các bước test, dữ liệu, kết quả mong đợi | Trong từng Sprint |
| Deployment Guide | Hướng dẫn Azure App Service, Azure SQL, migration, secret và rollback | Giai đoạn 8 |
| Release Notes | Chức năng, lỗi đã sửa và hạn chế của phiên bản | Mỗi lần release |

---

# 5. Phân biệt các tài liệu quan trọng

## 5.1. BRD — Business Requirements Document

BRD trả lời:

- Vì sao cần hệ thống?
- Hệ thống giải quyết vấn đề gì?
- Ai sử dụng?
- Phạm vi dự án là gì?
- Các yêu cầu nghiệp vụ cấp cao là gì?

Ví dụ:

```text
BR-INV-001:
Cửa hàng cần theo dõi tồn kho theo sản phẩm và lô hàng.

BR-FARM-001:
Trang trại cần tính được chi phí thức ăn và thuốc theo từng lứa heo.
```

## 5.2. FSD — Functional Specification Document

FSD trả lời:

- Mỗi chức năng hoạt động cụ thể như thế nào?
- Màn hình gồm những trường nào?
- Người dùng thực hiện các bước nào?
- Validation là gì?
- Hệ thống thay đổi dữ liệu như thế nào?
- Trường hợp lỗi xử lý ra sao?

Mỗi module nên có một phần FSD.

Ví dụ cấu trúc:

```text
1. Function Overview
2. Actors and Permissions
3. Preconditions
4. Main Flow
5. Alternative Flow
6. Exception Flow
7. Screen Fields
8. Validation Rules
9. Business Rules
10. API and Database Mapping
11. Acceptance Criteria
```

Ví dụ:

```text
FSD-INV-005: Xác nhận phiếu nhập

Precondition:
- Phiếu đang ở trạng thái Draft.
- Phiếu có ít nhất một dòng hàng.

Main Flow:
1. Người dùng nhấn Xác nhận.
2. Hệ thống kiểm tra dữ liệu.
3. Hệ thống chuyển trạng thái sang Confirmed.
4. Hệ thống tạo Inventory Transaction tăng kho.
5. Hệ thống ghi Audit Log.

Exception:
- Nếu phiếu không có dòng hàng, hệ thống từ chối xác nhận.
```

## 5.3. ERD — Entity Relationship Diagram

ERD thể hiện:

- Các bảng dữ liệu.
- Khóa chính.
- Khóa ngoại.
- Quan hệ một-một, một-nhiều hoặc nhiều-nhiều.

Các nhóm bảng chính:

### Hệ thống

- User.
- Role.
- AuditLog.

### Kho

- Product.
- ProductCategory.
- UnitOfMeasure.
- Supplier.
- Warehouse.
- PurchaseReceipt.
- PurchaseReceiptLine.
- InventoryLot.
- InventoryTransaction.
- StockAdjustment.

### Trang trại

- Farm.
- Barn.
- PigBatch.
- PigBatchEvent.
- FeedConsumption.
- MedicineUsage.
- MortalityRecord.
- WeightRecord.

### Bán hàng

- Customer.
- SaleOrder.
- SaleOrderLine.
- SalePayment.

### Thu chi

- CashTransaction.
- IncomeCategory.
- ExpenseCategory.
- PaymentMethod.

## 5.4. Data Dictionary

Data Dictionary giải thích chi tiết dữ liệu trong ERD.

Ví dụ:

| Table | Field | Type | Required | Rule |
|---|---|---|---:|---|
| Product | ProductCode | varchar(50) | Có | Duy nhất |
| Product | ProductName | nvarchar(200) | Có | Không để trống |
| InventoryLot | ExpiryDate | date | Tùy loại | Phải sau ngày nhập |
| PigBatch | InitialQuantity | int | Có | Lớn hơn 0 |
| SaleOrderLine | Quantity | decimal | Có | Lớn hơn 0 |

## 5.5. API Specification

Mỗi API cần ghi:

- Method và URL.
- Mục đích.
- Quyền truy cập.
- Request.
- Response.
- Validation.
- Error code.
- Bảng dữ liệu liên quan.

Ví dụ:

```text
POST /api/purchase-receipts/{id}/confirm

Permission:
Inventory.Confirm

Success:
200 OK

Errors:
400 — Dữ liệu không hợp lệ
403 — Không có quyền
404 — Không tìm thấy phiếu
409 — Phiếu đã được xác nhận
```

## 5.6. UI Style Guide — Quy chuẩn giao diện Bootstrap

Tài liệu này giúp các màn hình không bị thiết kế rời rạc.

Nội dung tối thiểu:

- Cấu trúc trang: header, sidebar, content và footer.
- Breakpoint hỗ trợ.
- Quy tắc dùng màu trạng thái.
- Cách dùng Button, Table, Form, Modal, Alert, Toast và Badge.
- Trạng thái loading, empty, error và disabled.
- Quy tắc hiển thị validation.
- Quy tắc responsive cho bảng dữ liệu.
- Mẫu trang danh sách, trang chi tiết và form nhập liệu.

Ví dụ:

```text
Primary button:
Dùng cho hành động chính như Lưu hoặc Xác nhận.

Danger button:
Chỉ dùng cho Hủy chứng từ hoặc thao tác có tác động lớn.

Status badge:
Draft      → secondary
Confirmed  → success
Cancelled  → danger
```

## 5.7. RTM — Requirements Traceability Matrix

RTM giúp kiểm tra yêu cầu đã được thiết kế, lập trình và kiểm thử hay chưa.

| Requirement | User Story | FSD | API | Database | Test Case | Status |
|---|---|---|---|---|---|---|
| FR-INV-001 | US-INV-01 | FSD-INV-01 | POST /purchase-receipts | PurchaseReceipt | TC-INV-01 | Done |
| FR-FARM-001 | US-FARM-05 | FSD-FARM-05 | POST /feed-consumptions | FeedConsumption | TC-FARM-05 | Planned |

---

# 6. Cách quản lý công việc

## 6.1. Scrum

- Một Sprint dài 2 tuần.
- Mỗi Sprint có một mục tiêu rõ ràng.
- Đầu Sprint chọn User Story cần thực hiện.
- Cuối Sprint phải có chức năng có thể demo.
- Sau Sprint ghi lại điều làm tốt và điều cần cải thiện.

Các buổi cần thực hiện:

1. Sprint Planning: chọn công việc cho Sprint.
2. Daily Update: ghi việc đã làm, việc tiếp theo và blocker.
3. Sprint Review: demo cho stakeholder.
4. Retrospective: rút kinh nghiệm.
5. Backlog Refinement: làm rõ công việc cho Sprint sau.

## 6.2. Kanban Board

Sử dụng các cột:

```text
Backlog
→ Ready
→ Analysis
→ In Progress
→ Testing
→ UAT
→ Done
```

Nếu bị chặn, gắn nhãn `Blocked`.

Quy tắc:

- Chỉ làm một User Story lớn tại một thời điểm.
- Không đưa công việc sang Done nếu chưa test.
- Mỗi User Story phải có Acceptance Criteria.
- Mỗi bug phải ghi mức độ và cách tái hiện.
- Cập nhật bảng mỗi ngày.

---

# 7. Definition of Ready

Một User Story được phép đưa vào Sprint khi:

- Có mục tiêu rõ ràng.
- Có người dùng cụ thể.
- Có mô tả chức năng.
- Có Acceptance Criteria.
- Có business rule liên quan.
- Có wireframe nếu liên quan giao diện.
- Có thể hoàn thành trong một Sprint.
- Không còn câu hỏi nghiệp vụ quan trọng.

---

# 8. Definition of Done

Một User Story chỉ hoàn thành khi:

- Code đã hoàn tất.
- Validation đã được xử lý.
- Phân quyền đã được kiểm tra.
- Database migration đã được tạo nếu cần.
- Unit Test hoặc Integration Test đã chạy.
- Acceptance Criteria đạt.
- API Specification được cập nhật.
- RTM được cập nhật.
- Không còn bug Critical hoặc High.
- Stakeholder đã xem demo nếu đây là chức năng nghiệp vụ.

---

# 9. Roadmap thực hiện

## Giai đoạn 0 — Khởi tạo dự án

**Thời gian:** 3–4 ngày.

### Công việc

- Viết Business Problem.
- Viết Product Goal.
- Chốt Azure App Service + Azure SQL là môi trường demo.
- Xác định stakeholder.
- Xác định phạm vi MVP.
- Xác định nội dung không làm.
- Xác định rủi ro chính.
- Tạo GitHub repository.
- Tạo GitHub Project.
- Tạo các Epic.
- Lập timeline tổng quát.

### Tài liệu cần tạo

- `Project-Charter.md`
- `Stakeholder-Register.xlsx`
- `Scope.md`
- `Risk-Register.xlsx`
- `Product-Backlog.xlsx` hoặc GitHub Issues

### Hoàn thành khi

- Mục tiêu sản phẩm rõ ràng.
- Phạm vi MVP được thống nhất.
- Có backlog cấp cao.
- Repository và board đã sẵn sàng.

---

## Giai đoạn 1 — Khảo sát nghiệp vụ

**Thời gian:** 1–2 tuần.

### Công việc

- Phỏng vấn người quản lý cửa hàng.
- Phỏng vấn người quản lý kho.
- Phỏng vấn người quản lý trang trại.
- Phỏng vấn người ghi thu chi.
- Quan sát quy trình thực tế.
- Thu thập sổ sách, hóa đơn và file Excel.
- Vẽ quy trình hiện tại.
- Xác định pain point.
- Xác định business rule.
- Xác định dữ liệu đầu vào và đầu ra.

### Quy trình cần khảo sát

- Nhập hàng.
- Bán hàng.
- Kiểm kê.
- Cấp thức ăn.
- Sử dụng thuốc.
- Chuyển chuồng.
- Ghi nhận hao hụt.
- Thu và chi.
- Tổng hợp báo cáo.

### Tài liệu cần tạo

- `Interview-Plan.md`
- `Interview-Notes.md`
- `Document-Request-List.xlsx`
- `AS-IS-Process.drawio`
- `Pain-Point-Matrix.xlsx`
- `Business-Glossary.md`
- `Business-Rule-Catalogue.xlsx`
- `BRD.md`

### Hoàn thành khi

- Hiểu rõ quy trình hiện tại.
- Các pain point có bằng chứng.
- Stakeholder xác nhận AS-IS.
- Có danh sách yêu cầu nghiệp vụ cấp cao.

---

## Giai đoạn 2 — Phân tích và thiết kế giải pháp

**Thời gian:** 1 tuần.

### Công việc

- Vẽ quy trình TO-BE.
- Viết Functional Requirement.
- Viết Non-functional Requirement.
- Tạo User Story.
- Viết Acceptance Criteria.
- Thiết kế wireframe.
- Xác định Bootstrap component cho từng màn hình.
- Viết UI Style Guide.
- Kiểm tra responsive cho desktop và điện thoại.
- Thiết kế database.
- Xác định role và permission.
- Xác định API chính.
- Liên kết yêu cầu với thiết kế và test.

### Tài liệu cần tạo

- `TO-BE-Process.drawio`
- `FSD.md`
- `ERD.drawio`
- `Data-Dictionary.xlsx`
- `Architecture-Diagram.drawio`
- `Wireframes.fig`
- `UI-Style-Guide.md`
- `Deployment-Architecture.drawio`
- `API-Specification.md`
- `Role-Permission-Matrix.xlsx`
- `RTM.xlsx`

### Hoàn thành khi

- Mỗi chức năng Must-have có User Story.
- Mỗi User Story có Acceptance Criteria.
- ERD hỗ trợ các nghiệp vụ chính.
- Wireframe được stakeholder xem.
- Bootstrap component và quy tắc responsive đã được xác định.
- Kiến trúc demo online đã được xác định.
- Các API chính đã được xác định.

---

## Giai đoạn 3 — Xây dựng nền tảng kỹ thuật

**Thời gian:** 1 tuần.

### Công việc

- Tạo solution .NET.
- Tạo các project Domain, Application, Infrastructure, API và Web.
- Cấu hình SQL Server.
- Cấu hình Entity Framework Core.
- Tạo migration đầu tiên.
- Cấu hình đăng nhập.
- Cấu hình Bootstrap 5.3.x và Bootstrap Icons.
- Tạo layout chung gồm navbar/sidebar/content.
- Tạo component dùng chung cho loading, validation, alert và pagination.
- Cấu hình role và permission.
- Cấu hình validation.
- Cấu hình logging.
- Cấu hình global exception handling.
- Cấu hình OpenAPI.
- Cấu hình Docker cho môi trường local.
- Cấu hình GitHub Actions để build, test và chuẩn bị deploy.
- Tạo cấu hình môi trường Development, Demo và Production.
- Chuẩn bị connection string bằng environment variable hoặc secret.
- Tạo Unit Test và Integration Test project.

### Tài liệu cần cập nhật

- `Architecture-Diagram.drawio`
- `API-Specification.md`
- `Deployment-Architecture.drawio`
- `UI-Style-Guide.md`
- `Deployment-Guide.md`
- `README.md`

### Hoàn thành khi

- Ứng dụng chạy được.
- Đăng nhập được.
- Database migration chạy được.
- Swagger hiển thị được.
- CI build và test thành công.
- Layout Bootstrap hiển thị đúng trên desktop và điện thoại.
- Ứng dụng sẵn sàng kết nối với môi trường demo online.

---

## Giai đoạn 4 — Module kho

**Thời gian:** 2 tuần.

### Chức năng

- Quản lý sản phẩm.
- Quản lý đơn vị tính.
- Quản lý nhà cung cấp.
- Quản lý kho.
- Tạo phiếu nhập.
- Xác nhận phiếu nhập.
- Theo dõi lô và hạn sử dụng.
- Điều chỉnh kho.
- Xem tồn kho.
- Xem lịch sử giao dịch.
- Cảnh báo tồn thấp.
- Cảnh báo sắp hết hạn.

### Quy tắc quan trọng

- Phiếu Draft không tăng kho.
- Phiếu Confirmed mới tăng kho.
- Không sửa hoặc xóa trực tiếp chứng từ đã xác nhận.
- Hủy chứng từ phải tạo giao dịch đảo.
- Điều chỉnh kho phải có lý do.
- Không cho tồn kho âm.

### Tài liệu cần viết hoặc cập nhật

- `FSD-Inventory.md`
- `ERD.drawio`
- `Data-Dictionary.xlsx`
- `API-Inventory.md`
- `Inventory-Wireframes.fig`
- `UI-Style-Guide.md`
- `Inventory-Test-Cases.xlsx`
- `RTM.xlsx`

### Hoàn thành khi

- Nhập hàng làm tăng tồn.
- Hủy nhập hàng hoàn lại tồn.
- Tồn kho có thể truy về chứng từ nguồn.
- Các business rule chính có test.

---

## Giai đoạn 5 — Module trang trại

**Thời gian:** 2 tuần.

### Chức năng

- Quản lý trang trại.
- Quản lý chuồng.
- Tạo lứa heo.
- Ghi số lượng đầu kỳ.
- Ghi chuyển chuồng.
- Ghi heo chết hoặc hao hụt.
- Ghi cân nặng.
- Ghi tiêu thụ thức ăn.
- Ghi sử dụng thuốc.
- Tính chi phí theo lứa.

### Quy tắc quan trọng

- Không ghi giao dịch cho lứa đã đóng.
- Số lượng heo chết không vượt số lượng hiện có.
- Tiêu thụ thức ăn và thuốc phải giảm tồn kho.
- Không cho tiêu thụ vượt tồn kho.
- Mọi thay đổi đàn phải có lịch sử.

### Tài liệu cần viết hoặc cập nhật

- `FSD-Farm.md`
- `ERD.drawio`
- `Data-Dictionary.xlsx`
- `API-Farm.md`
- `Farm-Wireframes.fig`
- `UI-Style-Guide.md`
- `Farm-Test-Cases.xlsx`
- `RTM.xlsx`

### Hoàn thành khi

- Tạo và theo dõi được lứa heo.
- Ghi tiêu thụ làm giảm tồn kho.
- Chi phí thức ăn và thuốc được cộng vào lứa.
- Có lịch sử biến động đàn.

---

## Giai đoạn 6 — Module bán hàng

**Thời gian:** 2 tuần.

### Chức năng

- Quản lý khách hàng.
- Tạo đơn bán.
- Thêm sản phẩm vào đơn.
- Xác nhận đơn.
- Ghi thanh toán.
- Theo dõi số tiền còn nợ.
- Hủy đơn.
- Xem doanh thu.

### Quy tắc quan trọng

- Đơn Draft không giảm tồn kho.
- Đơn Confirmed mới giảm tồn.
- Không cho bán vượt tồn.
- Hủy đơn phải hoàn tồn.
- Không xóa đơn đã xác nhận.
- Thanh toán không vượt số tiền còn lại.

### Tài liệu cần viết hoặc cập nhật

- `FSD-Sales.md`
- `ERD.drawio`
- `Data-Dictionary.xlsx`
- `API-Sales.md`
- `Sales-Wireframes.fig`
- `UI-Style-Guide.md`
- `Sales-Test-Cases.xlsx`
- `RTM.xlsx`

### Hoàn thành khi

- Xác nhận đơn làm giảm tồn.
- Hủy đơn hoàn lại tồn.
- Theo dõi được thanh toán.
- Có báo cáo doanh thu cơ bản.

---

## Giai đoạn 7 — Thu chi và báo cáo

**Thời gian:** 1–2 tuần.

### Chức năng

- Tạo phiếu thu.
- Tạo phiếu chi.
- Quản lý nhóm thu chi.
- Liên kết thu với đơn bán.
- Liên kết chi với nhập hàng hoặc chi phí trại.
- Xem dòng tiền.
- Xem giá trị tồn kho.
- Xem chi phí theo lứa.
- Xem dashboard.

### Quy tắc quan trọng

- Doanh thu không đồng nghĩa tiền đã thu.
- Chi phí không đồng nghĩa tiền đã chi.
- Phiếu đã xác nhận không được xóa.
- Không ghi nhận trùng một khoản thu hoặc chi.
- Báo cáo phải truy về chứng từ nguồn.

### Tài liệu cần viết hoặc cập nhật

- `FSD-Finance-Reporting.md`
- `Report-Specification.md`
- `API-Finance.md`
- `Dashboard-Wireframes.fig`
- `UI-Style-Guide.md`
- `Finance-Test-Cases.xlsx`
- `RTM.xlsx`

### Hoàn thành khi

- Thu chi liên kết được với chứng từ nguồn.
- Dashboard lấy dữ liệu thật từ database.
- Số liệu báo cáo khớp với giao dịch nguồn.

---

## Giai đoạn 8 — Kiểm thử, UAT và triển khai

**Thời gian:** 1–2 tuần.

### Công việc kiểm thử

- Chạy Unit Test.
- Chạy Integration Test.
- Chạy Regression Test.
- Kiểm tra phân quyền.
- Kiểm tra transaction.
- Kiểm tra concurrency tồn kho.
- Kiểm tra dữ liệu báo cáo.
- Kiểm tra backup và restore.

### Công việc triển khai demo online

- Tạo Azure App Service cho ứng dụng.
- Tạo Azure SQL Database cho dữ liệu demo.
- Cấu hình firewall và quyền truy cập database.
- Lưu connection string và secret trong cấu hình an toàn.
- Cấu hình GitHub Actions deploy lên Azure App Service.
- Chạy Entity Framework Core migration trên môi trường demo.
- Seed dữ liệu giả.
- Tạo tài khoản demo theo role.
- Bật HTTPS.
- Cấu hình Health Check và logging.
- Kiểm tra URL từ trình duyệt không đăng nhập.
- Kiểm tra đăng nhập và các luồng chính trên môi trường online.
- Viết hướng dẫn rollback.
- Thiết lập ngân sách hoặc cảnh báo chi phí cloud.
- Không đưa dữ liệu thật lên môi trường demo.

### Công việc UAT

- Chuẩn bị dữ liệu test.
- Viết kịch bản người dùng thực tế.
- Cho stakeholder thực hiện.
- Ghi lỗi và phản hồi.
- Sửa lỗi Critical và High.
- Xin xác nhận UAT.

### Kịch bản UAT tối thiểu

1. Nhập 20 bao thức ăn.
2. Bán 3 bao.
3. Cấp 5 bao cho một lứa heo.
4. Điều chỉnh giảm 1 bao.
5. Kiểm tra tồn còn 11 bao.
6. Ghi sử dụng thuốc.
7. Ghi heo chết.
8. Ghi phiếu chi.
9. Kiểm tra chi phí lứa.
10. Kiểm tra dashboard.

### Tài liệu cần tạo

- `Test-Plan.md`
- `Test-Cases.xlsx`
- `Test-Summary-Report.md`
- `UAT-Plan.md`
- `UAT-Report.md`
- `Defect-Log.xlsx`
- `Deployment-Architecture.drawio`
- `Deployment-Guide.md`
- `GitHub-Actions-Deployment.md`
- `Demo-Accounts.md`
- `Release-Notes.md`

### Hoàn thành khi

- Không còn lỗi Critical hoặc High.
- Stakeholder hoàn thành UAT.
- Có URL demo online dùng HTTPS.
- Có tài khoản demo theo role.
- Frontend Bootstrap responsive trên desktop và điện thoại.
- GitHub Actions deploy thành công.
- Azure App Service kết nối được Azure SQL Database.
- Không có secret hoặc dữ liệu thật trong repository.
- Có backup, restore và hướng dẫn rollback.
- Release MVP được tạo.

---

## Giai đoạn 9 — Hoàn thiện portfolio

**Thời gian:** 2–3 ngày, thực hiện song song với các Sprint.

### Công việc

- Hoàn thiện README.
- Chụp ảnh màn hình trên desktop và điện thoại.
- Quay video demo 5–7 phút.
- Thêm URL demo online vào README và CV.
- Làm sạch BPMN và ERD.
- Công khai BRD và FSD bản rút gọn.
- Công khai RTM và UAT Report.
- Thay dữ liệu thật bằng dữ liệu giả.
- Viết mô tả dự án trong CV.
- Chuẩn bị câu chuyện phỏng vấn.

### Tài liệu công khai nên có

- `README.md`
- `ROADMAP.md`
- `Project-Charter.md`
- `BRD.md`
- `FSD-Summary.md`
- `AS-IS-Process.pdf`
- `TO-BE-Process.pdf`
- `ERD.pdf`
- `Architecture-Diagram.pdf`
- `Deployment-Architecture.pdf`
- `UI-Style-Guide.md`
- `API-Specification.md`
- `RTM-Sample.xlsx`
- `Test-Summary-Report.md`
- `UAT-Report.md`

---

# 10. Cấu trúc thư mục tài liệu

```text
docs/
├── 01-init/
│   ├── Project-Charter.md
│   ├── Stakeholder-Register.xlsx
│   ├── Scope.md
│   └── Risk-Register.xlsx
│
├── 02-business-analysis/
│   ├── Interview-Plan.md
│   ├── Interview-Notes.md
│   ├── BRD.md
│   ├── Business-Rule-Catalogue.xlsx
│   ├── AS-IS-Process.drawio
│   └── TO-BE-Process.drawio
│
├── 03-functional-design/
│   ├── FSD-Inventory.md
│   ├── FSD-Farm.md
│   ├── FSD-Sales.md
│   ├── FSD-Finance-Reporting.md
│   └── Wireframes/
│
├── 04-technical-design/
│   ├── Architecture-Diagram.drawio
│   ├── ERD.drawio
│   ├── Data-Dictionary.xlsx
│   ├── API-Specification.md
│   ├── UI-Style-Guide.md
│   ├── Deployment-Architecture.drawio
│   └── Role-Permission-Matrix.xlsx
│
├── 05-testing/
│   ├── Test-Plan.md
│   ├── Test-Cases.xlsx
│   ├── Defect-Log.xlsx
│   └── Test-Summary-Report.md
│
├── 06-uat/
│   ├── UAT-Plan.md
│   └── UAT-Report.md
│
└── 07-release/
    ├── Deployment-Guide.md
    ├── GitHub-Actions-Deployment.md
    ├── Demo-Accounts.md
    └── Release-Notes.md
```

---

# 11. Product Backlog cấp cao

| Epic | Nội dung | Ưu tiên |
|---|---|---|
| Foundation | Đăng nhập, phân quyền, audit và logging | Must |
| Inventory | Danh mục, nhập hàng, tồn kho và điều chỉnh | Must |
| Farm | Chuồng, lứa heo, thức ăn, thuốc và chi phí | Must |
| Sales | Khách hàng, đơn bán, thanh toán và doanh thu | Must |
| Finance | Thu, chi và liên kết chứng từ | Must |
| Reporting | Dashboard và báo cáo quản trị | Should |
| Deployment | Azure App Service, Azure SQL, GitHub Actions, backup và demo online | Must |

---

# 12. User Story mẫu

```text
ID: US-FARM-005

Là người quản lý trại,
tôi muốn ghi nhận lượng thức ăn sử dụng cho một lứa heo,
để hệ thống tự động giảm tồn kho và tính chi phí của lứa.
```

Acceptance Criteria:

```gherkin
Scenario: Ghi nhận thức ăn thành công
  Given lứa heo đang hoạt động
  And kho còn 500 kg thức ăn
  When người dùng ghi nhận sử dụng 100 kg
  Then hệ thống lưu giao dịch tiêu thụ
  And tồn kho còn 400 kg
  And chi phí lứa heo được cập nhật
```

```gherkin
Scenario: Sử dụng vượt tồn kho
  Given kho chỉ còn 50 kg thức ăn
  When người dùng ghi nhận sử dụng 100 kg
  Then hệ thống từ chối giao dịch
  And không thay đổi tồn kho
```

---

# 13. Business Rule mẫu

```text
BR-INV-001:
Phiếu nhập Draft không làm tăng tồn kho.

BR-INV-002:
Chỉ phiếu nhập Confirmed mới tạo Inventory Transaction.

BR-INV-003:
Chứng từ đã Confirmed không được xóa vật lý.

BR-FARM-001:
Không được ghi tiêu thụ cho lứa heo đã đóng.

BR-FARM-002:
Số lượng heo chết không được vượt số lượng hiện có.

BR-SALE-001:
Đơn bán chỉ được xác nhận khi đủ tồn kho.

BR-SALE-002:
Hủy đơn bán phải tạo giao dịch hoàn kho.
```

---

# 14. Thứ tự thực hiện ngay

## Ngày 1

- Tạo repository.
- Tạo GitHub Project.
- Viết Project Charter.
- Viết Business Problem.
- Viết Product Goal.
- Chốt Azure App Service + Azure SQL là môi trường demo.

## Ngày 2

- Lập Stakeholder Register.
- Chuẩn bị Interview Plan.
- Thu thập sổ sách và file Excel.

## Ngày 3–4

- Phỏng vấn người quản lý cửa hàng.
- Phỏng vấn người quản lý trang trại.
- Ghi Interview Notes.
- Vẽ AS-IS.

## Ngày 5–7

- Viết Pain Point Matrix.
- Viết BRD bản đầu.
- Viết Business Rule Catalogue.
- Tạo Product Backlog.
- Chuẩn bị TO-BE, FSD và ERD.
- Tạo UI Style Guide cho Bootstrap.
- Vẽ Deployment Architecture cho demo online.

---

# 15. Đánh giá khả năng hosting demo online

Phương án này khả thi đối với dự án portfolio vì:

- Ứng dụng Blazor và ASP.NET Core có thể được đóng gói thành một web app.
- Azure App Service hỗ trợ triển khai ứng dụng .NET mà không cần tự quản lý máy chủ.
- Azure SQL Database giữ nguyên hướng thiết kế SQL Server và Entity Framework Core.
- GitHub Actions có thể tự động build, test và deploy khi merge vào branch release.
- Dữ liệu demo có quy mô nhỏ nên không cần kiến trúc phức tạp.
- Bootstrap không yêu cầu một dịch vụ frontend riêng.

Các điểm cần kiểm soát:

- Chi phí App Service và database.
- Connection string và secret.
- Migration database.
- Cold start hoặc giới hạn của gói hosting.
- Dữ liệu giả và quyền của tài khoản demo.
- Backup hoặc khả năng seed lại dữ liệu.
- Không cho tài khoản demo thực hiện thao tác quản trị nguy hiểm.

Môi trường đề xuất:

| Môi trường | Ứng dụng | Database | Mục đích |
|---|---|---|---|
| Local | ASP.NET Core + Blazor + Bootstrap | SQL Server/Docker | Phát triển |
| Demo | Azure App Service | Azure SQL Database | Portfolio và UAT |
| Production thật | Chưa thuộc MVP | Chưa thuộc MVP | Xem xét sau |

---

# 16. Tiêu chí hoàn thành dự án

Dự án được xem là hoàn thành khi:

- Có MVP chạy được.
- Có đủ bốn module chính.
- Mọi biến động kho có lịch sử.
- Chi phí thức ăn và thuốc được liên kết với lứa heo.
- Bán hàng cập nhật tồn kho chính xác.
- Thu chi liên kết được với chứng từ nguồn.
- Có Unit Test và Integration Test cho luồng quan trọng.
- UAT được stakeholder xác nhận.
- Có bản demo online dùng HTTPS trên Azure App Service.
- Demo sử dụng Azure SQL Database và dữ liệu giả.
- Giao diện dùng Bootstrap và responsive trên desktop, điện thoại.
- Có CI/CD từ GitHub Actions đến môi trường demo.
- Có BRD, FSD, ERD, API Spec, UI Style Guide, Deployment Guide, RTM và UAT Report.
- Repository không chứa dữ liệu thật hoặc thông tin nhạy cảm.
- Có thể trình bày dự án trong 5–7 phút.

---

# 17. Nguyên tắc thực hiện

- Chỉ làm chức năng thuộc MVP.
- Hoàn thành từng module trước khi mở rộng.
- Không bắt đầu quá nhiều User Story cùng lúc.
- Business rule quan trọng phải có test.
- Không xóa lịch sử của chứng từ đã xác nhận.
- Tài liệu phải được cập nhật cùng với code.
- Mỗi Sprint phải có chức năng có thể demo.
- Từ khi nền tảng ổn định, deploy định kỳ lên môi trường demo online.
- Giao diện mới phải dùng component Bootstrap nhất quán và responsive.
- Theo dõi chi phí cloud, không để tài nguyên demo chạy vượt ngân sách.
- Bắt đầu ứng tuyển khi module kho đã chạy, không chờ toàn bộ dự án hoàn thành.

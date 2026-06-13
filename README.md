BÁO CÁO TIẾN ĐỘ KHÓA HỌC GIT FOUNDATIONS

1 Thông tin học viên & Dự án khóa học: Git Foundations (Microsoft Learn - GitHub Foundations)
 
Học viên: Trương Lê Đình Bảo
 
Mã sinh viên: 25E1020006
 
Tên thư mục cục bộ (Repository): truongledinhbao1507
 
2  Quá trình học tập 
 
Quá trình học tập được chia làm 2 giai đoạn chính dựa theo tài liệu Microsoft Learn:
 
Giai đoạn 1 : Tiếp xúc các khái niệm cơ bảncủa Git bao gồm quản lý mã nguồn cục bộ, tìm hiểu cách hoạt động của mô hình GitHub Flow (Branching, Committing, Pull Request),quản lý công việc bằng GitHub Projects và định dạng văn bản Markdown.
 
Giai đoạn 2 : Học cách quản lý, phân quyền và bảo mật dự án, thực hành giải quyết xung đột mã nguồn trực tiếp (Conflict Resolution), quản lý lịch sử commit và thực hiện hoàn tác an toàn (Revert/Rollback).
3  Nhật ký thực hành
 
3.1. Hệ thống Nhánh (Branches)Dựa trên lịch sử log, hệ thống ghi nhận em đã khởi tạo và điều phối công việc thành công trên các nhánh chính sau:

main: Nhánh phân phối chính thức, lưu trữ sản phẩm cuối cùng sau khi gộp.
 
conflict-test: Nhánh phụ dùng để tạo tình huống và xử lý xung đột mã nguồn trực tiếp trên file README.md.
 
feature-profile: Nhánh tính năng dùng để thực hành quy trình Pull Request phát triển chức năng profile.
 
feature-login: Nhánh tính năng thực hành xây dựng chức năng đăng nhập và đẩy lên remote.
 

3.2 . Số lượng commit :18 Toàn bộ tiến trình commit từ điểm khởi tạo ban đầu (Initial commit) cho đến các bước xử lý nâng cao đều được lưu vào
 
3.3. Quản lý Pull Requests & Gộp mã nguồn (Merge)

Pull Request #1: Hợp nhất thành công nhánh feature-login vào hệ thống (Commit hash: 89c04bb).

Pull Request #2: Hợp nhất thành công nhánh feature-profile vào nhánh chính (Commit hash: cccadad).
 
3.4. Xử lý Xung đột (Conflict )

Tình huống: Khi thực hiện gộp nhánh conflict-test vào nhánh main, hệ thống phát hiện xung đột do cả hai nhánh cùng chỉnh sửa nội dung 
trong tệp README.md (Commit 084034e trên nhánh phụ và 224c6cd trên nhánh main).

Cách khắc phục : Em đã tiến hành mở tệp README.md trên trình soạn thảo, giải quyết xung đột thủ công bằng cách xóa bỏ các thẻ đánh dấu 
(<<<<<<<, =======, >>>>>>>), đồng thời đồng nhất nội dung và thực hiện commit hoàn thành việc fix conflict .
 
3.5. Thực hành Hoàn tác (Revert / Rollback)

Nhằm làm quen với việc xử lý lỗi an toàn, em đã thực hành tạo một commit thử nghiệm (5ab38c6 - "Add a line that we will revert later"),
sau đó sử dụng lệnh git revert ngay trên Terminal để tạo ra một commit mới (5bd94c8 - "Tao commit moi de thuc hanh revert").Hành động 
này giúp hủy bỏ nội dung thử nghiệm một cách an toàn mà vẫn giữ toàn vẹn lịch sử hệ thống.
 
4 Tôi sẽ dùng Git như thế nào khi Vibe Code với AI?

Khi bước vào giai đoạn Vibe Code với AI (sử dụng GitHub Copilot, Cursor, ...), AI có tốc độ sinh mã nguồn rất nhanh. Để kiểm soát dự án không bị mất kiểm soát, em áp dụng quy trình Git theo 3 tiêu chí :

Chuẩn bị (Setup) & cung cấp ngữ cảnh: Khởi tạo kho lưu trữ gọn gàng. Kết nối Git với không gian làm việc giúp AI hiểu toàn bộ cấu trúc 
thư mục để đưa ra gợi ý chính xác hơn.

Quy trình phối hợp  

Bước 1 (Prompt): Yêu cầu AI viết hoặc sửa code theo từng mảng nhỏ, không đưa ra yêu cầu quá phức tạp gây xáo trộn

Bước 2 (Review): Sử dụng lệnh git diff hoặc công cụ Source Control để so sánh, rà soát kỹ lưỡng phần code do AI sinh ra trước khi chấp nhận.

Bước 3 (Commit ): Tiến hành gom nhóm và commit ngay sau khi một prompt của AI chạy ổn định với thông điệp tường minh, ví dụ: git 
commit -m "feat: tích hợp AI sinh mã tự động cho module Auth".

Quy tắc an toàn (Branching & Testing): Tuyệt đối không cho AI viết code trực tiếp trên nhánh main. Mọi thử nghiệm với AI đều phải thực 
hiện trên các nhánh tính năng (feature/*). Sau khi chạy thử nghiệm (Testing) dưới máy cục bộ thấy ổn định hoàn toàn mới tiến hành tạo 
Pull Request để gộp vào nhánh chính 11. 

5 Danh sách các lệnh Git đã sử dụng và làm chủ
    
git init: Khởi tạo kho lưu trữ Git cục bộ.

git status: Kiểm tra trạng thái thay đổi của các tệp tin trong thư mục làm việc.git add <tên_file> hoặc git add .: Đưa các tệp thay đổi vào vùng đệm .
 
git commit -m "Thông điệp": Lưu lại ảnh chụp lịch sử mã nguồn kèm mô tả.
 
git branch: Quản lý, kiểm tra và tạo mới các nhánh phát triển.
 
git branch -M main: Đổi tên nhánh mặc định thành main.
 
git remote add origin <url>: Kết nối kho lưu trữ cục bộ với kho lưu trữ từ xa trên GitHub.
 
git push -u origin <tên_nhánh>: Đẩy dữ liệu commit từ máy cục bộ lên GitHub.
 
git log --oneline --graph --all: Xem lịch sử commit dưới dạng sơ đồ cây rút gọn .
 
git revert : Hoàn tác một commit lỗi bằng cách tạo một commit đảo ngược một cách an toàn

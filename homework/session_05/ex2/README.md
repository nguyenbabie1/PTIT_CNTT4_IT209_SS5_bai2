\# Bài 2: Tái cấu trúc lịch sử commit bằng Interactive Rebase



\## Thông tin sinh viên



\- Họ tên: Đoàn Trung Nguyên

\- Mã sinh viên: B24DTCN435

\- Lớp: HN-K24-CNTT4



\## 1. Chuẩn bị



Khởi tạo repository với nhánh main và một commit nền.

Tạo nhánh feature-auth để thực hành.



\## 2. Tạo bốn commit



1\. feat: khoi tao module auth — tạo auth.js.

2\. fix typo — sửa lỗi chính tả trong auth.js.

3\. adds utility functions — bổ sung hàm tiện ích.

4\. add temp file for debug — tạo file rác temp.txt.



\## 3. Thực hiện Interactive Rebase



Chạy:



&#x20;   git rebase -i HEAD\~4



Cấu hình:



\- Commit 1: reword.

\- Commit 2: squash.

\- Commit 3: squash.

\- Commit 4: drop.



reword đổi thông điệp commit.

squash gộp commit vào commit trước.

drop loại bỏ commit khỏi lịch sử nhánh được viết lại.



Thông điệp cuối cùng:



&#x20;   feat: hoan thien module authentication



!\[Cấu hình Interactive Rebase](interactive-rebase.png)



\## 4. Kết quả kiểm tra



Chạy:



&#x20;   git log --oneline main..HEAD



Kết quả chỉ còn một commit tính năng:



&#x20;   feat: hoan thien module authentication



Kiểm tra:



&#x20;   Test-Path homework/session\_05/ex2/temp.txt



Kết quả False: file rác không còn trong thư mục làm việc.



Commit nền được giữ nguyên. Ba commit thay đổi auth.js đã được gộp

thành một, còn commit tạo temp.txt đã bị loại bỏ.



!\[Lịch sử sau rebase](after-rebase.png)



\## 5. Hoàn thiện bài nộp



Bổ sung README và ảnh vào chính commit tính năng bằng:



&#x20;   git commit --amend --no-edit



Thao tác này giữ nguyên thông điệp và số lượng commit tính năng,

nhưng mã commit cuối cùng sẽ khác mã trong ảnh minh chứng.



Sau đó gộp feature-auth vào main bằng fast-forward để nộp bài.


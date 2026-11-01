# TRẢ LỜI BÀI THỰC HÀNH GIT – MONEYNOTE LITE

**Câu 1.**  
Nhánh `main` có số commit được xác định bằng `git log --oneline main`. Bốn nhánh còn lại:
- `feature/giao-dien-moi`
- `feature/tieu-de`
- `feature/xuat-csv`
- `hotfix/sua-loi-cong`

**Câu 2.**  
tổng: 7 commit

**Câu 3.**  
Nguyễn Minh viết phần khai báo hàm tinhTong() tại dòng 1–3, commit 35b9229.
Lê Hùng chỉnh sửa phần xử lý tính tổng tại dòng 4–7, commit df17ab7.
Lỗi nằm ở dòng 6: reduce() sử dụng giá trị khởi tạo '' (chuỗi rỗng) thay vì 0 (số).
=> Người gây ra lỗi là Lê Hùng, trong commit df17ab7. Cần đổi giá trị khởi tạo từ '' thành 0 để phép tính tổng hoạt động chính xác.

**Câu 4.**  
- `git diff`: Xem thay đổi chưa được đưa vào staging.
- `git diff --staged`: Xem thay đổi đã được đưa vào staging.
- File `.env` không nên đưa lên Git vì có thể chứa mật khẩu, API key và thông tin bí mật.

**Câu 5.**  
3.1 là Fast-forward vì nhánh `main` chưa có commit mới riêng kể từ khi tạo nhánh. 3.2 tạo merge commit vì hai nhánh đã phát triển độc lập và có lịch sử commit khác nhau.

**Câu 6.**  
`feature/giao-dien-moi` không xung đột vì thay đổi giao diện và màu sắc. `feature/tieu-de` xung đột vì cùng sửa nội dung thẻ `<h1>` trong `index.html`.

**Câu 7.**  
Dùng `git revert` vì lệnh tạo commit mới để đảo ngược thay đổi, không xóa lịch sử chung. `git reset` có thể làm thay đổi lịch sử commit và ảnh hưởng đến thành viên khác.

**Câu 8.**
- `--soft`: Xóa commit, giữ thay đổi trong staging.
- `--mixed`: Xóa commit, giữ thay đổi trong working directory, bỏ staging.
- `--hard`: Xóa commit và loại bỏ thay đổi trong working directory.

**Câu 9.**  
Dùng `git bisect` để tìm commit đầu tiên gây lỗi, sau đó dùng `git show <mã-commit>` để xem nội dung, thông điệp và tác giả. Lỗi do thay đổi cách tính tổng thu khiến phép cộng thực hiện với chuỗi thay vì số.

**Câu 10.**  
Nếu dùng `git merge hotfix/sua-loi-cong`, Git sẽ gộp toàn bộ commit trên nhánh hotfix, bao gồm cả commit thử font Comic Sans chưa được duyệt. `cherry-pick` chỉ lấy commit sửa lỗi cần thiết.

**Câu 11.**  
Mã commit sau rebase không giống mã cũ vì Git tạo commit mới với mã hash mới. Không nên rebase nhánh người khác đã kéo về vì làm thay đổi lịch sử commit, gây khó khăn khi đồng bộ.

**Câu 12.**
- `git fetch`: Tải thông tin và commit mới từ remote nhưng không tự gộp vào nhánh hiện tại.
- `git pull`: Tải thay đổi từ remote và tự động tích hợp vào nhánh hiện tại (thường là fetch + merge).
# Danh sách lệnh Git đã sử dụng

## Khởi tạo & Cấu hình

| Lệnh | Mô tả |
|------|-------|
| `git init` | Khởi tạo repository mới |
| `git clone <url>` | Clone repository về máy |
| `git config user.name "Tên"` | Đặt tên người dùng |
| `git config user.email "email"` | Đặt email người dùng |
| `git config --list` | Xem toàn bộ cấu hình |

## Theo dõi thay đổi

| Lệnh | Mô tả |
|------|-------|
| `git status` | Xem trạng thái working directory |
| `git diff` | Xem thay đổi chưa được staged |
| `git diff --staged` | Xem thay đổi đã staged |
| `git log` | Xem lịch sử commit |
| `git log --oneline` | Xem lịch sử commit dạng rút gọn |
| `git log --oneline --graph` | Xem lịch sử dạng đồ thị branch |

## Staging & Commit

| Lệnh | Mô tả |
|------|-------|
| `git add <file>` | Stage file cụ thể |
| `git add .` | Stage toàn bộ thay đổi |
| `git commit -m "message"` | Tạo commit với message |
| `git commit --amend` | Sửa commit cuối cùng |

## Branch

| Lệnh | Mô tả |
|------|-------|
| `git branch` | Liệt kê các branch |
| `git branch <tên>` | Tạo branch mới |
| `git checkout <tên>` | Chuyển sang branch |
| `git checkout -b <tên>` | Tạo và chuyển sang branch mới |
| `git switch <tên>` | Chuyển branch (cú pháp mới) |
| `git switch -c <tên>` | Tạo và chuyển branch (cú pháp mới) |
| `git merge <branch>` | Merge branch vào branch hiện tại |
| `git branch -d <tên>` | Xóa branch đã merge |

## Remote

| Lệnh | Mô tả |
|------|-------|
| `git remote -v` | Xem danh sách remote |
| `git remote add origin <url>` | Thêm remote |
| `git push origin <branch>` | Push branch lên remote |
| `git push -u origin <branch>` | Push và set upstream |
| `git pull` | Kéo thay đổi từ remote |
| `git fetch` | Tải thay đổi nhưng không merge |

## Rollback & Revert

| Lệnh | Mô tả |
|------|-------|
| `git revert <hash>` | Tạo commit đảo ngược thay đổi (an toàn) |
| `git reset HEAD~1` | Bỏ commit cuối, giữ thay đổi |
| `git reset --hard HEAD~1` | Bỏ commit cuối, xóa thay đổi |
| `git restore <file>` | Khôi phục file về trạng thái cuối commit |
| `git stash` | Lưu tạm thay đổi chưa commit |
| `git stash pop` | Lấy lại thay đổi đã stash |

## Conflict

| Lệnh | Mô tả |
|------|-------|
| `git merge <branch>` | Merge — có thể gây conflict |
| `git status` | Xem file đang conflict |
| `git add <file>` | Đánh dấu conflict đã giải quyết |
| `git merge --abort` | Hủy merge đang conflict |

## Tìm kiếm lịch sử

| Lệnh | Mô tả |
|------|-------|
| `git log --author="Tên"` | Lọc commit theo tác giả |
| `git log --since="2024-01-01"` | Lọc commit theo ngày |
| `git log -- <file>` | Lịch sử của một file |
| `git blame <file>` | Xem ai sửa từng dòng |
| `git show <hash>` | Xem chi tiết một commit |

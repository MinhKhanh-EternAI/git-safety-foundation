# Ghi chú Part 1 — GitHub Foundations Cơ bản

## 1. Version Control là gì?

Version Control System (VCS) theo dõi mọi thay đổi trong code theo thời gian.
Git là VCS phân tán (DVCS) — mỗi người clone về có đầy đủ lịch sử.

Lợi ích:
- Biết ai sửa gì, khi nào, tại sao
- Quay lại phiên bản cũ bất kỳ lúc nào
- Thử nghiệm tính năng mới mà không ảnh hưởng code chính
- Làm việc nhóm không lo ghi đè lên nhau

## 2. Git vs GitHub

| Git | GitHub |
|-----|--------|
| Công cụ version control chạy local | Dịch vụ lưu trữ repo trên cloud |
| Quản lý lịch sử thay đổi | Giao diện web + collaboration tools |
| Dùng qua command line | Dùng qua web hoặc CLI |

## 3. Repository

- **Local repo**: trên máy tính của mình
- **Remote repo**: trên GitHub
- `git init` — tạo repo mới từ đầu
- `git clone` — sao chép repo đã có về máy

## 4. Workflow cơ bản

```
Working Directory → Staging Area → Local Repo → Remote Repo
      git add          git commit       git push
```

## 5. Branch

Branch cho phép làm việc song song, tách biệt với nhánh chính.

```
main ──●──●──────────────●── (merge)
            \            /
feature      ●──●──●────
```

- Luôn tạo branch mới khi phát triển tính năng
- Không commit thẳng vào `main`

## 6. Pull Request

Pull Request (PR) là đề xuất merge branch vào nhánh khác.
- Cho phép review code trước khi merge
- Thảo luận, comment, yêu cầu chỉnh sửa
- Có thể liên kết với Issues

## 7. GitHub Flow

1. Tạo branch từ `main`
2. Thực hiện thay đổi + commit
3. Tạo Pull Request
4. Review và thảo luận
5. Merge vào `main`
6. Xóa branch đã merge

## 8. GitHub Copilot

AI pair programmer tích hợp trong editor:
- Gợi ý code theo context
- Giải thích code
- Tạo unit test
- Chat để hỏi về code

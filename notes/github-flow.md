# GitHub Flow

## Quy trình chuẩn

```
1. Tạo branch từ main
       main ──●
               \
                ● feature/new-login

2. Commit thay đổi
       main ──●
               \
                ●──●──● feature/new-login

3. Tạo Pull Request
       main ──●
               \
                ●──●──● feature/new-login
                        [PR: đề xuất merge]

4. Review & thảo luận
   - Reviewer comment
   - Tác giả sửa thêm commit

5. Merge vào main
       main ──●──────────●
               \         /
                ●──●──●── feature/new-login

6. Xóa branch
       main ──●──────────●
```

## Nguyên tắc

- `main` luôn là code ổn định, sẵn sàng deploy
- Mọi tính năng đều bắt đầu từ branch mới
- Commit message rõ ràng, có ý nghĩa
- Pull Request là nơi thảo luận về thay đổi
- Merge sau khi được approve

## Commit message convention

```
<type>: <mô tả ngắn>

type có thể là:
- feat    : tính năng mới
- fix     : sửa lỗi
- docs    : cập nhật tài liệu
- refactor: cải thiện code không thay đổi chức năng
- test    : thêm hoặc sửa test
- init    : khởi tạo
```

## Ví dụ thực tế trong Vibe Coding

```bash
# Nhận yêu cầu tính năng mới
git checkout -b feature/user-authentication

# AI sinh code xác thực người dùng
# → review diff kỹ trước khi commit
git diff
git add src/auth.py
git commit -m "feat: add JWT authentication via GitHub Copilot"

# AI sinh thêm unit test
git add tests/test_auth.py
git commit -m "test: add unit tests for authentication module"

# Push và tạo PR để mentor review
git push origin feature/user-authentication
# → Tạo Pull Request trên GitHub
```

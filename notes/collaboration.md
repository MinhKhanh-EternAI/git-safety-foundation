# Ghi chú Part 2 — Cộng tác & Bảo mật

## 1. Đóng góp Open Source

Quy trình chuẩn khi đóng góp vào dự án open source:
1. **Fork** repo về tài khoản của mình
2. **Clone** fork về máy
3. Tạo branch mới, thực hiện thay đổi
4. **Push** lên fork
5. Tạo **Pull Request** về repo gốc
6. Chờ maintainer review và merge

Lưu ý: Đọc kỹ `CONTRIBUTING.md` và `CODE_OF_CONDUCT.md` trước khi đóng góp.

## 2. InnerSource

InnerSource áp dụng nguyên tắc open source trong nội bộ công ty:
- Mọi team có thể đóng góp vào repo của team khác
- Tăng tái sử dụng code
- Giảm silo giữa các team
- Cần tài liệu rõ ràng: README, CONTRIBUTING, issue templates

## 3. Bảo mật Repository

### Không được commit lên GitHub:
- API keys, tokens, passwords
- File `.env` chứa secrets
- Private keys, certificates
- Dữ liệu cá nhân người dùng

### Công cụ bảo vệ:
- **`.gitignore`**: ngăn track file nhạy cảm
- **GitHub Secret Scanning**: tự động phát hiện secrets bị commit
- **Dependabot**: cảnh báo dependency có lỗ hổng bảo mật
- **Code scanning (CodeQL)**: phân tích lỗ hổng trong code
- **Branch protection rules**: yêu cầu review trước khi merge vào main

## 4. Pull Request nâng cao

- **Draft PR**: tạo PR chưa sẵn sàng review, để thảo luận sớm
- **Review required**: bắt buộc ít nhất N người approve trước khi merge
- **Squash merge**: gộp nhiều commit thành 1 khi merge
- **Rebase merge**: giữ lịch sử tuyến tính
- **Auto-merge**: tự động merge khi đủ điều kiện

## 5. Tìm kiếm lịch sử

```bash
# Tìm commit theo nội dung message
git log --grep="keyword"

# Tìm thay đổi chứa chuỗi text
git log -S "function_name"

# Xem ai sửa từng dòng
git blame filename.md

# So sánh 2 branch
git diff main..feature/branch
```

## 6. GitHub Administration

- **Organization**: nhóm nhiều repo và thành viên
- **Teams**: phân quyền theo nhóm trong org
- **Repository roles**: Read, Triage, Write, Maintain, Admin
- **SAML SSO**: đăng nhập một lần cho toàn org
- **Audit log**: theo dõi mọi hành động trong org

## 7. Authentication & Authorization

- **HTTPS**: dùng Personal Access Token (PAT)
- **SSH**: dùng SSH key pair
- **GitHub Apps**: xác thực cho ứng dụng tích hợp
- **OAuth Apps**: xác thực qua OAuth flow
- **2FA**: bắt buộc bật để bảo mật tài khoản

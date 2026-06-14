# Bảo mật Repository trên GitHub

## Những gì KHÔNG được đưa lên GitHub

```
# Ví dụ file .gitignore cần có
.env
.env.local
*.key
*.pem
config/secrets.yml
node_modules/
__pycache__/
```

## Checklist bảo mật

- [ ] Đã có file `.gitignore` phù hợp
- [ ] Không có API key hoặc password trong code
- [ ] Branch protection rule bật trên `main`
- [ ] Bật 2FA cho tài khoản GitHub
- [ ] Dependabot alerts được bật
- [ ] Secret scanning được bật

## Branch Protection Rules

Cấu hình trên GitHub: Settings → Branches → Add rule

```
Branch name pattern: main
✅ Require a pull request before merging
✅ Require approvals (minimum 1)
✅ Dismiss stale pull request approvals
✅ Require status checks to pass
✅ Do not allow bypassing the above settings
```

## Nếu lỡ commit secret lên GitHub

```bash
# Bước 1: Thu hồi key/token ngay lập tức (ưu tiên hàng đầu)
# Bước 2: Xóa khỏi lịch sử git
git filter-branch --force --index-filter \
  "git rm --cached --ignore-unmatch path/to/secret-file" \
  --prune-empty --tag-name-filter cat -- --all

# Bước 3: Force push (cần cẩn thận khi làm việc nhóm)
git push origin --force --all
```

## Lưu ý khi dùng AI sinh code

- AI có thể vô tình sinh ra code chứa placeholder secrets
- Luôn review `git diff` trước khi commit code do AI tạo
- Dùng `git status` để kiểm tra file nào sắp được commit

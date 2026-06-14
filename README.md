# Git Safety Foundation Before Vibe Coding

## Giới thiệu

Repository này là bằng chứng thực hành cho khóa học **Git Safety Foundation** của AKA Lab — điều kiện bắt buộc trước khi tham gia khóa Vibe Code.

## Mục tiêu

Trong kỷ nguyên AI Coding, Git đóng 3 vai trò cốt lõi:

- **Phanh an toàn**: kiểm soát thay đổi trước khi đưa vào nhánh chính
- **Cỗ máy thời gian**: quay lại phiên bản ổn định khi AI sinh code lỗi
- **Ngôn ngữ cộng tác**: làm việc có kiểm soát giữa người, mentor và AI

## Quá trình học tập

### Part 1 — GitHub Foundations (Cơ bản)
- Introduction to Git
- Introduction to GitHub
- Introduction to GitHub's products
- Configure code scanning on GitHub
- Introduction to GitHub Copilot
- Code with GitHub Codespaces
- Manage your work with GitHub Projects
- Communicate effectively on GitHub using Markdown

### Part 2 — GitHub Foundations (Nâng cao)
- Contribute to an open-source project on GitHub
- Manage an InnerSource program by using GitHub
- Maintain a secure repository by using GitHub best practices
- Introduction to GitHub administration
- Authenticate and authorize user identities on GitHub
- Manage repository changes by using pull requests on GitHub
- Search and organize repository history by using GitHub
- Using GitHub Copilot with Python

## Minh chứng thực hành

| Yêu cầu | Trạng thái |
|---|---|
| 10+ commits có ý nghĩa | ✅ |
| 3+ branches | ✅ |
| 2+ pull requests | ✅ |
| 1 conflict scenario | ✅ |
| 1 rollback/revert | ✅ |

## Cấu trúc Repository

```
git-safety-foundation/
├── README.md                  # Mô tả quá trình học
├── git-commands-reference.md  # Danh sách lệnh Git đã dùng
├── notes/
│   ├── git-basics.md          # Ghi chú Part 1
│   ├── collaboration.md       # Ghi chú Part 2
│   ├── conflict-demo.md       # Demo xử lý conflict
│   └── rollback-demo.md       # Demo rollback/revert
```

## Tôi sẽ dùng Git như thế nào khi Vibe Code với AI?

Khi làm việc với AI để sinh code, tôi sẽ áp dụng Git theo quy trình sau:

1. **Tạo branch mới** trước mỗi tính năng do AI sinh ra — không bao giờ commit thẳng vào `main`
2. **Commit nhỏ, thường xuyên** sau mỗi đoạn code AI tạo ra để dễ rollback nếu có lỗi
3. **Review diff kỹ** trước khi commit code AI sinh — `git diff` là bước bắt buộc
4. **Dùng `git revert`** thay vì sửa trực tiếp khi AI tạo ra bug nghiêm trọng
5. **Tạo Pull Request** để mentor hoặc đồng đội review code AI trước khi merge vào main
6. **Dùng `git log`** để theo dõi lịch sử — biết chính xác AI đã thay đổi gì, khi nào

> Git là cầu nối an toàn giữa AI và codebase — bảo vệ sự ổn định của hệ thống production trước tốc độ sinh code của AI.

## Thông tin học viên

- **Họ tên**: Nguyễn Văn Minh Khánh
- **Khóa học**: AKA Lab — Git Safety Foundation Before Vibe Coding
- **Microsoft Learn**: Hoàn thành GitHub Foundations Part 1 & Part 2

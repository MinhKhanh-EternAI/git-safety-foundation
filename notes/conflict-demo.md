# Demo Xử lý Merge Conflict

## Conflict là gì?

Conflict xảy ra khi 2 branch sửa **cùng một dòng** trong cùng một file, và Git không thể tự quyết định giữ phiên bản nào.

## Tình huống thực tế

**Branch `main`** sửa dòng mô tả Git:
```
Git là công cụ version control phổ biến nhất thế giới.
```

**Branch `feature/learn-git-basics`** sửa cùng dòng đó thành:
```
Git là hệ thống quản lý phiên bản phân tán (DVCS) mạnh mẽ nhất.
```

Khi merge → **CONFLICT**.

## Kết quả conflict trong file

```
<<<<<<< HEAD (main)
Git là công cụ version control phổ biến nhất thế giới.
=======
Git là hệ thống quản lý phiên bản phân tán (DVCS) mạnh mẽ nhất.
>>>>>>> feature/learn-git-basics
```

- `<<<<<<< HEAD`: nội dung từ branch hiện tại (main)
- `=======`: ranh giới phân cách
- `>>>>>>> feature/...`: nội dung từ branch được merge vào

## Cách giải quyết

### Bước 1: Xem file bị conflict
```bash
git status
# both modified: notes/conflict-demo.md
```

### Bước 2: Mở file, chọn nội dung muốn giữ
Xóa toàn bộ marker (`<<<<<<<`, `=======`, `>>>>>>>`), giữ lại nội dung phù hợp:
```
Git là hệ thống quản lý phiên bản phân tán (DVCS) — phổ biến và mạnh mẽ nhất thế giới.
```

### Bước 3: Stage và commit
```bash
git add notes/conflict-demo.md
git commit -m "fix: resolve merge conflict in conflict-demo.md"
```

## Kết quả sau khi giải quyết

Conflict được resolve thành công. Branch merge vào main với nội dung đã chọn.

## Bài học rút ra

- Conflict không phải lỗi — là tín hiệu Git cần người quyết định
- Luôn đọc kỹ cả 2 phiên bản trước khi chọn
- Có thể dùng VS Code / IDE để giải quyết conflict dễ hơn
- Commit message sau khi fix conflict nên ghi rõ `fix: resolve conflict`

# Demo Rollback & Revert

## Khi nào cần rollback?

- AI sinh code lỗi làm hỏng tính năng đang chạy tốt
- Commit nhầm file nhạy cảm (API key, password)
- Tính năng mới gây regression
- Cần khôi phục về trạng thái ổn định trước đó

## Hai phương pháp chính

### Phương pháp 1: `git revert` (Khuyến nghị)

Tạo một commit **mới** đảo ngược nội dung commit cũ. **An toàn** vì không xóa lịch sử.

```bash
# Xem lịch sử để lấy hash commit cần revert
git log --oneline

# Output ví dụ:
# a1b2c3d feat: add broken feature by AI
# e4f5g6h feat: stable feature
# i7j8k9l init: setup repository

# Revert commit lỗi
git revert a1b2c3d

# Git tự tạo commit message: "Revert 'feat: add broken feature by AI'"
# Lịch sử được giữ nguyên, chỉ thêm commit mới đảo ngược
```

**Kết quả lịch sử sau revert:**
```
m0n1o2p Revert "feat: add broken feature by AI"  ← commit mới
a1b2c3d feat: add broken feature by AI            ← vẫn còn trong lịch sử
e4f5g6h feat: stable feature
i7j8k9l init: setup repository
```

### Phương pháp 2: `git reset` (Dùng cẩn thận)

Dịch chuyển HEAD về commit cũ hơn. **Nguy hiểm** khi đã push lên remote.

```bash
# Reset về commit trước, GIỮ thay đổi trong working directory
git reset HEAD~1

# Reset về commit trước, XÓA toàn bộ thay đổi
git reset --hard HEAD~1

# Reset về một commit cụ thể
git reset --hard e4f5g6h
```

## Thực hành trong repo này

### Bước 1: Tạo commit "lỗi" giả lập
```bash
echo "# File lỗi do AI sinh ra" > bad-code.md
git add bad-code.md
git commit -m "feat: add AI generated code (has bug)"
```

### Bước 2: Revert commit đó
```bash
git revert HEAD
# Hoặc dùng hash cụ thể: git revert abc1234
```

### Bước 3: Kiểm tra lịch sử
```bash
git log --oneline
# Thấy commit revert được thêm vào, commit cũ vẫn còn
```

## So sánh `revert` vs `reset`

| | `git revert` | `git reset --hard` |
|---|---|---|
| Lịch sử | Giữ nguyên + thêm commit mới | Xóa commit khỏi lịch sử |
| An toàn khi đã push | ✅ Có | ❌ Không |
| Dùng khi | Cần undo commit đã push lên remote | Chỉ dùng trên local chưa push |
| Cộng tác nhóm | ✅ An toàn | ❌ Gây vấn đề cho người khác |

## Bài học rút ra

Trong Vibe Coding với AI:
- Luôn dùng `git revert` khi cần rollback code đã push
- Commit thường xuyên để có nhiều điểm rollback
- Mỗi tính năng AI sinh ra = 1 branch riêng → dễ revert cả branch

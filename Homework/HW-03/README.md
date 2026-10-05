# Bài 3: Cấu hình tường lửa UFW và chuẩn đoán cổng mạng

### 1. Đăng nhập VPS quyền sudo
```bash
ssh root@<IP>
```

### 2. Đảm bảo cấu hình chặn tất cả đầu vào và mở tất cả đầu ra mặc định:
```bash
sudo ufw default deny incoming

sudo ufw default allow outgoing
```

### 3. Thêm quy tắc cho phép cổng SSH và cổng ứng dụng Web:
```bash
sudo ufw allow 22/tcp


sudo ufw allow 8080/tcp
```

### 4. Bật tường lửa
```bash
sudo ufw enable
```
- Gõ y để xác nhận cảnh báo có thể ngắt kết nối SSH hiện tại nếu cấu hình sai

## Kết quả kiểm tra:
- Xem trạng thái tường lửa chi tiết:
```bash
sudo ufw status verbose
```

- Kiểm tra các cổng đang lắng nghe thực tế trên máy chủ:
```bash
ss -tlnp
```
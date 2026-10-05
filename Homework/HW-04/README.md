# Bài 4: Quản lý tiến trình nền với nohup và tín hiệu Kill

### 1. Đăng nhâp quyền root
```bash
ssh root@<IP>
```

### 2. Tạo kịch bản script loop-monitor.sh
- Tạo và viết nội dung vào file script:
```bash
cat << 'EOF' > loop-monitor.sh
#!/bin/bash
while true; do
    echo "System time: $(date)" >> /tmp/monitor.log
    sleep 5
done
EOF
```

- ```ls -l loop-monitor.sh``` để kiểm tra xem file đã được tạo thành công hay chưa.


### 3. Cấp quyền thực thi cho file:
```bash
chmod +x loop-monitor.sh
```

### 4. Khởi chạy tiến trình dưới nền độc lập
```bash
nohup ./loop-monitor.sh > /dev/null 2>&1 &
```

### 5. Kiểm tra PID của tiến trình:
```bash
pgrep -f loop-monitor.sh
```


## Kiểm tra
**Kiểm tra tiến trình đang hoạt động:**
```bash
ps aux | grep loop-monitor.sh
```

**Kiểm tra tệp tin log đang được ghi liên tục:**
```bash
tail -n 10 /tmp/monitor.log
```

**Tắt tiến trình:**
```bash
kill -15 <PID_CUA_TIEN_TRINH>
```


# Bài 1: Khảo sát FHS và Phân quyền File/Folder nâng cao

### 1. Bước tiên quyết - đăng nhập
```bash
ssh root@<IP>
```

### 2. Khởi tạo cấu trúc thư mục bằng lệnh có đặc quyền sudo
```bash
sudo mkdir -p /var/www/my-app/public
```

```bash
sudo mkdir -p /var/www/my-app/logs
```

### 3. Gán quyền cho thư mục public
```bash
sudo chmod 750 /var/www/my-app/public
```

### 4. Gán quyền cho thư mục logs
```bash
sudo chmod 770 /var/www/my-app/logs
```

### 5. Đổi nhóm sở hữu về www-data 
```bash
sudo chown -R $USER:www-data /var/www/my-app
```


## Kết quả: sau câu lệnh 
```bash
ls -la /var/www/my-app
```

```bash
total 16
drwxr-xr-x 4 ubuntu www-data 4096 Oct  5 14:57 .
drwxr-xr-x 3 root   root     4096 Oct  5 14:57 ..
drwxrwx--- 2 ubuntu www-data 4096 Oct  5 14:57 logs
drwxr-x--- 2 ubuntu www-data 4096 Oct  5 14:57 public
```
# BÀI LÀM – THI THỬ HACKATHON 01

  

-  **Mã đề:** Thi thử

-  **Họ tên:** Bùi Hải Đăng

-  **Lớp:** CNTT2

-  **Link repository:**

-  **Hệ điều hành (Windows/macOS):** Window

  

## 4.2. Thao tác máy tính cơ bản bằng CLI

  

### Các lệnh đã chạy

  

```shell


 pwd
 Get-ChildItem -Force -Recurse
 mv .\nhap_hang.txt .\docs 
 cp .\media\logo_van_phong_pham.PNG .\back
 rm .\temp_131.tmp
 cd .\logs
 mv .\shop.log .\logs
 mv .\don_ban_thang_10.xlsx .\data
 Get-ChildItem -Force
 cd..
```

  

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

  

```text



Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/26/2026  12:26 AM                backup
d-----        10/26/2026  12:27 AM                data
d-----        10/26/2026  12:27 AM                docs
d-----        10/26/2026  12:27 AM                logs
d-----        10/26/2026  12:27 AM                media
-a----        10/26/2026  12:16 AM             78 .env
-a----        10/26/2026  12:16 AM           6105 don_ban_thang_10.xlsx
-a----        10/26/2026  12:16 AM           6053 logo_van_phong_pham.PNG
-a----        10/26/2026  12:16 AM             51 nhap_hang.txt
-a----        10/26/2026  12:16 AM           1053 shop.log
-a----        10/26/2026  12:16 AM             22 temp_131.tmp


PS C:\Users\BUI HAI DANG\Downloads\starter-kit (5)\starter-kit\Van Phong Pham Website FINAL> mv .\nhap_hang.txt .\docs
PS C:\Users\BUI HAI DANG\Downloads\starter-kit (5)\starter-kit\Van Phong Pham Website FINAL> mv .\logo_van_phong_pham.PNG .\media
PS C:\Users\BUI HAI DANG\Downloads\starter-kit (5)\starter-kit\Van Phong Pham Website FINAL> cp .\media\logo_van_phong_pham.PNG .\backup
PS C:\Users\BUI HAI DANG\Downloads\starter-kit (5)\starter-kit\Van Phong Pham Website FINAL> rm .\temp_131.tmp
PS C:\Users\BUI HAI DANG\Downloads\starter-kit (5)\starter-kit\Van Phong Pham Website FINAL> cd .\logs
PS C:\Users\BUI HAI DANG\Downloads\starter-kit (5)\starter-kit\Van Phong Pham Website FINAL\logs> Get-ChildItem -Force
PS C:\Users\BUI HAI DANG\Downloads\starter-kit (5)\starter-kit\Van Phong Pham Website FINAL\logs> cd ..
PS C:\Users\BUI HAI DANG\Downloads\starter-kit (5)\starter-kit\Van Phong Pham Website FINAL> mv .\shop.log .\logs
PS C:\Users\BUI HAI DANG\Downloads\starter-kit (5)\starter-kit\Van Phong Pham Website FINAL> mv .\don_ban_thang_10.xlsx .\data
PS C:\Users\BUI HAI DANG\Downloads\starter-kit (5)\starter-kit\Van Phong Pham Website FINAL> Get-ChildItem -Force


    Directory: C:\Users\BUI HAI DANG\Downloads\starter-kit (5)\starter-kit\Van Phong Pham Website FINAL


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/26/2026  12:31 AM                backup
d-----        10/26/2026  12:36 AM                data
d-----        10/26/2026  12:30 AM                docs
d-----        10/26/2026  12:36 AM                logs
d-----        10/26/2026  12:31 AM                media
-a----        10/26/2026  12:16 AM             78 .env


PS C:\Users\BUI HAI DANG\Downloads\starter-kit (5)\starter-kit\Van Phong Pham Website FINAL> cd..
  

```

  

## 4.3. Lọc log thủ công

  

### Lệnh đã chạy

  

```shell
Get-Content .\logs\shop.log
Get-Content .\logs\shop.log |Select-String "ERROR" |ForEach-Object { $_.Line } |Set-Content .\logs\daily_report.txt
Get-Content .\logs\daily_report.txt
  

```

  

### 2 dòng lỗi đầu tiên trong daily_report.txt

  

```text

2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi


```

  

## 4.4. Thao tác với tài liệu Markdown (README.md)

  

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

  

- [x] Heading 1: tên dự án

- [x] Mô tả ngắn có cả **in đậm** và *in nghiêng*

- [x] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu

- [x] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án

- [x] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành

- [x] Blockquote nhắc không upload `.env`

  

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

  

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

  

```shell

.\auto_report.ps1
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass

  

```

  

### Nội dung file logs/auto_report.txt

  

```text

# Script: auto_report.ps1
# Tac gia:
# Ngay tao: 23/10/2026

Write-Host "Dang loc log..."

"=== BAO CAO LOI ===" > logs/auto_report.

Get-Content logs/shop.log | Select-String "ERROR" >> logs/auto_report.txt

Write-Host "Hoan thanh!"


```

  

## 4.6. Đếm số dòng lỗi

  

### Lệnh

  

```shell

(Get-Content .\logs\shop.log |Select-String "ERROR").Count

  

```

  

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

  

```text

6

  

```

  

## 4.7. Báo cáo tổng hợp

  

### Các lệnh đã chạy

  

```shell

# Ghi lần lượt các lệnh đã chạy, mỗi lệnh một dòng (xoá dòng này)

  

```

  

### Nội dung file logs/tong_hop.txt

  

```text

 "=== TONG HOP LOG ===" |Set-Content .\logs\tong_hop.txt
 
 Get-Content .\logs\shop.log |Select-String "WARNING" | 
ForEach-Object { $_.Line } | Add-Content .\logs\tong_hop.txt

 "SO DONG ERROR: $((Get-Content .\logs\shop.log |Select-String 'ERROR').Count)" | Add-Content .\logs\tong_hop.txt  

```

  

## 4.8. Excel

  

> Phần Excel được chấm trực tiếp trên file `data/don_ban_thang_10.xlsx`, không cần ghi vào đây.

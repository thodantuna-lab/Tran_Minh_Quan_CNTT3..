# BÀI LÀM –(CHỦ ĐỀ QUẢN LÝ MODEL AI)

- **Mã đề:**
- **Họ tên:Trần Minh Quân**
- **Lớp:CNTT3**
- **Link repository:https://github.com/thodantuna-lab/Tran_Minh_Quan_CNTT3../blob/main/quan-ly-model-ai/README.md**
- **Hệ điều hành Windows**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell

PS C:\Users\admin\Downloads\Luyen_Tap_11_9\MiniPrjoect\starter-kit\quan-ly-model-ai> pwd
PS C:\Users\admin\Downloads\Luyen_Tap_11_9\MiniPrjoect\starter-kit\quan-ly-model-ai> ls -Force
PS C:\Users\admin\Downloads\Luyen_Tap_11_9\MiniPrjoect\starter-kit\quan-ly-model-ai> mv .\tai_lieu_ban_giao.txt .\docs\
PS C:\Users\admin\Downloads\Luyen_Tap_11_9\MiniPrjoect\starter-kit\quan-ly-model-ai> mkdir backup
PS C:\Users\admin\Downloads\Luyen_Tap_11_9\MiniPrjoect\starter-kit\quan-ly-model-ai> cp .\data\chi_phi_model_thang_11.xlsx .\backup\
PS C:\Users\admin\Downloads\Luyen_Tap_11_9\MiniPrjoect\starter-kit\quan-ly-model-ai> rm .\model_cache_01.tmp
PS C:\Users\admin\Downloads\Luyen_Tap_11_9\MiniPrjoect\starter-kit\quan-ly-model-ai> cd .\logs\
PS C:\Users\admin\Downloads\Luyen_Tap_11_9\MiniPrjoect\starter-kit\quan-ly-model-ai\logs> Get-ChildItem
PS C:\Users\admin\Downloads\Luyen_Tap_11_9\MiniPrjoect\starter-kit\quan-ly-model-ai\logs> cd ..
PS C:\Users\admin\Downloads\Luyen_Tap_11_9\MiniPrjoect\starter-kit\quan-ly-model-ai>
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
   Directory: C:\Users\admin\Downloads\Luyen_Tap_11_9\MiniPrjoect\starter-
    kit\quan-ly-model-ai


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/10/2026   1:43 PM                data
d-----        11/10/2026   1:42 PM                docs
d-----        11/10/2026   1:42 PM                evidence
d-----        11/10/2026   1:43 PM                logs
d-----        11/10/2026   1:41 PM                web
-a----        11/10/2026   1:41 PM             96 .env
-a----        11/10/2026   1:41 PM           2665 bai_lam.md
-a----        11/10/2026   1:41 PM             44 model_cache_01.tmp
-a----        11/10/2026   1:41 PM            204 tai_lieu_ban_giao.txt

```

## 4.3. Lọc log vận hành Model AI

### a) Lệnh lọc các dòng ERROR

```shell
PS C:\Users\admin\Downloads\Luyen_Tap_11_9\MiniPrjoect\starter-kit\quan-ly-model-ai> gc .\logs\inference.log | Select-String "ERROR"> .\logs\loi_model.txt

```

### 2 dòng đầu tiên trong logs/loi_model.txt

```text
2026-11-10 08:27:45 ERROR POST /v1/chat/completions model=CLAUDE-35
2026-11-10 08:31:12 ERROR POST /v1/audio/transcriptions model=WHISPER-V3


```

### b) Lệnh đếm số dòng WARNING và kết quả

```shell
PS C:\Users\admin\Downloads\Luyen_Tap_11_9\MiniPrjoect\starter-kit\quan-ly-model-ai> (gc .\logs\inference.log | Select-String "warning").count

```

```text
5

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
# Ghi lệnh vào đây (xoá dòng này)
PS C:\Users\admin\Downloads\Luyen_Tap_11_9\MiniPrjoect\starter-kit\quan-ly-model-ai> Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
PS C:\Users\admin\Downloads\Luyen_Tap_11_9\MiniPrjoect\starter-kit\quan-ly-model-ai> .\tong_hop.ps1
```

### Nội dung file logs/tong_hop.txt

```text
=== BAO CAO VAN HANH MODEL AI ===

2026-11-10 08:09:18 WARNING POST /v1/embeddings model=LLAMA-2-OLD
2026-11-10 08:16:05 WARNING GET /v1/fine-tune/jobs-legacy
2026-11-10 08:38:29 WARNING GET /images/model-card-v1.png
2026-11-10 09:01:44 WARNING POST /v1/completions model=DAVINCI-002
2026-11-10 09:14:02 WARNING GET /v1/quota/expired-key




Count    : 6
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property : 



```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [ ] README.md: Heading 1, hình ảnh (`![Alt](path)`), mô tả có **in đậm**, _in nghiêng_ và `inline code`, bảng, code block, task list, blockquote
- [ ] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [ ] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | -------------------------- | --------------------------- | -------------- |
| 1   |      Network                      |   network.png         |  đổi tên file ảnh thành đúng tên có trong đường dẫn              |
| 2   |      Console               |     console.png   |    đổi tên bảng giá thành đúng tên của nó trong js     |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:tôi là sinh viên năm nhất chưa sửa qua lỗi web trên js bao giờ**
- **Expected:tôi muốn sửa bảng giá hiện đầy đủ dữ liệu**
- **Actual:Không hiện bảng giá **
- **Log:Uncaught ReferenceError: hienThiBangModel is not defined**

### Câu tìm kiếm Google

```text
site:StackOverflow.com "Uncaught ReferenceError"

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/chi_phi_model_thang_11.xlsx`, không cần ghi vào đây.

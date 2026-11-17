# Bài tập thực hành tổng hợp: Kỹ thuật Prompting Nâng cao (Logic & Chuỗi)

## 1. Bối cảnh bài toán

Công ty Logistics cần tính toán chi phí vận chuyển 50 container từ Hà Nội đến TP.HCM.

**Mục tiêu:** Sử dụng Chain-of-Thought và Prompt Chaining để kiểm tra dữ liệu, tính toán chi phí và xử lý lỗi.

## 2. Thiết kế chuỗi Prompt

Quy trình thực hiện:

```
Dữ liệu đầu vào
      ↓
Bước 1: Kiểm tra dữ liệu
      ↓
Bước 2: Tính toán chi phí
      ↓
Bước 3: Kiểm tra kết quả
      ↓
Bước 4: Xuất báo cáo
```

## 3. Các Prompt thực thi

### Prompt 1: Kiểm tra dữ liệu

```
Bạn là chuyên viên Logistics.
Hãy kiểm tra dữ liệu vận chuyển 50 container.
Phát hiện dữ liệu thiếu, sai định dạng hoặc giá trị âm.
Không tự ý sửa dữ liệu.
Nếu dữ liệu không hợp lệ, hãy thông báo lỗi.
```

### Prompt 2: Tính toán

```
Sử dụng dữ liệu hợp lệ từ bước 1.
Tính chi phí vận chuyển, cầu đường, nhiên liệu và phát sinh.
Tính tổng chi phí và trình bày bằng bảng.
Không tự tạo dữ liệu.
```

### Prompt 3: Kiểm tra logic

```
Kiểm tra kết quả từ bước 2.
Đối chiếu số lượng container, đơn vị tiền tệ và phép tính.
Nếu có lỗi, thông báo và yêu cầu kiểm tra lại.
Nếu hợp lệ, đánh dấu VERIFIED.
```

### Prompt 4: Xuất báo cáo

```
Dựa trên kết quả VERIFIED từ bước 3.
Hãy xuất báo cáo tổng chi phí bằng Markdown.
Nếu dữ liệu chưa hợp lệ, không xuất báo cáo chính thức.
```

## 4. Xử lý lỗi

| Trường hợp | Cách xử lý |
|---|---|
| Thiếu dữ liệu | Yêu cầu bổ sung |
| Nhập chữ thay số | Báo lỗi định dạng |
| Giá trị âm | Từ chối dữ liệu |
| Tính toán sai | Kiểm tra lại |
| AI trả về sai cấu trúc | Yêu cầu xuất lại |

## 5. Kết quả chạy thử

**Dữ liệu giả định:**

| Khoản chi phí | Đơn giá/container |
|---|---|
| Vận chuyển | 15.000.000 VNĐ |
| Cầu đường | 1.000.000 VNĐ |
| Nhiên liệu | 2.000.000 VNĐ |
| Phát sinh | 500.000 VNĐ |

**Kết quả tính toán:**

| Khoản chi phí | Thành tiền |
|---|---|
| Vận chuyển | 750.000.000 VNĐ |
| Cầu đường | 50.000.000 VNĐ |
| Nhiên liệu | 100.000.000 VNĐ |
| Phát sinh | 25.000.000 VNĐ |
| **Tổng cộng** | **925.000.000 VNĐ** |

**Kết quả kiểm tra:**

- Dữ liệu hợp lệ: `VALID`.
- Kết quả tính toán: `VERIFIED`.
- Tổng chi phí: 925.000.000 VNĐ.

## 6. Kết luận

Qua bài thực hành, em đã kết hợp Chain-of-Thought, Prompt Chaining và xử lý lỗi để xây dựng quy trình gồm 4 bước liên kết.

Giải pháp giúp AI xử lý dữ liệu có trình tự, hạn chế sai sót, phát hiện dữ liệu bất thường và đưa ra kết quả rõ ràng.


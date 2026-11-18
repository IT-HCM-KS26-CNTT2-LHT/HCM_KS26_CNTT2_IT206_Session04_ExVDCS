# [Vận dụng chuyên sâu] Thiết kế giải pháp Prompting ứng dụng thực tế cho Kỹ thuật Prompting Nâng cao (Logic & Chuỗi)

## Bước 1: Thiết kế giải pháp (I/O)

### 1. Input (Dữ liệu đầu vào)

- Tên sản phẩm.
- Số lượng sản phẩm khách đặt.
- Đơn giá sản phẩm.
- Thông tin khách hàng.
- Tình trạng tồn kho.
- Thông tin khuyến mãi (nếu có).

### 2. Output (Kết quả đầu ra)

AI trả về kết quả gồm:

- Thông tin đơn hàng.
- Tổng tiền cần thanh toán.
- Kiểm tra tình trạng tồn kho.
- Thông báo nếu thiếu hoặc sai dữ liệu.
- Đề xuất hướng xử lý nếu đơn hàng có vấn đề.

## Bước 2: Viết prompt và chạy thử

### 1. Prompt hoàn chỉnh

> Bạn là trợ lý AI quản lý đơn hàng cho cửa hàng.
>
> **Nhiệm vụ:**
> 1. Kiểm tra thông tin đơn hàng và dữ liệu tồn kho.
> 2. Phân tích từng bước để xác định đơn hàng hợp lệ.
> 3. Tính tổng tiền dựa trên số lượng và đơn giá.
> 4. Nếu có khuyến mãi, áp dụng đúng điều kiện.
> 5. Nếu thiếu dữ liệu hoặc dữ liệu sai lệch, hãy thông báo rõ và không tự ý đoán.
> 6. Chia quy trình thành các bước: tiếp nhận dữ liệu → kiểm tra → tính toán → xuất kết quả.
> 7. Nếu câu trả lời quá dài hoặc bị gián đoạn, hãy tiếp tục từ phần còn thiếu, giữ nguyên dữ liệu và kết quả trước đó, không lặp lại.
>
> **Định dạng đầu ra:**
> - Tên khách hàng:
> - Sản phẩm:
> - Số lượng:
> - Đơn giá:
> - Tình trạng tồn kho:
> - Tổng thanh toán:
> - Trạng thái đơn hàng:
> - Lỗi dữ liệu (nếu có):
> - Hướng xử lý đề xuất:
>
> Hãy trình bày ngắn gọn, chính xác và dễ hiểu.

### 2. Kết quả chạy thử (Ví dụ)

- **Khách hàng:** Nguyễn Văn A.
- **Sản phẩm:** Áo thun.
- **Số lượng:** 2.
- **Đơn giá:** 150.000đ.
- **Tồn kho:** 10 sản phẩm.
- **Tổng thanh toán:** 300.000đ.
- **Trạng thái:** Đơn hàng hợp lệ.
- **Lỗi dữ liệu:** Không có.
- **Hướng xử lý:** Xác nhận đơn hàng và tiến hành giao hàng.


> => Giải pháp sử dụng Chain-of-Thought để phân tích logic, Prompt Chaining để chia nhỏ quy trình xử lý và kỹ thuật xử lý đứt gãy để duy trì tính nhất quán khi AI phản hồi bị gián đoạn.

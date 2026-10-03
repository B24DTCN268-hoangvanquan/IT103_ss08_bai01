Phân tích lỗi kỹ thuật
Lỗi 1 (Sai quy tắc điều phối FIFO): Đoạn code dùng waitingQueue.pop() lấy phần tử ở cuối mảng (LIFO), làm xe đến sau lại được sạc trước. Cần đổi thành waitingQueue.shift() để lấy phần tử ở đầu mảng (FIFO).

Lỗi 2 (Tính tổng ra NaN): Vòng lặp i <= completedSessionsKwh.length bị duyệt quá chỉ số hợp lệ. Khi i = length, completedSessionsKwh[i] trả về undefined. Phép cộng totalKwh + undefined làm totalKwh thành NaN (and kéo theo totalRevenue thành NaN). Cần sửa điều kiện thành i < completedSessionsKwh.length.
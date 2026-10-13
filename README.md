Phân tích lỗi & Lập bảng Test Cases (trình bày trong README.md):
Đọc hiểu mã nguồn, xác định dòng lệnh sai logic và phân tích nguyên nhân kỹ thuật dẫn đến sự cố nghiệp vụ.
- trong đề nói là khi chuyển sang ngày thứ 4 mới hạ sub.status nhưng mà code thì viết là "if (sub.daysOverdue >= 3)" gây ra lỗi
Lập bảng 02 Test Cases đối chứng gồm các cột: Trường hợp kiểm thử, Dữ liệu đầu vào, Kết quả sai thực tế, Kết quả đúng mong đợi.

Trường hợp kiểm thử: Ngày thứ 3 
Dữ liệu đầu vào: 
{ subscriptionId: 'SUB-001', customerName: 'Nguyen Van An', planTier: 'FAMILY', deviceLimit: 5, daysOverdue: 3, status: 'ACTIVE' }
Kết quả sai thực tế: 
sub.planTier = 'FREE';
sub.deviceLimit = 1;
sub.status = 'EXPIRED';
Kết quả đúng mong đợi: 
sub.status = 'GRACE_PERIOD';

Trường hợp kiểm thử: Ngày thứ 4
Dữ liệu đầu vào: 
{ subscriptionId: 'SUB-002', customerName: 'Tran Thi Mai', planTier: 'FAMILY', deviceLimit: 5, daysOverdue: 4, status: 'ACTIVE' }
Kết quả sai thực tế: 
không có sai
Kết quả đúng mong đợi: 
sub.planTier = 'FREE';
sub.deviceLimit = 1;
sub.status = 'EXPIRED';

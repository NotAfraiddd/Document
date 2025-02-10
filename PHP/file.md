# 1.Để chuyển mảng thành chuỗi ta dùng hàm gì? Để tách chuỗi thành mảng ta dùng hàm gì?
- Chuyển mảng thành chuỗi dùng: **implode(string kyTuPhanTach, array mang)**
    + Áp dụng được cho mảng tuần tự, mảng bất tuần tự, KHÔNG hỗ trợ cho mảng đa chiều.
- Chuyển chuỗi thành mảng dùng: **explode(string $separator, string $string, int $limit = PHP_INT_MAX): array**
    + Áp dụng cho chuỗi thành mảng tuần tự thôi.

# 2.So sánh serialize() vs json_encode()
- serialize: Chuyển đổi dữ liệu bất kì thành 1 chuỗi đặc biệt trong PHP
    + Chỉ hỗ trợ ngôn ngữ PHP
    + Dịnh dạng nhị phân
    + Hỗ trợ đầy đủ đủ các kiểu dữ liệu
- json_encode: chuyển đổi dữ liệu json thành array hoặc object đơn giản
    + Hỗ trợ đa ngôn ngữ.
    + Định dạng JSON
    + Hỗ trợ chủ yếu là array, object, string, number

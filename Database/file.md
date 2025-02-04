# SQL vs NoSQL khác nhau như thế nào? Khi nào nên dùng SQL và khi nào nên dùng NoSQL?
Khi nào dùng SQL?
- Dữ liệu có cấu trúc chặt chẽ, có mối quan hệ rõ ràng.
- Cần tính toàn vẹn dữ liệu cao (banking, giao dịch tài chính).
- Ứng dụng có nhiều join, quan hệ phức tạp giữa các bảng.
- Ví dụ: MySQL, PostgreSQL, SQL Server, Oracle.

 Khi nào dùng NoSQL?
- Dữ liệu phi cấu trúc hoặc thay đổi thường xuyên.
- Ứng dụng cần tốc độ cao, mở rộng linh hoạt.
- Big Data, real-time applications, chat, streaming, IoT.
- Ví dụ: MongoDB (document), Redis (key-value), Cassandra (column-family), Neo4j (graph).

# Index trong database là gì? Tại sao cần sử dụng index?
- Index (chỉ mục) trong cơ sở dữ liệu là một cấu trúc dữ liệu đặc biệt giúp tăng tốc truy vấn bằng cách cho phép tìm kiếm dữ liệu nhanh hơn, tương tự như mục lục trong một cuốn sách.

#  ACID là gì? Tại sao nó quan trọng trong hệ thống cơ sở dữ liệu?
- Atomicity (Tính nguyên tử), Consistency (Tính nhất quán), Isolation (Tính cô lập) và Durability (Tính bền vững).
giúp đảm bảo tính toàn vẹn và tin cậy của dữ liệu trong các giao dịch (transactions).
    + Atomicity (Tính nguyên tử): Một transaction (giao dịch) sẽ được thực hiện toàn bộ hoặc không.
    + Consistency (Tính nhất quán): Database phải luôn ở trạng thái hợp lệ trước và sau giao dịch. dữ liệu không thể rơi vào trạng thái lỗi
     vd: Nếu tài khoản ngân hàng không cho phép số dư âm, sau một giao dịch số dư không thể nhỏ hơn 0.
    + Isolation (Tính cô lập): Hệ thống đảm bảo kết quả của mỗi transaction không bị tác động bởi các transaction khác đang chạy song song.
    + Durability (Tính bền vững): Sau khi transaction hoàn tất, dữ liệu sẽ được lưu vĩnh viễn vào hệ thống cho dù như mất điện, crash
     Ví dụ: Sau khi bạn gửi tiền qua ngân hàng, dù hệ thống bị sập, tiền vẫn phải được ghi nhận khi hệ thống hoạt động lại.
    ###  Lưu ý:
    - SQL databases (MySQL, PostgreSQL, SQL Server) tuân thủ chặt chẽ ACID.
    - NoSQL databases (MongoDB) có thể không tuân thủ hoàn toàn ACID để tối ưu tốc độ và khả năng mở rộng (scalability).
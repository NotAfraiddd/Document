### Application and OS Images (Amazon Machine Image)
Là mẫu cấu hình có sẵn chứa tất cả thông tin về một EC2, bao gồm:
  - Hệ điều hành (OS): Linux, Windows, hoặc các hệ điều hành khác.
  - Phần mềm và ứng dụng: Các ứng dụng, công cụ hoặc cấu hình đã được cài đặt sẵn.
  - Cài đặt mặc định: Dung lượng lưu trữ, bảo mật, và quyền truy cập.

### Instance Type

- **t2.micro** là một instance loại t2 với 1 vCPU và 1 GiB bộ nhớ, phù hợp cho các ứng dụng nhẹ, website nhỏ, hoặc thử nghiệm.

- **t3**: Tương tự như t2, nhưng cải thiện hiệu suất và giảm chi phí. T3 có hiệu suất CPU tốt hơn và hỗ trợ CPU credits. Các ứng dụng cần khả năng xử lý thay đổi, như **web server, dev/test environment**. Ví dụ: t3.micro, t3.small, t3.medium.

- **m5**: Cân bằng giữa CPU và bộ nhớ, thích hợp cho các ứng dụng đòi hỏi bộ nhớ vừa phải và hiệu suất CPU ổn định. Các ứng dụng sản xuất, máy chủ cơ sở dữ liệu, và các ứng dụng doanh nghiệp. Ví dụ: m5.large, m5.xlarge, m5.2xlarge

- **c5**: Cao cấp về hiệu suất CPU, được tối ưu hóa cho các tác vụ tính toán nặng. **phân tích dữ liệu, học máy, biểu đồ 3D, và tính toán khoa học.** Ví dụ: c5.large, c5.xlarge, c5.9xlarge.

- **r5**: Tối ưu hóa cho bộ nhớ cao, với dung lượng bộ nhớ lớn hơn so với các instance khác. Các ứng dụng yêu cầu bộ nhớ lớn như **cơ sở dữ liệu** trong bộ nhớ, **phân tích dữ liệu lớn**, hoặc **ứng dụng khoa học**. Ví dụ: r5.large, r5.xlarge, r5.12xlarge.

- **p3**: Instance tối ưu cho tính toán GPU, với sự hỗ trợ mạnh mẽ cho các ứng dụng sử dụng machine learning và deep learning. **Training model trong AI, học máy, hoặc hình ảnh 3D**. p3.2xlarge, p3.8xlarge, p3.16xlarge.

- **i3**: Instance tối ưu hóa cho lưu trữ dữ liệu nhanh với bộ nhớ NVMe (Non-Volatile Memory Express), thường được sử dụng trong các ứng dụng cần truy xuất dữ liệu nhanh.Các ứng dụng như **cơ sở dữ liệu NoSQL, lưu trữ dữ liệu log, và hệ thống phân tán**. Ví dụ: i3.large, i3.xlarge, i3.4xlarge

- **z1d**: Instance này được tối ưu hóa cho các tác vụ đòi hỏi CPU cao và bộ nhớ cao, với bộ vi xử lý Intel Xeon Scalable và bộ nhớ lên tới 3.6 TB. Các ứng dụng yêu cầu **tính toán với độ trễ thấp hoặc xử lý cơ sở dữ liệu lớn**. Ví dụ: z1d.large, z1d.xlarge, z1d.12xlarge

- **a1**: Tối ưu hóa cho các ứng dụng dựa trên ARM với các vi xử lý Graviton của AWS. Các ứng dụng có khả năng chạy trên nền tảng ARM như **web server, microservices**.Ví dụ: a1.medium, a1.large, a1.xlarge.

### Cách chọn Instance Type phù hợp:
- T2 và T3: Dành cho các ứng dụng nhẹ, thử nghiệm, và không cần tài nguyên quá lớn.
- M5 và C5: Dành cho các ứng dụng sản xuất, web server, cơ sở dữ liệu, và phân tích dữ liệu.
- R5: Tốt cho các ứng dụng yêu cầu bộ nhớ lớn như cơ sở dữ liệu trong bộ nhớ.
- P3 và G4: Dành cho học máy, AI, và các tác vụ sử dụng GPU.
- I3: Thích hợp cho các ứng dụng cần tốc độ truy xuất dữ liệu nhanh và lưu trữ nhanh.
- A1: Dành cho ứng dụng tiết kiệm chi phí và muốn sử dụng nền tảng ARM.

# Enterprise Network Lab

Một lab mạng doanh nghiệp toàn diện được thiết kế để thực hành và học tập về kiến trúc mạng, định tuyến, định tính truy cập (ACL), và quản lý mạng quy mô lớn.

## 📋 Mô tả

Lab này bao gồm các tình huống thực tế về:
- Thiết kế và triển khai mạng doanh nghiệp
- Cấu hình các thiết bị mạng (Router, Switch, Firewall)
- Cấu hình định tính truy cập (ACL - Access Control List)
- Định tuyến giữa các phòng ban
- Bảo mật mạng cơ bản
- Quản lý lưu lượng mạng

## 🛠️ Công nghệ sử dụng

- **Cisco Packet Tracer** - Phần mềm mô phỏng mạng
- **Cisco IOS** - Hệ điều hành của thiết bị mạng
- **Giao thức định tuyến**: OSPF, RIP, EIGRP
- **ACL** - Để kiểm soát lưu lượng mạng
- **VLAN** - Phân tách mạng ảo

## 📁 Cấu trúc tệp

```
ENTERPRISE NETWORK LAB/
├── final.pkt              # Phiên bản hoàn thành của lab
├── truoc_ACL.pkt          # Phiên bản trước khi cấu hình ACL
└── README.md              # File tài liệu này
```

## 💻 Yêu cầu

Trước khi bắt đầu, bạn cần cài đặt:

1. **Cisco Packet Tracer** (Phiên bản 8.0 trở lên)
   - Tải từ: https://www.netacad.com/courses/packet-tracer
   - Yêu cầu tài khoản Cisco NetAcad (miễn phí)

2. **Máy tính** với cấu hình:
   - CPU: Intel Core i5 hoặc tương đương trở lên
   - RAM: Tối thiểu 4GB
   - Ổ cứng: Tối thiểu 2GB dung lượng trống

## 🚀 Hướng dẫn sử dụng

### 1. Mở file Lab

1. Mở **Cisco Packet Tracer**
2. Chọn **File** → **Open**
3. Chọn file `.pkt` bạn muốn mở:
   - `truoc_ACL.pkt` - Để xem phiên bản chưa cấu hình ACL
   - `final.pkt` - Để xem phiên bản hoàn chỉnh

### 2. Khám phá Topology

- Xem sơ đồ mạng tổng thể trong khu vực thiết kế (Design)
- Kiểm tra các thiết bị được kết nối
- Xem chi tiết cấu hình các interface

### 3. Thực hành Cấu hình

#### ACL Configuration (từ truoc_ACL.pkt → final.pkt)

```bash
# Trên Router
Router(config)# access-list 10 permit 192.168.1.0 0.0.0.255
Router(config)# access-list 10 deny any
Router(config)# interface fa0/0
Router(config-if)# ip access-group 10 in
```

#### Kiểm tra cấu hình

```bash
Router# show access-list
Router# show ip route
Router# show running-config
```

### 4. Kiểm tra kết nối

- Sử dụng công cụ **Ping** hoặc **Tracert** để kiểm tra kết nối giữa các thiết bị
- Kiểm tra bảng định tuyến trên các router
- Xác minh các quy tắc ACL đang hoạt động

## 📚 Các kịch bản học tập

### Kịch bản 1: Cấu hình ACL cơ bản
- Tạo danh sách kiểm soát truy cập tiêu chuẩn
- Áp dụng ACL trên các interface
- Kiểm tra lưu lượng được phép/từ chối

### Kịch bản 2: Định tuyến động
- Cấu hình OSPF hoặc EIGRP
- Kiểm tra sự hội tụ của định tuyến
- Kiểm tra bảng định tuyến

### Kịch bản 3: Bảo mật VLAN
- Cấu hình VLAN giữa các chi nhánh
- Áp dụng ACL giữa các VLAN
- Kiểm tra cô lập của VLAN

## 🔍 Các lệnh thường dùng

### Cấu hình chế độ

```bash
Router# configure terminal
Router(config)# ...
Router(config)# exit
Router#
```

### Xem cấu hình

```bash
Router# show running-config
Router# show startup-config
Router# show interfaces
Router# show ip route
Router# show ip protocols
```

### ACL Commands

```bash
Router# show access-list
Router# show access-list 10
Router(config)# no access-list 10        # Xóa ACL
Router(config)# access-list 10 remark    # Thêm ghi chú
```

## 📊 Hệ thống địa chỉ IP

| Mạng | Subnet Mask | Gateway | Ghi chú |
|------|-------------|---------|---------|
| 192.168.1.0 | /24 | 192.168.1.1 | LAN 1 |
| 192.168.2.0 | /24 | 192.168.2.1 | LAN 2 |
| 10.0.0.0 | /24 | 10.0.0.1 | LAN 3 |
| 172.16.0.0 | /24 | 172.16.0.1 | LAN 4 |

*(Cập nhật theo tình huống của bạn)*

## 🎯 Mục tiêu học tập

Sau khi hoàn thành lab này, bạn sẽ:

- ✅ Hiểu rõ kiến trúc mạng doanh nghiệp
- ✅ Thành thạo cấu hình Cisco IOS
- ✅ Biết cách tạo và áp dụng ACL
- ✅ Nắm vững định tuyến động
- ✅ Hiểu được VLAN và bảo mật mạng
- ✅ Có khả năng khắc phục sự cố mạng cơ bản

## 🤝 Đóng góp

Nếu bạn có cải tiến hoặc phát hiện lỗi:

1. Fork repository
2. Tạo branch cho tính năng của bạn (`git checkout -b feature/YourFeature`)
3. Commit thay đổi (`git commit -m 'Add some YourFeature'`)
4. Push lên branch (`git push origin feature/YourFeature`)
5. Mở Pull Request

## 📝 Ghi chú

- **Thời gian hoàn thành**: 2-4 giờ tùy theo kinh nghiệm
- **Độ khó**: Trung bình đến nâng cao
- **Đối tượng**: Sinh viên CCNA, kỹ sư mạng, IT professional

## 📖 Tài liệu tham khảo

- [Cisco IOS Documentation](https://www.cisco.com/c/en/us/support/ios-nx-os-software/index.html)
- [Cisco Academy Courses](https://www.netacad.com/)
- [Packet Tracer Tutorial](https://www.ccna.com/)
- [ACL Configuration Guide](https://www.cisco.com/c/en/us/support/security/access-control-list/)

## 📄 Giấy phép

Dự án này được cấp phép dưới giấy phép **MIT License** - xem file [LICENSE](LICENSE) để biết chi tiết.

## 👤 Tác giả

Được tạo bởi các kỹ sư mạng để phục vụ mục đích giáo dục.

---

**Cập nhật cuối cùng**: Tháng 8 năm 2026

**Lưu ý**: Hãy chắc chắn bạn có quyền sử dụng Cisco Packet Tracer theo Điều khoản sử dụng của Cisco.

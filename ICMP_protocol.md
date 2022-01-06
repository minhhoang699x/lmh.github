- Internet Control Messge Protocol (ICMP) cung cấp phản hồi về các vấn đề liên quan đến việc xử lí các gói IP trong các điều kiện nhất định

- Thông báo ICMP gồm:
    + Khả năng truy cập máy chủ - Host Reachability
    + Không thể truy cập điểm đến hoặc dịch vụ - Destination or Service Unreachable
    + Đã vượt quá thời gian - Time exceeded

***ICMP Echo Message***
- ICMP Echo Message có thể được sử dụng để kiểm tra khả năng truy cập của máy chủ lưu trữ trên mạng IP.
- Ví dụ: 
    + Máy chủ lưu trữ cục bộ gửi Echo Request đến máy chủ lưu trữ.
    + Nếu máy chủ khả dụng, máy chủ đích sẽ phản hồi bằng Echo Reply.
***ICMP Destination Ureachable Message***
- Thông báo ICMP Destination Unreachable có thể được sử dụng để thông báo cho nguồn tin rằng một điểm đến hoặc dịch vụ không thể truy cập được.
- Thông báo ICMP sẽ bao gồm một mã cho biết lý do tại sao không thể gửi được gói:
    - ICMPv4:
        + 0 - Net unreachable - Không thể truy cập mạng
        + 1 - Host unreachable - Máy chủ không thể truy cập
        + 2 - Protocol unreachable - Giao thức không thể truy cập
        + 3 - Port unreachable  - Port không thể truy cập

    - ICMPv6:
        + 0 - No route to destination - Không tìm được đường tới đích
        + 1 - Communication with the destination is administratively prohibited (e.g., firewall) - Giao tiếp với đích bị cấm về mặt quản trị (tường lửa)
        + 2 – Beyond scope of the source address - Ngoài phạm vi của địa chỉ nguồn
        + 3 - Address unreachable - Địa chỉ không thể truy cập
        + 4 - Port unreachable - Cổng không thể truy cập

***ICMP Time Exceeded Message***
 - Khi trường Time to Live trong IPv4 trong gói giảm về 0, thông báo ICMPv4 Time Exceeded sẽ được gửi đến máy đích.
 - IPv6 cũng gửi gói Time Exceeded, nhưng thay vì trường TTL như IPv4, ICMPv6 sử dụng trường Hop Limit để xác định xem gói đã hết hạn hay chưa.

***Ping***
- Lệnh ping là một tiện ích kiểm tra IPv4 và IPv6 sử dụng các thông báo yêu cầu một Echo Request và 1 phản hồi lại một Echo Reply để kiểm tra kết nối giữa các máy chủ và cung cấp một bản tóm tắt bao gồm tỷ lệ thành công và thời gian trung bình khứ hồi đến đích.
- Nếu không nhận được phản hồi trong thời gian chờ, ping sẽ cung cấp thông báo cho biết rằng không nhận được phản hồi.

***Ping the Loopback***
- Lệnh ping có thể dùng để kiếm tra cấu hình nội bộ của IPv4 và IPv6 trên local host. Để làm điều đó, ta dùng lệnh ping đến địa chỉ loopback là 127.0.0.1 cho IPv4 và ::1 cho IPv6.
- Phản hổi từ địa chỉ loopback cho biết rằng IP đã được cài đặt đúng cách trên host.
- Nếu nhận được một thông báo lỗi cho biết rằng TCP/IP chưa được cài đặt trên host.

***Ping the Default Gateway***
- Lệnh ping có thể được sử dụng để kiểm tra khả năng giao tiếp của máy chủ trên mạng cục bộ.
- Địa chỉ cổng mặc định thường được sử dụng nhất vì bộ định tuyến thường luôn hoạt động.
- Ping thành công đến cổng mặc định cho biết rằng máy chủ và giao diện bộ định tuyến đóng vai trò là cổng mặc định đều hoạt động trên mạng cục bộ.
- Nếu địa chỉ cổng mặc định không phản hồi, một ping có thể được gửi đến địa chỉ IP của một máy chủ khác trên mạng cục bộ được biết là đang hoạt động.

## Các phương thức được sử dụng để kiểm duyệt mạng
Tại Việt Nam, nhà mạng sử dụng 2 phương thức kiểm duyệt mạng chính đó là:
 1. Nhiễm độc DNS (DNS Spoofing/DNS Poisoning): Đây là phương pháp phổ biến nhất để kiểm duyệt mạng. Phương pháp này không chỉ phổ biến trong kiểm duyệt mạng trên phạm vi quốc gia mà nó còn phổ biến trong các hộ gia đình/công ty cũng thường xuyên sử dụng phương pháp này để ngăn chặn người dùng cơ bản truy cập các trang web quản trị viên không mong muốn. Nhưng phương pháp này không hiệu quả nếu người dùng đã biết trước địa chỉ IP của trang web mà họ truy cập, qua đó người dùng có thể truy cập trực tiếp vào trang web mà không cần hỏi DNS về IP của máy chủ đằng sau tên miền.
 2. Kiểm tra gói sâu (DPI/Deep Packet Inspection): Đây là phương pháp phổ biến để kiểm duyệt mạng trên phạm vi quốc gia nhưng không phổ biến trong hộ gia đình. Phương pháp này sử dụng các công nghệ kiểm duyệt để kiểm tra sâu rộng các gói mạng được truyền qua phương thức TCP/HTTP qua đó có thể ngăn chặn triệt để việc truy cập các trang web không mong muốn. Phương pháp này vô cùng hiệu quả, bởi vì kể cả khi người dùng biết địa chỉ tên miền/Địa chỉ IP của trang web họ cần truy cập thì kết nối vẫn sẽ không được thực hiện.

**Giải thích đơn giản:**

 1. Ví dụ bạn là shipper đang muốn đến nhà chú Việt để giao hàng. Do không biết nhà, bạn hỏi đường bác Nam bán trà đá đầu ngõ nhà bạn Việt. Nhưng do bạn hỏi đường quá to, thằng Kiểm Duyệt ngồi uống trà đá ở đó nghe thấy. Do có tư thù với chú Việt, thằng Kiểm Duyệt chặn họng bác Nam, nói với bạn rằng nhà chú Việt không phải ở trong ngõ này đâu, mà là ở ngõ trên kia kìa. Thế là bạn cảm ơn Kiểm Duyệt rối rít và đưa kiện hàng đến nơi thằng Kiểm Duyệt chỉ mà không biết rằng đó chính là nhà của nó chứ không phải của chú Việt. Trong câu chuyện này, shipper là trình duyệt của bạn, món hàng là truy vấn của bạn, nhà chú Việt là máy chủ của trang web mà bạn muốn truy cập, ngõ nhà chú Việt là Internet, bác Nam là máy chủ DNS không kiểm duyệt, còn thằng Kiểm Duyệt thì y như cái tên, máy chủ DNS đã bị kiểm duyệt và đưa truy vấn của bạn đi sai đường, còn nhà thằng Kiểm Duyệt là máy chủ giả mạo trang web mà bạn muốn truy cập. Theo đó, nếu bạn đã biết nhà chú Việt và không cần hỏi đường thì bạn vẫn có thể giao món hàng thành công.
 2. Lần này, bạn vẫn là anh shipper kém may mắn đó. Thằng Kiểm Duyệt giờ đang giữ chức công an phường và vẫn ngồi quán trà đá của bác Nam ở đầu ngõ nhà chú Việt. Rút kinh nghiệm lần trước, bạn đã bảo chú Việt gửi hẳn địa chỉ trên Google Map cho chắc. Nhưng vừa định vô ngõ nhà chú Việt, thằng Kiểm Duyệt chặn bạn lại với lý do đang thực hiện chuyên án buôn bán cần sa ở trong ngõ này và cần kiểm tra mọi món đồ trong giỏ hàng của bạn. Thằng Kiểm Duyệt lục lọi trong giỏ hàng của bạn và phát hiện món đồ có ghi người nhận là chú Việt, thế là nó tịch thu, thậm chí đập nát món đồ đó và đuổi bạn về. Trong câu chuyện này, Kiểm Duyệt đóng vai khác là hệ thống Kiểm tra gói sâu. Nếu chú Việt đặt hàng bằng tên vợ của chú Việt là cô Huyền thì thằng Kiểm Duyệt sẽ không phát hiện ra và cho bạn vào trong ngõ, mặc dù nhà cô Huyền và chú Việt là một. Trong câu chuyện này, cô Huyền là tên miền mới/máy chủ mới của trang web, cung cấp cùng một nội dung của trang web cũ nhưng do thằng Kiểm Duyệt chưa cập nhật thông tin là chú Việt đã lấy vợ nên không biết để kiểm duyệt.

## Cách để vượt qua kiểm duyệt mạng ở Việt Nam
Qua hai câu chuyện ngắn ở trên, ta có thể thấy chỉ cần biết địa chỉ chính xác và thay đổi tiêu đề của gói hàng thì gói hàng sẽ có thể đến tay chú Việt một các an toàn mà không bị thằng Kiểm Duyệt chặn. Vậy có những cách nào để vượt qua kiểm duyệt mạng ở Việt Nam?
1. DNS qua HTTPS/TLS: Truy vấn đến máy chủ DNS thông qua phương thức bảo mật HTTPS/TLS cách duy nhất để có thể tránh nhiễm độc DNS (ngoài cách tự xây dựng DNS riêng). Hai DNS mình khuyên các bạn dùng là CloudFlare DNS và AdGuard DNS.
2. Sử dụng phần mềm để đánh lừa hệ thống DPI. Các bạn có thể làm xáo trộn tiêu đề của các gói tin truyền qua Layer 4. Vì DPI đa số chỉ quét 3 lớp trong mô hình OSI, nơi định tuyến các gói mạng nên ta có thể làm cho các gói mạng trông "khác đi" một tí và qua mặt hệ thống này. Có rất nhiều phần mềm mã nguồn mở cung cấp khả năng đánh lừa hệ thống DPI, chi tiết mình sẽ cũng cấp trong mục sau.
3. Sử dụng một đường hầm kết nối, phổ biến nhất là VPN. VPN là mạng riêng ảo, khi bạn kết nối đến một trang web thì nhà mạng sẽ chỉ thấy bạn đang kết nối đến máy chủ VPN. Phương thức hoạt động của VPN là sẽ tạo ra một đường hầm giữa bạn và trang web bạn muốn truy cập để tránh mọi sự kiểm soát của nhà mạng với bạn. Tuy rằng VPN dễ bị đánh chặn, ví dụ như Trung Quốc thường chặn VPN trước các sự kiện chính trị lớn,  nhưng do cái quan trọng thực sự của VPN là máy chủ chứ không phải IP nên bỏ qua việc chặn VPN là cực kì dễ dàng. Tuy nhiên, mình khuyên bạn nên tự tạo máy chủ VPN của riêng mình mà không sử dụng bên thứ ba, vì VPN thường để lại các tệp nhật kí nhằm cho việc định tuyến đường hầm trở nên khả thi nên khi bị các cơ quan chức năng tịch thu máy chủ thì thông tin truy cập của bạn vẫn có thể lộ lọt ra ngoài.

# Tài nguyên
## DNS qua HTTPS
1. CloudFlare:
- Không có bộ lọc: https://cloudflare-dns.com/dns-query
- Lọc các trang web mã độc/lừa đảo: https://security.cloudflare-dns.com/dns-query
- Lọc các trang web mã độc/lừa đảo/khiêu dâm: https://family.cloudflare-dns.com/dns-query
2. AdGuard:
- Không có bộ lọc: https://unfiltered.adguard-dns.com/dns-query
- Lọc quảng cáo, trình theo dõi: https://dns.adguard-dns.com/dns-query
- Lọc quảng cáo, tình theo dõi, trang web khiêu dâm, kết quả tìm kiếm khiêu dâm: https://family.adguard-dns.com/dns-query
## DNS qua TLS
1. CloudFlare:
- Không có bộ lọc: cloudflare-dns.com
- Lọc các trang web mã độc/lừa đảo: security.cloudflare-dns.com
- Lọc các trang web mã độc/lừa đảo/khiêu dâm: family.cloudflare-dns.com
2. AdGuard:
- Không có bộ lọc: unfiltered.adguard-dns.com
- Lọc quảng cáo, trình theo dõi: dns.adguard-dns.com
- Lọc quảng cáo, tình theo dõi, trang web khiêu dâm, kết quả tìm kiếm khiêu dâm: family.adguard-dns.com
## DPI Spoofing
- Windows: [GoodbyeDPI by ValdikSS](https://github.com/ValdikSS/GoodbyeDPI)
- Linux/MacOS: [SpoofDPI by xvzc](https://github.com/xvzc/SpoofDPI)
- Android: [PowerTunnel by krlvm](https://github.com/krlvm/PowerTunnel-Android)
- Windows/Linux/MacOS: [PowerTunnel by krlvm](https://github.com/krlvm/PowerTunnel)
## VPN
### VPN được quản lý
VPN được quản lý là các máy chủ VPN được cấu hình sẵn để truy cập.
1. VPN dễ sử dụng: [NordVPN (aff)](https://go.nordvpn.net/aff_c?offer_id=658&aff_id=56406).
NordVPN là một VPN dễ sử dụng, đăng nhập và sử dụng qua tài khoản NordVPN nên dễ dàng quản lý. NordVPN có các IP với độ tin cậy cao nhằm tránh bị liệt vào Blacklist. NordVPN cũng có các máy chủ VPN để có thể xem các nội dung bị cấm theo địa lý trên Netflix, Spotify, Hulu, v.v
2. VPN không có tài khoản:
- [Mullvad VPN](https://mullvad.net/): Mullvad VPN là một VPN được quản lý, không có tài khoản, không có nhật kí, không có lời hứa sặc mùi quảng cáo. Mullvad VPN đơn giản là VPN và quyền riêng tư.
- [IVPN](https://www.ivpn.net/): IVPN cũng giống như Mullvad, là một VPN được quản lý không có tài khoản, không có nhật ký.
### VPN miễn phí
**LƯU Ý QUAN TRỌNG**: KHÔNG BAO GIỜ TIN TƯỞNG BẤT CỨ DỊCH VỤ VPN MIỄN PHÍ NÀO NGOÀI 2 DỊCH VỤ ĐƯỢC LIỆT KÊ Ở DƯỚI ĐÂY. VIỆC SỬ DỤNG VPN MIỄN PHÍ ĐEM LẠI RỦI RO CỰC KÌ CAO. NHÀ CUNG CẤP VPN MIỄN PHÍ CÓ THỂ BÁN THÔNG TIN CỦA BẠN, NGUY HIỂM HƠN CHÚNG CÓ THỂ LÀ HONEYPOT, BIẾN THIẾT BỊ CỦA BẠN THÀNH CÔNG CỤ KHAI THÁC, TẤN CÔNG!
Hai VPN miễn phí duy nhất được mình khuyến nghị là:
- [CloudFlare Warp](https://1.1.1.1/): Một VPN miễn phí của CloudFlare, không thực sự bảo vệ bạn hoàn toàn nhưng có thể giúp bạn truy cập các trang web bị nhà mạng cấm một cách dễ dàng.
- [Proton VPN](https://protonvpn.com/): Một VPN MIỄN PHÍ DUY NHẤT TRÊN THẾ GIỚI CỦA CÔNG TY LỚN thực sự bảo mật. VPN không có nhật kí, trụ sở công ty được đặt ở quốc gia đặt quyền riêng tư trên hàng đầu. Có các máy chủ đặt ở căn cứ quân sự cũ được Proton mua lại (chỉ máy chủ Secure Core ở gói trả phí).
### VPN không được quản lý
VPN không được quản lý, hay còn gọi là tự quản lý là máy chủ VPN do chính bạn tạo ra. Đặc điểm của loại VPN này là bạn an toàn tuyệt đối, vì máy chủ VPN thuộc sở hữu của bạn. Nhà cung cấp máy chủ được tin cậy là:
#### [BuyVM](https://my.frantech.ca/aff.php?aff=5042)
Đây là nhà cung cấp duy nhất mình tin cậy. BuyVM cung cấp máy chủ ở các vị trí chống kiểm soát luật mạnh mẽ. BuyVM chấp nhận các phương thức thanh toán bằng tiền ảo nên có thể xóa dấu vết dễ dàng hơn. Ngoài ra, giá server ở đây **CỰC KÌ RẺ**, phù hợp để làm máy chủ VPN mà không phải chi quá nhiều tiền.
#### Script cài đặt máy chủ VPN riêng tư nhanh
[OpenVPN Install](https://github.com/angristan/openvpn-install)
[OpenVPN Connect](https://openvpn.net/vpn-client/)
## Tham khảo bài viết khác về cách bảo mật thông tin trên mạng
[OPSEC Guilde by NDBIAW](https://github.com/ndbiaw/opsec-guide)

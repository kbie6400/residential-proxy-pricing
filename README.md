# proxy dân cư: nên mua theo IP hay theo GB, giá thực tế và cách chọn gói đúng nhu cầu

Ai tìm cụm "proxy dân cư" thường đã biết mình cần gì. Vấn đề nằm ở chỗ khác: có quá nhiều nhà cung cấp, mỗi nơi báo giá một kiểu, và rất ít chỗ nói rõ rằng bạn đang bị tính tiền theo *số IP* hay theo *dung lượng*. Chọn sai kiểu tính tiền thì dù đơn giá có rẻ đến đâu, hóa đơn cuối tháng vẫn phình ra vô ích.

Bài này đi từ gốc: proxy dân cư là gì, hai kiểu tính tiền khác nhau ở đâu, rồi lấy 9Proxy làm ví dụ cụ thể với bảng giá đầy đủ để bạn đối chiếu trước khi xuống tiền.

## Proxy dân cư khác gì proxy datacenter

Proxy dân cư là proxy trung gian đẩy traffic của bạn ra Internet qua địa chỉ IP do nhà mạng viễn thông cấp cho một hộ gia đình thật. Website nhận request sẽ thấy một kết nối băng thông rộng bình thường, không thấy dấu hiệu của máy chủ.

Điểm mấu chốt nằm ở ASN. IP datacenter thuộc các dải của AWS, Google Cloud, Alibaba Cloud — website nhận diện và chặn theo lô rất dễ. IP dân cư thuộc dải của Viettel, FPT, VNPT hay AT&T, Comcast, nhìn ở tầng mạng thì không phân biệt được với khách hàng thật.

Khoảng cách về tỷ lệ thành công không nhỏ. Theo bảng so sánh trên Scrapeless, khi nhắm vào các mục tiêu được bảo vệ:

| Loại mục tiêu | Proxy dân cư | Proxy ISP | Proxy datacenter |
| --- | --- | --- | --- |
| Thương mại điện tử (Amazon, eBay) | 95–99% | 85–90% | 30–40% |
| Mạng xã hội (Instagram, Facebook) | 97–99% | 80–85% | 20–30% |
| Trang du lịch (Booking, Expedia) | 96–99% | 80–88% | 25–35% |
| Mạng quảng cáo | 95–98% | 85–92% | 40–50% |

Đổi lại, proxy dân cư chậm hơn. Độ trễ trung bình 50–200ms và thông lượng thường 1–3 Mbps mỗi thiết bị, vì traffic đang đi qua đường truyền nhà của một người thật. Nếu bạn cần tốc độ thuần túy để tải file nặng, datacenter vẫn thắng.

Còn về giá, mức chung của thị trường cho proxy dân cư thường rơi vào khoảng $5–15/GB ở phân khúc cao cấp. Đó là lý do các nhà cung cấp giá rẻ như 9Proxy, DataImpulse hay GeoNode tồn tại, và cũng là lý do bạn cần hiểu rõ mình đang trả tiền cho cái gì.

## Trả tiền theo IP hay theo GB: quyết định quan trọng nhất

Một nửa thị trường tính giá theo dung lượng, nửa còn lại tính theo số địa chỉ. Hai mô hình này cho ra chi phí hoàn toàn khác nhau tùy cách bạn dùng.

**Trả theo IP (băng thông không giới hạn).** Bạn mua một số lượng IP cố định, dùng bao nhiêu dữ liệu cũng không bị tính thêm. Phù hợp khi bạn giữ phiên dài, tải nhiều, hoặc không đoán được mức tiêu thụ dữ liệu. Ví dụ: treo tài khoản, chạy tool liên tục, scrape trang nặng JavaScript.

**Trả theo GB.** Bạn nạp một lượng traffic, IP xoay thoải mái trong pool. Phù hợp khi mỗi request dùng ít dữ liệu nhưng cần đổi IP liên tục: kiểm tra vị trí quảng cáo, kiểm tra giá theo khu vực, gọi API, test nhẹ.

Cách kiểm tra đơn giản: nếu bạn dùng đúng vài chục IP nhưng băng thông chạy vài chục GB mỗi tháng, mô hình theo IP gần như luôn rẻ hơn. Còn nếu bạn cần hàng nghìn IP nhưng mỗi tháng chỉ tốn vài GB, mua theo IP là tự bắn vào chân mình.

## 9Proxy và hai kiểu tính tiền đó

9Proxy là nhà cung cấp proxy dân cư thành lập năm 2023, hiện công bố pool hơn 20 triệu IP dân cư ở hơn 90 quốc gia, hỗ trợ HTTP, HTTPS và SOCKS5. Hỗ trợ định vị theo quốc gia, bang, thành phố, mã ZIP và cả ISP — mức chi tiết này quan trọng khi bạn cần traffic trông giống người dùng thật ở một khu vực cụ thể.

Điểm đáng chú ý là họ bán song song cả hai mô hình, và cách vận hành khá rõ ràng:

- **Gói theo IP**: số IP cố định, băng thông không giới hạn, IP không hết hạn sau khi mua (hệ thống chạy theo số dư, không phải subscription hàng tháng).
- **Gói theo GB**: nạp traffic, tạo không giới hạn đầu proxy, chọn phiên sticky hoặc xoay liên tục, xác thực bằng user/pass hoặc whitelist IP.
- **Gói bundle**: kết hợp IP và GB trong một gói, dành cho ai cần cả phiên ổn định lẫn traffic linh hoạt.

Về công cụ, 9Proxy có Proxy Program (client Windows chạy ở tầng hệ điều hành, dùng được với phần mềm không hỗ trợ proxy), Proxy2Web (không cần cài, xác thực bằng user:pass, tiện kiểm tra nhanh trên trình duyệt), ProxyHub và ProxyHub Pro cho quản lý thiết bị di động, cùng Public API cho pipeline tự động. SOCKS5 có sẵn nên cắm thẳng vào AdsPower, Dolphin Anty, BitBrowser hay proxychains đều được.

Vài tính năng ảnh hưởng trực tiếp đến chi phí: tính năng Today List cho phép dùng lại miễn phí các IP đã lấy trong 24 giờ trước, theo hướng dẫn tích hợp của Scrapeless thì tiết kiệm thêm khoảng 20–30%. Cơ chế auto-refresh tự phát hiện và thay IP offline trong vòng 60 giây, nên bạn không phải ngồi canh tool chết giữa phiên.

## Bảng giá proxy dân cư 9Proxy

Ngày 18/5/2026, 9Proxy công bố đợt điều chỉnh giá đầu tiên trong lịch sử công ty, áp dụng từ 1/6/2026. Gói theo IP và gói bundle tăng giá; gói theo GB giữ nguyên. Bảng dưới đây là mức giá được ghi nhận sau đợt điều chỉnh đó.

### Gói theo IP (băng thông không giới hạn)

| Gói | Số IP nhận được | Đơn giá/IP | Tổng | Link mua |
| --- | --- | --- | --- | --- |
| Cơ bản | 100 IP | $0.24 | $24 | [ Xem gói 100 IP](https://bit.ly/9-Proxy) |
| Nhỏ | 500 IP | $0.144 | $72 | [ Xem gói 500 IP](https://bit.ly/9-Proxy) |
| Phổ biến | 1.000 IP + tặng 500 IP | $0.084 | $126 | [ Xem gói 1.000 + 500 IP](https://bit.ly/9-Proxy) |
| Tăng dần | 2.500 IP | $0.084 | $210 | [ Xem gói 2.500 IP](https://bit.ly/9-Proxy) |
| Nhóm nhỏ | 5.000 IP | $0.072 | $360 | [ Xem gói 5.000 IP](https://bit.ly/9-Proxy) |
| Doanh nghiệp vừa | 15.000 IP | $0.048 | $720 | [ Xem gói 15.000 IP](https://bit.ly/9-Proxy) |
| Bán lại | 25.000 IP | $0.035 | $863 | [ Xem gói 25.000 IP](https://bit.ly/9-Proxy) |
| Khối lượng lớn | 50.000 IP | $0.029 | $1.438 | [ Xem gói 50.000 IP](https://bit.ly/9-Proxy) |
| Business | 100.000 IP | $0.023 | $2.300 | [ Xem gói 100.000 IP](https://bit.ly/9-Proxy) |
| Business | 200.000 IP | $0.021 | $4.140 | [ Xem gói 200.000 IP](https://bit.ly/9-Proxy) |
| Business | 500.000 IP | $0.018 | $8.625 | [ Xem gói 500.000 IP](https://bit.ly/9-Proxy) |

### Gói theo GB (dung lượng)

| Gói | Dung lượng | Đơn giá/GB | Tổng | Hiệu lực | Link mua |
| --- | --- | --- | --- | --- | --- |
| Thử nghiệm | 5 GB | $3.00 | $15 | 180 ngày | [ Xem gói 5 GB](https://bit.ly/9-Proxy) |
| Tiết kiệm | 50 GB + tặng 5 GB | $2.10 | $105 | 180 ngày | [ Xem gói 50 GB](https://bit.ly/9-Proxy) |
| Vừa | 100 GB | $1.50 | $150 | 180 ngày | [ Xem gói 100 GB](https://bit.ly/9-Proxy) |
| Khá | 200 GB | $1.00 | $200 | 180 ngày | [ Xem gói 200 GB](https://bit.ly/9-Proxy) |
| Lớn | 1.000 GB | $0.80 | $800 | 180 ngày | [ Xem gói 1.000 GB](https://bit.ly/9-Proxy) |
| Lớn hơn | 2.000 GB | $0.75 | $1.500 | 180 ngày | [ Xem gói 2.000 GB](https://bit.ly/9-Proxy) |
| Enterprise | 3.000 GB | $0.72 | $2.160 | Không hết hạn | [ Xem gói Enterprise 3.000 GB](https://bit.ly/9-Proxy) |
| Enterprise | 6.000 GB | $0.70 | $4.200 | Không hết hạn | [ Xem gói Enterprise 6.000 GB](https://bit.ly/9-Proxy) |
| Enterprise | 10.000 GB | $0.68 | $6.800 | Không hết hạn | [ Xem gói Enterprise 10.000 GB](https://bit.ly/9-Proxy) |

### Gói bundle (IP + GB)

| Gói | Cấu hình | Giá | Ghi chú | Link mua |
| --- | --- | --- | --- | --- |
| Starter | 100 IP + 5 GB | $30 | Phần GB hiệu lực 180 ngày | [ Xem gói Starter](https://bit.ly/9-Proxy) |
| Popular | 1.500 IP + 50 GB | $180 | Phù hợp nhóm vài dự án | [ Xem gói Popular](https://bit.ly/9-Proxy) |
| Pro | 5.000 IP + 500 GB | $720 | Gói all-in cho shop lớn hơn | [ Xem gói Pro](https://bit.ly/9-Proxy) |

Vài lưu ý về bảng trên. Thứ nhất, giá có thể thay đổi theo chương trình hiện hành và theo phương thức thanh toán, nên con số cuối cùng vẫn là con số hiển thị ở bước thanh toán trong dashboard. Thứ hai, gói Enterprise không chỉ là dung lượng lớn hơn: nó đi kèm chế độ team (1 owner và tối đa 5 thành viên), chia sẻ băng thông không hết hạn trong nội bộ nhóm, kiểm soát traffic theo từng thành viên, log hoạt động đầy đủ và hỗ trợ riêng. Nếu bạn chạy agency, phần này đáng tính hơn là vài cent chênh lệch trên mỗi GB.

## Chi phí thực tế cho vài tình huống ở Việt Nam

Con số đẹp trên bảng giá không nói lên nhiều. Hãy quy về tình huống cụ thể.

**Nuôi một nhóm tài khoản quy mô nhỏ, 10–50 tài khoản.** Bạn cần IP ổn định, mỗi tài khoản gắn một IP, traffic mỗi phiên không lớn nhưng chạy hàng ngày. Gói 100 IP giá $24 (băng thông không giới hạn) là điểm vào hợp lý, và vì IP không hết hạn, phần bạn chưa dùng vẫn còn nguyên cho tháng sau. So với việc mua theo GB rồi trả $3/GB ở gói nhỏ nhất, đây là lựa chọn rẻ hơn rõ rệt nếu bạn dùng đều.

**Kiểm tra giá và vị trí quảng cáo theo khu vực.** Bạn cần đổi IP liên tục, mỗi lần chỉ tải một trang nhẹ. Ở đây mua theo GB hợp lý hơn: gói 100 GB giá $150 dùng trong 180 ngày, tức khoảng $25 mỗi tháng nếu chia đều, và bạn không phải quản lý danh sách IP.

**Scrape dữ liệu sản phẩm.** Trang thương mại điện tử nặng 2–5MB mỗi trang. 100.000 trang mỗi tháng có thể ngốn vài trăm GB, và nếu trả theo GB ở mức $1–1.5 thì chi phí sẽ vượt xa một gói theo IP. Đây chính là trường hợp mô hình "trả theo IP, băng thông vô hạn" phát huy tác dụng: gói 5.000 IP giá $360, bạn muốn đẩy bao nhiêu dữ liệu qua đó cũng được.

**Bán lại cho khách.** 9Proxy có chương trình dành cho reseller với giá bán buôn, và chính sách IP không hết hạn giúp bạn không bị ép xả hàng tồn. Nếu bạn mua ở mức 25.000 IP ($863) rồi chia nhỏ bán lại, biên lợi nhuận phụ thuộc vào cách bạn định giá chứ không phụ thuộc vào việc giá nhập có tăng hay không — số IP mua trước đợt điều chỉnh vẫn giữ nguyên giá cũ.

## 9Proxy đứng ở đâu trong phân khúc giá rẻ

Theo tổng hợp của Traffic Creator về giá proxy dân cư pay-as-you-go, 9Proxy nằm trong nhóm ngân sách cùng DataImpulse, với mức khoảng $0.70–2/GB, tức khoảng $1.30/GB cho gói nhỏ. Nhóm này phù hợp cho mục tiêu được bảo vệ ở mức trung bình: tỷ lệ thành công 99%+ với mục tiêu dễ, 90–95% với mục tiêu trung bình, và tụt xuống 70–85% với những mục tiêu khó.

Nói cách khác, đây không phải công cụ để đánh vào những hệ thống chống bot khó nhất — phân khúc đó là sân của các nhà cung cấp lớn với pool hàng trăm triệu IP và giá cao hơn nhiều lần. 9Proxy phù hợp khi bạn cần chi phí thấp, dung lượng lớn và chấp nhận retry một phần request lỗi.

Trên các trang so sánh, 9Proxy thường được chấm khoảng 3.9/5 với điểm tin cậy 7.8/10 và tỷ lệ thành công ghi nhận 97%. Đây là dữ liệu tổng hợp từ bên thứ ba, nên xem như tham khảo — cách kiểm tra đáng tin hơn vẫn là chạy thử một batch nhỏ trên chính mục tiêu của bạn rồi đếm tỷ lệ thành công.

Một điểm cần lưu ý về cấu trúc thị trường: nửa thị trường tính theo băng thông, nửa tính theo địa chỉ. Đừng so sánh $0.02/GB của nhà này với $0.024/IP của nhà kia như thể chúng cùng đơn vị. Chúng không cùng đơn vị.

## Cách bắt đầu từ đăng ký tới gắn vào trình duyệt

Quy trình không dài:

1. Tạo tài khoản. Đăng ký qua [👉 link đăng ký 9Proxy kèm mã mời](https://bit.ly/9-Proxy) để mã mời được áp tự động — 9Proxy có chương trình giới thiệu người dùng nên đăng ký qua link mời thường đi kèm ưu đãi áp dụng ngay khi nạp.
2. Chọn mô hình tính tiền. Muốn băng thông không giới hạn thì chọn gói theo IP; muốn xoay IP thoải mái thì chọn gói theo GB. Nếu chưa chắc, gói bundle Starter cho bạn cả hai để thử.
3. Lấy proxy. Vào mục Residential Proxies → GB → Proxy Generator trong dashboard, hoặc dùng Proxy2Web nếu chỉ cần kiểm tra nhanh trên trình duyệt.
4. Chọn định vị. Quốc gia, bang, thành phố, ZIP, hoặc ISP. Chọn sticky nếu cần giữ nguyên IP trong một khoảng thời gian, chọn rotating nếu cần IP mới mỗi request.
5. Chọn cách xác thực. User/pass tiện cho nhiều máy và cho tool chạy trên cloud; whitelist IP thì khỏi cần nhập mật khẩu, nhưng chỉ dùng được khi IP thiết bị của bạn cố định.
6. Gắn vào tool. Proxy dạng host:port:user:pass nên cắm vào anti-detect browser, proxychains hay script Python đều giống nhau. Xuất danh sách dạng .txt hoặc .csv nếu cần nhập hàng loạt.

## Vài điểm cần biết trước khi nạp tiền

- **Hiệu lực dung lượng.** Gói GB thường có hiệu lực 180 ngày, kể cả bundle. Gói Enterprise thì không hết hạn. Nếu bạn làm dự án theo đợt, rải đều trong nửa năm là vừa đủ; còn nếu mua dùng lai rai cả năm, cân nhắc lên Enterprise.
- **IP theo gói IP không hết hạn.** Hệ thống chạy theo số dư nên số IP chưa dùng vẫn còn đó. Đây là lý do việc nạp sớm trước đợt tăng giá có ý nghĩa.
- **Một số phương thức thanh toán có ưu đãi thêm.** Theo ghi nhận của SoftwareSuggest, một số cách thanh toán có thể kèm ưu đãi 5% hoặc cộng thêm 5% sản phẩm. Kiểm tra ở bước thanh toán để chọn cách có lợi nhất.
- **Hỗ trợ.** 9Proxy công bố hỗ trợ người thật 24/7 qua Telegram, email và ticket. Với người dùng Việt Nam, Telegram thường là kênh phản hồi nhanh nhất.
- **Chưa có gói datacenter.** Proxy datacenter đang được ghi là "sắp ra mắt" trên các trang giới thiệu gói. Nếu bạn cần loại đó ngay, đây chưa phải lựa chọn.
- **Đọc điều khoản hoàn tiền trước khi nạp lớn.** Kể cả khi bạn đã quen dùng proxy, việc biết rõ chính sách xử lý khi IP lỗi hoặc khi cần hoàn tiền vẫn nên làm trước, không phải sau.

## Câu hỏi thường gặp

**Proxy dân cư có thay thế được VPN không?** Không hẳn, vì mục đích khác nhau. VPN mã hóa đường truyền của bạn và thường đẩy traffic qua máy chủ datacenter. Proxy dân cư cho bạn xuất hiện như một người dùng bình thường ở một địa điểm cụ thể. Nếu bạn cần ẩn IP để truy cập nội dung, VPN đủ. Nếu bạn cần traffic trông giống người dùng thật ở một thành phố nhất định, proxy dân cư mới là công cụ đúng.

**Nên mua 5 GB hay 100 IP trước?** Nếu bạn định chạy tool treo phiên liên tục, mua theo IP. Nếu bạn chỉ cần kiểm tra vài khu vực vài lần mỗi ngày, mua gói 5 GB giá $15 rồi đo mức tiêu thụ thực tế trước khi nạp gói lớn.

**9Proxy có nhanh không?** Nhanh hơn datacenter là khó, vì bản chất traffic đi qua đường truyền hộ gia đình. Con số tham khảo là độ trễ 50–200ms. Với các tác vụ cần tỷ lệ thành công hơn là tốc độ, đánh đổi này hợp lý.

**Đơn giá $0.018/IP có phải giá bạn phải trả không?** Không. Đó là mức ở gói 500.000 IP. Mua 100 IP thì đơn giá là $0.24. Luôn nhìn cột tổng tiền thay vì cột đơn giá.

Điểm cuối cùng, và cũng là điểm dễ bị bỏ qua: chọn đúng mô hình tính tiền quan trọng hơn chọn nhà cung cấp rẻ nhất. Một người dùng cần băng thông không giới hạn mà mua gói theo GB sẽ trả gấp nhiều lần so với mua gói theo IP, dù cả hai đều là 9Proxy. Xác định trước bạn tiêu tốn nhiều IP hay nhiều dữ liệu, rồi mới chọn gói — [👉 xem các gói proxy dân cư hiện có và giá áp dụng](https://bit.ly/9-Proxy) để đối chiếu với nhu cầu thực tế của mình.

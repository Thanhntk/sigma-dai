---
title: Chú thích
order: 3
---
## Chú thích
Dưới dây là các khái niệm và chỉ số được sử dụng trong các thống kê liên quan.
| Số thứ tự | Tên                                                          | Giải thích                                                   |
| --------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1         | Total ads                                                    | Tổng số lượng ads đã chạy                                    |
| 2         | Session View                                                 | Lượt xem quảng cáo=  số user= 1 User xem quảng cáo →  tính 1 lượt view |
| 3         | Ad Request                                                   | = Tổng số lượng vast Request(= trường hợp gọi, chèn ad thành công(imps) + trường hợp gọi nhưng chèn ad không thành công(fails))<br />Số lượng request gọi lên server |
| 4         | Impression                                                   | (= ad insert)<br />Số lượng ad chèn vào luồng video tới user,<br />Số lần quảng cáo được hiển thị thành công lên màn hình |
| 5         | Complete View                                                | Số lần quảng cáo được hiển thị đến hết thời lượng            |
| 6         | VTR                                                          | = Complete View/ Impression x 100%<br />(Số lần xem hết quảng cáo/ số lần hiển thị thành công) |
| 7         | Avail. Duration                                              | Tổng thời lượng thực tế server ad trả về                     |
| 8         | AdDecisionServer.Duration                                    | Tổng thời lượng thực tế server ad trả về                     |
| 9         | Avail.FilledDuration                                         | Thời lượng thực tế được chèn vào quảng cáo                   |
| 10        | SimpleAdDecisionServer. Fillrate<br />(the simple average)   | The simple averages( Trung bình đơn giản) là tỷ lệ phần trăm tỷ lệ Fillrate cho tổng của tất cả các thời lượng có sẵn<br />= Trung bình cộng các phần tử con [ AdDecisionServer.Duration( thời lượng server ad thực tế trả về) /  Avail.Duration( thời lượng của luồng video có thể chèn quảng cáo) x 100%]<br />**Ví dụ:** Thời lượng của luồng video có thể chèn quảng cáo avail.duration = 15s<br />Thời lượng server thực tế trả về AdDecisionServer.Duration =30s<br />AdDecisionServer. Fillrate= 30/15 100(%)= 200%<br />Thời lượng của luồng video có thể chèn quảng cáo avail.duration = 15s |
| 11        | WeightedAdDecisionServer. Fillrate<br />(The weighted average) | = AdDecisionServer.Duration( Tổng thời lượng server ad thực tế trả về)/ Avail.Duration( Tổng thời lượng của luồng video có thể chèn quảng cáo) x 100%<br />**Ví dụ:**<br />Avail. Duration(second): 3650<br />AdDecisionServer.Duration: 5535<br />WeightedAdDecisionServer. Fillrate= 5535/3650 x 100% |
| 12        | SimpleAvail.FillRate<br />(the simple average)               | = Trung bình cộng các phần tử con [Avail.FilledDuration(thời lượng thực tế được chèn)*100%  /  Avail.Duration( thời lượng của luồng video có thể chèn quảng cáo) ]<br />Kết quả là trung bình cộng tổng thời lượng của nhiều phần tử con bên trong<br />**Ví dụ:** <br />Quảng cáo đầu tiên có thời lượng 90 giây:<br />Tổng thời lượng thực tế server ad trả về- AdDecisionServer.Duration  (50% filled).<br />Thời lượng thực tế được chèn vào quảng cáo-Avail.FilledDuration  45 seconds  (50% filled).<br />Quảng cáo thứ hai có thời lượng 120 giây:<br />Tổng thời lượng thực tế server ad trả về- AdDecisionServer.Duration 120 seconds  (100% filled).<br />Thời lượng thực tế được chèn vào quảng cáo-Avail.FilledDuration  90 seconds (75% filled).<br />**Các số liệu như sau:**<br />AvailDuration là 210, Tổng của hai khoảng thời gian đầy: 90 + 120.<br />AdDecisionServer.Duration: 45 + 120= 165<br />Avail.FilledDuration is 135, Tổng của hai filled durations: 45 + 90.<br />SimpleAvail.FillRate là 62,5%, trung bình của tỷ lệ phần trăm đầy cho mỗi lần sử dụng: (50% + 75%) / 2 |
| 13        | WeightedAvail.FillRate                                       | = Avail.FilledDuration( Tổng thời lượng thực tế được chèn) 100  /  Avail.Duration( Tổng thời lượng của luồng video có thể chèn quảng cáo)<br />WeightedAvail.FillRate: (135100) / 210=64,29% |

Bạn có thể tính mức trung bình theo 2 cách: Simple và weighted như bảng trên, 2 cách tính thể hiện phản hồi từ quảng cáo đến các yêu cầu quảng cáo từ phía SSAI và cách mà SSAI fill vào quảng cáo có sẵn( ad avails).

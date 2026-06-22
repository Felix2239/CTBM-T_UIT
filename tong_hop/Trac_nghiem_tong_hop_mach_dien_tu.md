---
title: "Trắc Nghiệm Tổng Hợp Mạch Điện Tử"
author: "Tổng hợp toàn bộ kiến thức"
lang: "vi"
mainfont: DejaVu Sans
monofont: Noto Sans Mono
mathfont: Latin Modern Math
geometry: margin=1.8cm
fontsize: 11pt
header-includes:
  - \usepackage{amsmath}
  - \usepackage{amssymb}
  - \usepackage{xcolor}
---

# Phần A. Câu hỏi trắc nghiệm

## 1. Kiến thức cơ bản

1. Điện tích được tính theo công thức nào?

   - **A.** $Q = U/R$
   - **\textcolor{red}{B.}** $Q = It$
   - **C.** $Q = Pt$
   - **D.** $Q = UI$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Điện tích bằng dòng điện nhân thời gian: $Q = I t$.

2. Đơn vị của điện dung là:

   - **A.** Henry
   - **B.** Volt
   - **\textcolor{red}{C.}** Farad
   - **D.** Ohm

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Điện dung đo bằng farad, ký hiệu là F.

3. Trong mạch DC xác lập, tụ điện lý tưởng được xem gần đúng là:

   - **A.** Ngắn mạch
   - **\textcolor{red}{B.}** Hở mạch
   - **C.** Nguồn áp
   - **D.** Nguồn dòng

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Ở trạng thái xác lập DC, tụ không cho dòng DC đi qua nên xem như hở mạch.

4. Trong mạch DC xác lập, cuộn cảm lý tưởng được xem gần đúng là:

   - **A.** Hở mạch
   - **\textcolor{red}{B.}** Ngắn mạch
   - **C.** Nguồn dòng
   - **D.** Tụ điện

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Ở trạng thái xác lập DC, cuộn cảm lý tưởng có sụt áp bằng 0 nên gần như ngắn mạch.

5. Công thức định luật Ohm là:

   - **\textcolor{red}{A.}** $U = IR$
   - **B.** $P = UI$
   - **C.** $Q = It$
   - **D.** $I = U + R$

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** Định luật Ohm viết dưới dạng điện áp là $U = IR$.

6. Dung kháng được xác định bởi:

   - **A.** $X_C = 2\pi fC$
   - **\textcolor{red}{B.}** $X_C = 1/(2\pi fC)$
   - **C.** $X_C = R/C$
   - **D.** $X_C = 2\pi RC$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Dung kháng giảm khi tần số hoặc điện dung tăng, theo công thức $1/(2\pi f C)$.

7. Cảm kháng được xác định bởi:

   - **A.** $X_L = 1/(2\pi fL)$
   - **\textcolor{red}{B.}** $X_L = 2\pi fL$
   - **C.** $X_L = L/R$
   - **D.** $X_L = 2\pi RL$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Cảm kháng tăng theo tần số và điện cảm: $X_L = 2\pi fL$.

8. Công suất điện được tính theo:

   - **A.** $P = U/I$
   - **\textcolor{red}{B.}** $P = UI$
   - **C.** $P = I/R$
   - **D.** $P = Q/t^2$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Công suất tức thời cơ bản của mạch điện là $P = UI$.

## 2. Bán dẫn và diode

9. Trong bán dẫn loại N, hạt tải đa số là:

   - **A.** Lỗ trống
   - **B.** Ion âm
   - **\textcolor{red}{C.}** Electron
   - **D.** Photon

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Pha tạp loại N làm electron trở thành hạt tải đa số.

10. Trong diode, cực P được gọi là:

   - **A.** Cathode
   - **\textcolor{red}{B.}** Anode
   - **C.** Drain
   - **D.** Gate

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Cực P của diode gọi là anode, cực N gọi là cathode.

11. Với diode silicon, điện áp ngưỡng xấp xỉ là:

   - **A.** $0.1\,V$
   - **B.** $0.3\,V$
   - **\textcolor{red}{C.}** $0.7\,V$
   - **D.** $1.5\,V$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Diode silicon thường dẫn rõ khi điện áp thuận xấp xỉ 0.7 V.

12. Khi diode phân cực nghịch bình thường:

   - **A.** Dẫn mạnh
   - **\textcolor{red}{B.}** Dòng gần như bằng 0
   - **C.** Điện trở bằng 0
   - **D.** Tăng dòng tuyến tính

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Phân cực nghịch bình thường chỉ còn dòng rò rất nhỏ, gần bằng 0.

13. Mô hình diode lý tưởng xem diode thuận là:

   - **A.** Hở mạch
   - **B.** Biến áp
   - **\textcolor{red}{C.}** Ngắn mạch
   - **D.** Nguồn dòng

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Trong mô hình lý tưởng, diode thuận được xem như khóa đóng hay ngắn mạch.

14. Chức năng nổi bật của diode Zener là:

   - **A.** Khuếch đại dòng
   - **B.** Dao động
   - **\textcolor{red}{C.}** Ổn áp
   - **D.** Cộng điện áp

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Diode Zener làm việc ở vùng đánh thủng nghịch để ổn định điện áp.

15. Trong chỉnh lưu toàn chu kỳ, tần số gợn sóng đầu ra bằng:

   - **A.** $f$
   - **B.** $\dfrac{f}{2}$
   - **\textcolor{red}{C.}** $2f$
   - **D.** $4f$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Chỉnh lưu toàn chu kỳ biến cả hai bán kỳ thành cùng cực tính nên tần số gợn là $2f$.

16. Tụ lọc trong mạch chỉnh lưu có tác dụng chính là:

   - **A.** Tăng tần số nguồn
   - **\textcolor{red}{B.}** Giảm độ nhấp nhô điện áp
   - **C.** Đảo pha điện áp
   - **D.** Làm điện áp ra âm

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Tụ lọc nạp ở đỉnh và xả qua tải để làm điện áp ra mịn hơn.

17. PIV của diode là:

   - **A.** Dòng thuận cực đại
   - **B.** Công suất dẫn cực đại
   - **\textcolor{red}{C.}** Điện áp ngược cực đại phải chịu
   - **D.** Điện áp ngưỡng khi dẫn

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** PIV là điện áp ngược cực đại mà diode phải chịu được mà không hỏng.

18. Với chỉnh lưu bán kỳ có tụ lọc, gần đúng:

   - **A.** $V_{r(pp)}$ tăng khi $C$ tăng
   - **\textcolor{red}{B.}** $V_{r(pp)}$ giảm khi $C$ tăng
   - **C.** $V_{r(pp)}$ không phụ thuộc tải
   - **D.** $V_{r(pp)}$ luôn bằng 0

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Độ gợn giảm khi tụ lớn hơn vì tụ xả chậm hơn giữa hai lần nạp.

## 3. BJT

19. BJT có ba cực:

   - **A.** Anode, Cathode, Gate
   - **B.** Drain, Gate, Source
   - **\textcolor{red}{C.}** Emitter, Base, Collector
   - **D.** Input, Output, Ground

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** BJT gồm ba cực emitter, base và collector.

20. Trong vùng active của BJT:

   - **A.** $I_C = 0$
   - **\textcolor{red}{B.}** $I_C = \beta I_B$
   - **C.** $V_{BE} = 0$
   - **D.** $V_{CE} = 0$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Trong vùng active, BJT tuân gần đúng quan hệ $I_C = \beta I_B$.

21. Quan hệ đúng là:

   - **A.** $I_B = I_C + I_E$
   - **B.** $I_C = I_B + I_E$
   - **\textcolor{red}{C.}** $I_E = I_B + I_C$
   - **D.** $I_E = I_B - I_C$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Dòng emitter bằng tổng dòng base và collector: $I_E = I_B + I_C$.

22. Khi transistor bão hòa:

   - **A.** $I_C$ luôn bằng $\beta I_B$
   - **\textcolor{red}{B.}** $V_{CE}$ rất nhỏ
   - **C.** $V_{BE} < 0$
   - **D.** transistor ngắt

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Khi bão hòa, transistor có $V_{CE}$ rất nhỏ, thường cỡ vài phần mười volt.

23. Điểm Q của transistor là:

   - **A.** Điểm gãy trên đặc tuyến diode
   - **\textcolor{red}{B.}** Điểm làm việc DC
   - **C.** Điểm cộng hưởng
   - **D.** Điểm ngắn mạch

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Điểm Q là điểm làm việc tĩnh DC, dùng để phân tích tín hiệu nhỏ quanh nó.

24. Mạch khuếch đại CE có đặc điểm:

   - **A.** Không đảo pha, $A_v \approx 1$
   - **\textcolor{red}{B.}** Đảo pha 180 độ, khuếch đại áp lớn
   - **C.** Trở vào rất nhỏ, không khuếch đại dòng
   - **D.** Chỉ dùng cho dao động

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Mạch CE cho độ lợi áp lớn và đầu ra đảo pha 180 độ.

25. Mạch khuếch đại CC có đặc điểm nổi bật:

   - **A.** $A_v$ rất lớn âm
   - **B.** Trở vào nhỏ
   - **\textcolor{red}{C.}** $A_v$ gần bằng 1
   - **D.** Không khuếch đại dòng

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Mạch CC hay emitter follower có độ lợi áp gần 1 và đệm tải tốt.

26. Mạch CB có đặc điểm:

   - **A.** $A_i$ rất lớn hơn nhiều 1
   - **\textcolor{red}{B.}** Trở vào rất nhỏ
   - **C.** $A_v$ luôn bằng 1
   - **D.** Luôn đảo pha 180 độ

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Mạch CB có trở vào nhỏ vì tín hiệu đi vào phía emitter.

27. Công thức gần đúng của điện trở emitter vi sai là:

   - **\textcolor{red}{A.}** $r'_e \approx \dfrac{25\,mV}{I_E}$
   - **B.** $r'_e \approx \dfrac{I_E}{25\,mV}$
   - **C.** $r'_e = \beta /I_C$
   - **D.** $r'_e = V_{CC}/I_B$

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** Điện trở vi sai emitter gần đúng là r_e' xap xi 25mV/I_E.

28. Phân cực cầu chia áp BJT thường ổn định hơn phân cực cố định vì:

   - **A.** Không cần điện trở
   - **\textcolor{red}{B.}** Ít phụ thuộc beta hơn
   - **C.** Không cần nguồn DC
   - **D.** Làm $V_{BE} = 0$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Mạch phân cực cầu chia áp bớt phụ thuộc vào biến thiên beta nên ổn định hơn.

29. Với CE có tụ bypass emitter đủ lớn, tác dụng chính là:

   - **A.** Giảm gain AC
   - **\textcolor{red}{B.}** Tăng gain AC
   - **C.** Ngắt hoàn toàn tín hiệu AC
   - **D.** Làm $I_C = 0$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Tụ bypass làm emitter gần như nối mass theo AC, nên độ lợi tăng.

30. Tụ coupling có tác dụng:

   - **A.** Cho DC qua, chặn AC
   - **\textcolor{red}{B.}** Chặn DC, cho AC qua
   - **C.** Chỉ tạo cộng hưởng
   - **D.** Chỉ dùng cho nguồn

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Tụ coupling chặn thành phần DC và truyền thành phần AC giữa các tầng.

## 4. FET

31. JFET là linh kiện:

   - **A.** Điều khiển bằng dòng
   - **\textcolor{red}{B.}** Điều khiển bằng điện áp
   - **C.** Điều khiển bằng công suất
   - **D.** Không điều khiển được

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** JFET điều khiển bằng điện áp đặt ở cổng gate.

32. Trong JFET, dòng vào cổng gate lý tưởng là:

   - **A.** Rất lớn
   - **B.** Bằng dòng drain
   - **\textcolor{red}{C.}** Gần bằng 0
   - **D.** Luôn âm

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Gate của JFET phân cực nghịch nên dòng cổng lý tưởng gần bằng 0.

33. Phương trình Shockley của JFET là:

   - **A.** $I_D = \beta I_B$
   - **\textcolor{red}{B.}** $I_D = I_{DSS}(1 - V_{GS}/V_P)^2$
   - **C.** $I_D = V/R$
   - **D.** $I_D = C.dv/dt$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Phương trình Shockley mô tả quan hệ $I_D$ và $V_{GS}$ của JFET.

34. Cấu hình khuếch đại CS của FET tương tự với cấu hình nào của BJT?

   - **\textcolor{red}{A.}** CE
   - **B.** CC
   - **C.** CB
   - **D.** Darlington

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** Mạch CS của FET tương tự mạch CE của BJT vì đều cho độ lợi áp lớn và đảo pha.

35. MOSFET khác JFET ở điểm nổi bật là:

   - **\textcolor{red}{A.}** Gate của MOSFET được cách điện bởi oxide
   - **B.** MOSFET không có cực source
   - **C.** JFET không có dòng drain
   - **D.** MOSFET luôn là loại PNP

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** MOSFET có cổng cách điện bởi lớp oxide nên trở vào rất lớn.

36. Với E-MOSFET kênh N, transistor bắt đầu dẫn khi:

   - **A.** $V_{GS} < 0$
   - **B.** $V_{GS} = 0$ luôn dẫn mạnh
   - **\textcolor{red}{C.}** $V_{GS} > V_{TH}$
   - **D.** $V_{DS} = 0$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** E-MOSFET kênh N chỉ dẫn khi điện áp cổng-nguồn vượt ngưỡng $V_{TH}$.

37. Công thức dòng trong miền bão hòa của E-MOSFET kênh N là:

   - **\textcolor{red}{A.}** $I_D = K(V_{GS} - V_{TH})^2$
   - **B.** $I_D = \beta I_B$
   - **C.** $I_D = V_{DS}/R_D$
   - **D.** $I_D = I_{DSS}(1 - V_{GS}/V_P)^2$

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** Ở miền bão hòa của E-MOSFET, dòng thường dùng công thức bình phương theo $V_{GS}-V_{TH}$.

38. Điều kiện miền bão hòa của E-MOSFET kênh N là:

   - **A.** $V_{DS} < V_{GS} - V_{TH}$
   - **B.** $V_{DS} = 0$
   - **\textcolor{red}{C.}** $V_{DS} \ge  V_{GS} - V_{TH}$
   - **D.** $V_{GS} < 0$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Điều kiện bão hòa của E-MOSFET kênh N là $V_{DS} \ge V_{GS}-V_{TH}$.

39. Với JFET tự phân cực, thường có:

   - **\textcolor{red}{A.}** $V_G \approx 0$ và $V_{GS} < 0$
   - **B.** $V_{GS} > 0$
   - **C.** $I_G = I_D$
   - **D.** $V_{DS} = 0$

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** JFET tự phân cực thường có gate gần mass và source dương hơn gate nên $V_{GS}<0$.

40. Độ dẫn truyền nhỏ tín hiệu của JFET/MOSFET được ký hiệu là:

   - **A.** $\beta$
   - **\textcolor{red}{B.}** $g_m$
   - **C.** $r_e$
   - **D.** $A_0$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Độ dẫn truyền nhỏ tín hiệu của transistor trường ký hiệu là $g_m$.

## 5. Op-Amp

41. Op-Amp lý tưởng có:

   - **A.** Trở vào nhỏ, trở ra lớn
   - **\textcolor{red}{B.}** Trở vào lớn, trở ra nhỏ
   - **C.** Trở vào và trở ra đều nhỏ
   - **D.** Trở vào và trở ra đều lớn

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Op-amp lý tưởng có trở vào rất lớn và trở ra rất nhỏ.

42. Trong chế độ tuyến tính có hồi tiếp âm:

   - **A.** $V_+ = 0$
   - **B.** $V_- = 0$
   - **\textcolor{red}{C.}** $V_+ \approx V_-$
   - **D.** $V_{out} = 0$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Có hồi tiếp âm và làm việc tuyến tính thì hai đầu vào gần bằng nhau: $V_+ \approx V_-$.

43. Hệ số khuếch đại của mạch đảo là:

   - **A.** $A_v = R_f/R_{in}$
   - **\textcolor{red}{B.}** $A_v = -R_f/R_{in}$
   - **C.** $A_v = 1 + R_f/R_{in}$
   - **D.** $A_v = 0$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Mạch đảo có hệ số khuếch đại $A_v = -\dfrac{R_f}{R_{in}}$.

44. Hệ số khuếch đại của mạch không đảo là:

   - **A.** $A_v = -R_f/R_1$
   - **\textcolor{red}{B.}** $A_v = 1 + R_f/R_1$
   - **C.** $A_v = R_1/R_f$
   - **D.** $A_v = -1$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Mạch không đảo có hệ số khuếch đại $A_v = 1 + \dfrac{R_f}{R_1}$.

45. Mạch theo áp có hệ số khuếch đại gần:

   - **A.** 0
   - **\textcolor{red}{B.}** 1
   - **C.** 10
   - **D.** vô cùng

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Mạch theo áp hay voltage follower có độ lợi gần bằng 1.

46. CMRR thể hiện khả năng:

   - **A.** Khuếch đại tín hiệu đồng pha
   - **\textcolor{red}{B.}** Triệt tín hiệu đồng pha
   - **C.** Tăng dòng bias
   - **D.** Ổn áp nguồn

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** CMRR càng lớn thì op-amp càng triệt tốt tín hiệu đồng pha.

47. Mạch so sánh dùng op-amp thường làm việc ở:

   - **A.** Vùng tuyến tính hẹp
   - **\textcolor{red}{B.}** Vùng bão hòa đầu ra
   - **C.** Vùng ngắt hoàn toàn
   - **D.** Chỉ miền common mode

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Comparator thường bị đẩy vào bão hòa để cho ra mức cao hoặc thấp rõ ràng.

48. Mạch cộng đảo có đầu ra là:

   - **\textcolor{red}{A.}** Tổng đại số có dấu âm của các đầu vào
   - **B.** Hiệu của hai đầu vào
   - **C.** Tích phân của đầu vào
   - **D.** Đạo hàm của đầu vào

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** Mạch cộng đảo cho tổng có trọng số và có dấu âm ở đầu ra.

49. Mạch tích phân op-amp có đầu ra tỉ lệ với:

   - **A.** Đạo hàm của đầu vào
   - **\textcolor{red}{B.}** Tích phân của đầu vào
   - **C.** Bình phương đầu vào
   - **D.** Căn bậc hai đầu vào

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Mạch tích phân tạo đầu ra tỉ lệ với tích phân theo thời gian của tín hiệu vào.

50. Mạch vi phân op-amp có đầu ra tỉ lệ với:

   - **A.** Tích phân của đầu vào
   - **B.** Trung bình của đầu vào
   - **\textcolor{red}{C.}** Đạo hàm của đầu vào
   - **D.** Giá trị hiệu dụng

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Mạch vi phân cho đầu ra tỉ lệ với đạo hàm của tín hiệu vào.

51. Trong mạch đảo lý tưởng, nút vào chân $-$ thường được gọi là:

   - **A.** Mass thật
   - **\textcolor{red}{B.}** Mass ảo
   - **C.** Điểm bão hòa
   - **D.** Điểm Q

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Do $V_- \approx V_+ = 0$ nên nút đó được gọi là mass ảo.

52. Schmitt trigger dùng:

   - **A.** Hồi tiếp âm
   - **\textcolor{red}{B.}** Hồi tiếp dương
   - **C.** Không có hồi tiếp
   - **D.** Chỉ điện trở thuần

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Schmitt trigger dùng hồi tiếp dương để tạo hai ngưỡng chuyển mạch.

53. Comparator khác mạch khuếch đại tuyến tính ở chỗ:

   - **A.** luôn cần tụ ghép
   - **\textcolor{red}{B.}** thường làm việc trong bão hòa
   - **C.** không dùng nguồn đối xứng
   - **D.** không có đầu ra

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Comparator được dùng như mạch quyết định mức nên thường làm việc trong bão hòa.

## 6. Dao động

54. Điều kiện Barkhausen để dao động ổn định là:

   - **A.** $|A\beta | = 0$
   - **\textcolor{red}{B.}** $|A\beta | = 1$
   - **C.** $|A\beta | > 10$
   - **D.** $\beta  = 0$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Dao động ổn định theo Barkhausen cần $|A\beta| = 1$.

55. Điều kiện khởi động thực tế của mạch dao động là:

   - **A.** $|A\beta | < 1$
   - **B.** $|A\beta | = 0$
   - **\textcolor{red}{C.}** $|A\beta | > 1$
   - **D.** $A = 0$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Để khởi động, biên độ vòng phải lớn hơn 1 một chút: $|A\beta| > 1$.

56. Điều kiện pha của mạch dao động tự duy trì là:

   - **A.** Tổng lệch pha bằng `90°`
   - **B.** Tổng lệch pha bằng `180°`
   - **\textcolor{red}{C.}** Tổng lệch pha bằng `0°` hoặc `360°`
   - **D.** Không cần điều kiện pha

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Tổng lệch pha vòng kín phải bằng 0 hoặc 360 độ để hồi tiếp là dương.

57. Mạch cầu Wien thường dùng để tạo:

   - **A.** Xung vuông công suất lớn
   - **\textcolor{red}{B.}** Sóng sin tần số thấp
   - **C.** Dòng DC ổn định
   - **D.** Xung kim

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Cầu Wien thường dùng tạo sóng sin tần số thấp và trung bình.

58. Với cầu Wien đối xứng, tần số dao động là:

   - **A.** $f_0 = 2\pi RC$
   - **\textcolor{red}{B.}** $f_0 = 1/(2\pi RC)$
   - **C.** $f_0 = R/(2\pi C)$
   - **D.** $f_0 = C/(2\pi R)$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Với phần tử đối xứng, tần số dao động Wien là $f_0 = \dfrac{1}{2\pi RC}$.

59. Tại tần số dao động của cầu Wien, mạng hồi tiếp có độ suy hao xấp xỉ:

   - **A.** `1`
   - **B.** $\dfrac{1}{2}$
   - **\textcolor{red}{C.}** $\dfrac{1}{3}$
   - **D.** $\dfrac{1}{10}$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Mạng RC của cầu Wien suy hao khoảng 1/3 tại tần số dao động.

60. Do đó bộ khuếch đại trong cầu Wien cần có độ lợi xấp xỉ:

   - **A.** `1`
   - **B.** `2`
   - **\textcolor{red}{C.}** `3`
   - **D.** `10`

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Nếu $\beta \approx \dfrac{1}{3}$ thì cần $A \approx 3$ để có $A\beta \approx 1$.

## 7. Đáp ứng tần số và Bode

61. Đáp ứng tần số của một hệ liên tục được xác định bằng cách thay:

   - **A.** $s = 0$
   - **B.** $s = 1$
   - **\textcolor{red}{C.}** $s = jω$
   - **D.** $s = -j\omega$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Đáp ứng tần số của hệ liên tục lấy trên trục ảo bằng cách thay $s = j\omega$.

62. Trong $H(jω)$, đại lượng $|H(jω)|$ biểu diễn:

   - **A.** Chỉ pha
   - **\textcolor{red}{B.}** Độ lợi biên độ theo tần số
   - **C.** Năng lượng nguồn
   - **D.** Điện trở tải

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** $|H(j\omega)|$ cho biết mức khuếch đại hoặc suy giảm biên độ theo tần số.

63. Pha của đáp ứng tần số được xác định bởi:

   - **\textcolor{red}{A.}** $arg H(jω)$
   - **B.** $|H(jω)|$
   - **C.** $1/H(jω)$
   - **D.** $dH/dt$

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** Pha của đáp ứng tần số là góc của số phức $H(j\omega)$, tức $rg H(j\omega)$.

64. Độ lợi theo dB được tính bởi:

   - **A.** $10log10(Vout/Vin)$
   - **\textcolor{red}{B.}** $20log10(Vout/Vin)$
   - **C.** $ln(Vout/Vin)$
   - **D.** $Vout - Vin$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Độ lợi điện áp theo dB được tính bằng $20\log_{10}(V_{out}/V_{in})$.

65. Tại tần số cắt của lọc bậc một, biên độ gần bằng:

   - **A.** `1`
   - **B.** $\dfrac{1}{2}$
   - **\textcolor{red}{C.}** $\dfrac{1}{\sqrt{2}}$
   - **D.** `2`

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Tại $f_c$ của lọc bậc một, biên độ còn $1/\sqrt{2}$ lần giá trị dải thông.

66. Tương ứng theo dB, mức đó xấp xỉ:

   - **A.** $-1 dB$
   - **\textcolor{red}{B.}** $-3 dB$
   - **C.** $-6 dB$
   - **D.** $+3 dB$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** $20\log_{10}\left(\dfrac{1}{\sqrt{2}}\right) \approx -3\,dB$.

67. Pole của hàm truyền là:

   - **A.** Nghiệm của tử số
   - **\textcolor{red}{B.}** Nghiệm của mẫu số
   - **C.** Tần số nguồn cấp
   - **D.** Điện áp ngưỡng

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Pole là nghiệm làm mẫu số của hàm truyền bằng 0.

68. Mỗi pole bậc một đóng góp xấp xỉ:

   - **A.** $-10 dB/dec$
   - **\textcolor{red}{B.}** $-20 dB/dec$
   - **C.** $-30 dB/dec$
   - **D.** $-40 dB/dec$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Mỗi pole bậc một tạo thêm độ dốc xấp xỉ $-20\,dB/dec$.

69. Bộ lọc bậc hai có roll-off xấp xỉ:

   - **A.** $-20 dB/dec$
   - **B.** $-30 dB/dec$
   - **\textcolor{red}{C.}** $-40 dB/dec$
   - **D.** $-60 dB/dec$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Bộ lọc bậc hai có hai pole nên suy giảm xấp xỉ $-40\,dB/dec$.

70. $Roll-off$ là:

   - **A.** Tần số trung tâm
   - **\textcolor{red}{B.}** Độ dốc suy giảm của đáp ứng biên độ
   - **C.** Độ lợi DC
   - **D.** Độ lệch pha nguồn

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Roll-off là độ dốc suy giảm của đồ thị biên độ theo tần số.

## 8. Mạch lọc thụ động và tích cực

71. Tần số cắt của mạch RC bậc một là:

   - **A.** $f_c = 2\pi RC$
   - **\textcolor{red}{B.}** $f_c = 1/(2\pi RC)$
   - **C.** $f_c = R/(2\pi C)$
   - **D.** $f_c = C/(2\pi R)$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Mạch RC bậc một có tần số cắt $f_c = \dfrac{1}{2\pi RC}$.

72. Bộ lọc thông thấp cho qua tốt:

   - **A.** Tần số cao
   - **\textcolor{red}{B.}** Tần số thấp
   - **C.** Chỉ một tần số duy nhất
   - **D.** Không cho tín hiệu nào qua

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Thông thấp cho thành phần tần số thấp đi qua tốt hơn tần số cao.

73. Bộ lọc thông cao cho qua tốt:

   - **A.** Tần số thấp
   - **\textcolor{red}{B.}** Tần số cao
   - **C.** Chỉ DC
   - **D.** Chỉ một tần số

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Thông cao chặn thấp tần và cho cao tần đi qua tốt hơn.

74. Băng thông của bộ lọc thông dải là:

   - **A.** $BW = f_L + f_H$
   - **\textcolor{red}{B.}** $BW = f_H - f_L$
   - **C.** $BW = f_L/f_H$
   - **D.** $BW = f_0^2$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Băng thông của thông dải bằng khoảng cách giữa hai tần số cắt: $BW=f_H-f_L$.

75. Tần số trung tâm của thông dải là:

   - **A.** $f_0 = f_H - f_L$
   - **\textcolor{red}{B.}** $f_0 = \sqrt{f_L f_H}$
   - **C.** $f_0 = f_L + f_H$
   - **D.** $f_0 = \dfrac{1}{f_L f_H}$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Tần số trung tâm của thông dải lấy theo trung bình nhân: $f_0 = \sqrt{f_L f_H}$.

76. Hệ số chất lượng của thông dải là:

   - **A.** $Q = BW/f_0$
   - **\textcolor{red}{B.}** $Q = f_0/BW$
   - **C.** $Q = f_L/f_H$
   - **D.** $Q = R/C$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Hệ số chất lượng của thông dải là $Q = \dfrac{f_0}{BW}$.

77. Bộ lọc Sallen-Key bậc hai có độ dốc xấp xỉ:

   - **A.** $20 dB/dec$
   - **B.** $30 dB/dec$
   - **\textcolor{red}{C.}** $40 dB/dec$
   - **D.** $80 dB/dec$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Sallen-Key bậc hai có hai pole nên độ dốc xấp xỉ 40 dB/dec.

78. Butterworth là đáp ứng:

   - **A.** Có gợn mạnh trong băng thông
   - **\textcolor{red}{B.}** Phẳng trong băng thông
   - **C.** Chỉ dùng cho mạch số
   - **D.** Không phụ thuộc linh kiện

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Butterworth nổi bật ở đáp ứng biên độ phẳng trong dải thông.

79. Lọc tích cực khác lọc thụ động ở điểm nổi bật:

   - **A.** Không dùng $R$, $C$
   - **\textcolor{red}{B.}** Có thể khuếch đại và cách ly tải nhờ op-amp
   - **C.** Luôn cần cuộn cảm lớn
   - **D.** Không có tần số cắt

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Lọc tích cực dùng op-amp nên có thể khuếch đại và giảm ảnh hưởng tải.

80. Trong mạch lọc tích cực, mạng `RC` chủ yếu quyết định:

   - **A.** Màu dây dẫn
   - **\textcolor{red}{B.}** Miền tần số được chọn
   - **C.** Điện áp nguồn nuôi
   - **D.** Dòng bias đầu vào

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Mạng RC quyết định miền tần số được chọn, còn op-amp chủ yếu khuếch đại và cách ly.

## 9. Bổ sung từ đề thi

81. Với mạch đa hài dùng hai transistor $Q1$, $Q2$, nguyên tắc hoạt động là:

   - **\textcolor{red}{A.}** $Q1$ tắt thì $Q2$ bão hòa và ngược lại
   - **B.** $Q1$ tắt thì $Q2$ tuyến tính và ngược lại
   - **C.** $Q1$, $Q2$ luôn cùng bão hòa
   - **D.** $Q1$, $Q2$ luôn cùng tuyến tính

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** Đa hài phi ổn dùng hai transistor đóng ngắt luân phiên; một bên bão hòa thì bên kia tắt.

82. Muốn tăng độ dốc `roll-off` của mạch lọc thì:

   - **A.** Chỉ thay đổi giá trị $R$, $C$
   - **B.** Chỉ tăng điện trở hồi tiếp
   - **\textcolor{red}{C.}** Tăng bậc lọc và ghép nhiều tầng nối tiếp
   - **D.** Mắc nhiều mạch lọc song song

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Độ dốc phụ thuộc số pole hay bậc của lọc; ghép tầng nối tiếp làm tăng bậc và tăng độ dốc.

83. Với mạch lọc thông dải, băng thông `BW` được tính bởi:

   - **A.** $BW = f_{c1} + f_{c2}$
   - **B.** $BW = \sqrt{f_{c1}f_{c2}}$
   - **\textcolor{red}{C.}** $BW = f_{c2} - f_{c1}$
   - **D.** $BW = \sqrt{f_{c2}/f_{c1}}$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Băng thông là khoảng cách giữa tần số cắt trên và dưới: $BW = f_H - f_L$.

84. Mạch dùng op-amp cộng đảo với các điện trở trọng số nhận các bit số vào là:

   - **A.** ADC 4 bit
   - **\textcolor{red}{B.}** DAC 4 bit
   - **C.** Khuếch đại không đảo
   - **D.** Mạch tích phân

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Các bit số qua điện trở trọng số cộng về op-amp tạo điện áp analog ra, nên đó là DAC.

85. Lý do chính dùng hồi tiếp âm trong op-amp là:

   - **A.** Để tạo dao động
   - **\textcolor{red}{B.}** Để mạch làm việc tuyến tính và ổn định hơn
   - **C.** Để tăng vô hạn độ lợi vòng hở
   - **D.** Để làm ngõ vào hút dòng lớn

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Hồi tiếp âm ép op-amp làm việc gần vùng tuyến tính, giảm sai số và tăng ổn định.

86. Một mạch lọc tích cực thông cao bậc hai thường có `roll-off` xấp xỉ:

   - **A.** $-20 dB/dec$
   - **B.** $0 dB/dec$
   - **C.** $-60 dB/dec$
   - **\textcolor{red}{D.}** $-40 dB/dec$

   **Đáp án đúng:** **\textcolor{red}{D}**
   **Giải thích:** Lọc bậc hai có hai pole nên độ dốc biên độ xấp xỉ $40\,dB/dec$.

87. Trong ngữ cảnh mạch lọc, thuật ngữ `pole` gần nhất với:

   - **A.** Độ lợi của op-amp
   - **\textcolor{red}{B.}** Số cực hay số khâu RC độc lập quyết định bậc lọc
   - **C.** Độ rộng băng thông khi ghép song song
   - **D.** Điện áp nguồn của mạch

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Pole là cực của hàm truyền; trong các mạch RC cơ bản, số pole gắn với số khâu RC độc lập và bậc lọc.

88. Mạch ổn áp Zener có $V_Z = 20\,V$, $R = 20\Omega$, $R_L = 200\Omega$, $V_{in} = 30\,V$. Nếu Zener còn làm việc đúng vùng ổn áp thì điện áp ra gần bằng:

   - **\textcolor{red}{A.}** $20\,V$
   - **B.** $30\,V$
   - **C.** $10\,V$
   - **D.** $400\,V$

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** Khi Zener còn trong vùng ổn áp, điện áp trên tải gần bằng điện áp Zener: $V_o \approx V_Z = 20\,V$.

89. Với JFET, việc đóng mở kênh dẫn dựa trên:

   - **A.** Phân cực thuận chuyển tiếp `pn`
   - **\textcolor{red}{B.}** Phân cực nghịch chuyển tiếp `pn`
   - **C.** Cấu trúc oxide cách điện như MOSFET tăng cường
   - **D.** Dòng cổng rất lớn

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** JFET điều khiển bề rộng kênh bằng vùng nghèo do phân cực nghịch ở mối nối gate-channel.

90. Với một hệ khuếch đại nhiều tầng, độ lợi điện áp toàn mạch được tính bởi:

   - **A.** $A_V = V_{o1} \times V_{o2}$
   - **B.** $A_V = V_{o1} \times V_{o2} \times V_{in}$
   - **\textcolor{red}{C.}** $A_V = V_{out}/V_{in}$
   - **D.** $A_V = V_{in}/V_{out}$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Độ lợi điện áp luôn là tỉ số điện áp ra trên điện áp vào; với nhiều tầng thì cũng bằng tích các gain từng tầng.

## 10. Câu tương tự đề thi

91. Trong mạch đa hài transistor, tại một thời điểm ổn định tức thời thường có:

   - **A.** Hai transistor cùng hoạt động tuyến tính
   - **\textcolor{red}{B.}** Một transistor bão hòa, transistor kia ngắt
   - **C.** Hai transistor cùng ngắt
   - **D.** Hai transistor cùng bão hòa

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Trạng thái của đa hài là xen kẽ: một nhánh dẫn mạnh, nhánh còn lại tắt.

92. Nếu ghép nối tiếp hai mạch lọc bậc một giống nhau thì độ dốc vùng chặn gần đúng là:

   - **A.** $-10 dB/dec$
   - **B.** $-20 dB/dec$
   - **\textcolor{red}{C.}** $-40 dB/dec$
   - **D.** $-80 dB/dec$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Hai tầng bậc một tạo thành bậc hai, nên tổng độ dốc gần bằng $-40\,dB/dec$.

93. Nếu bộ lọc thông dải có $f_L = 2\,kHz$ và $f_H = 6\,kHz$ thì băng thông là:

   - **A.** `2 kHz`
   - **\textcolor{red}{B.}** `4 kHz`
   - **C.** `8 kHz`
   - **D.** `12 kHz`

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** $BW = f_H - f_L = 6 - 2 = 4\,kHz$.

94. Tác dụng quan trọng khác của hồi tiếp âm ngoài việc tuyến tính hóa là:

   - **A.** Làm mạch tự dao động dễ hơn
   - **B.** Tăng vô hạn $A_{OL}$
   - **\textcolor{red}{C.}** Giảm phụ thuộc vào độ lợi vòng hở và tăng ổn định
   - **D.** Ép dòng ngõ vào lớn hơn

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Hồi tiếp âm làm gain kín mạch ít nhạy với biến thiên tham số bên trong op-amp.

95. Với op-amp thực tế tốt, đặc điểm gần đúng đúng là:

   - **\textcolor{red}{A.}** Trở vào lớn, trở ra nhỏ
   - **B.** Trở vào nhỏ, trở ra lớn
   - **C.** Trở vào bằng 0, trở ra vô cực
   - **D.** Trở vào và trở ra đều rất lớn

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** Op-amp thực tế không lý tưởng tuyệt đối nhưng vẫn được thiết kế để trở vào lớn và trở ra nhỏ.

96. Một transistor có $I_C = 1.8\,mA$ và $\beta = 90$. Dòng base gần đúng là:

   - **A.** $200 \mu A$
   - **\textcolor{red}{B.}** $20 \mu A$
   - **C.** `2 mA`
   - **D.** $0.2 \mu A$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** $I_B = I_C/\beta = 1.8\,mA/90 = 0.02\,mA = 20\,\mu A$.

97. Diode được phân cực thuận khi:

   - **A.** Cực dương nối vào `N`, cực âm nối vào `P`
   - **\textcolor{red}{B.}** Cực dương nối vào `P`, cực âm nối vào `N`
   - **C.** Hai cực cùng nối đất
   - **D.** Điện áp ngoài bằng 0

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Phân cực thuận nghĩa là nguồn ngoài làm hạ rào thế, nên cực dương đặt vào anode/P và cực âm vào cathode/N.

98. Với lọc Butterworth bậc hai dạng đề thi, nếu tra bảng được $R_1/R_2 = 0.586$ và $R_2 = 2.7\,k\Omega$ thì $R_1$ gần đúng là:

   - **\textcolor{red}{A.}** $1.58\,k\Omega$
   - **B.** $2.7\,k\Omega$
   - **C.** $4.61\,k\Omega$
   - **D.** $9.21\,k\Omega$

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** $R_1 = 0.586R_2 = 0.586 \times 2.7 \approx 1.58\,k\Omega$.

## 11. Luyện nâng cao

99. Mạch chỉnh lưu bán kỳ có tụ lọc, nếu dòng tải tăng gấp đôi còn các đại lượng khác giữ nguyên thì gần đúng độ gợn $V_{r(pp)}$ sẽ:

   - **A.** Giảm một nửa
   - **\textcolor{red}{B.}** Tăng gấp đôi
   - **C.** Không đổi
   - **D.** Tăng gấp bốn

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Với gần đúng $V_{r(pp)} \approx I_L/(fC)$, khi $I_L$ tăng gấp đôi thì gợn tăng gấp đôi.

100. Với chỉnh lưu toàn kỳ dùng tụ lọc, nếu tần số lưới tăng từ $50\,Hz$ lên $100\,Hz$ thì độ gợn gần đúng sẽ:

   - **\textcolor{red}{A.}** Giảm một nửa
   - **B.** Tăng gấp đôi
   - **C.** Không đổi
   - **D.** Giảm bốn lần

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** Gợn tỉ lệ nghịch với tần số nạp lại tụ; toàn kỳ có $f_r = 2f$, nên tăng $f$ gấp đôi làm gợn giảm một nửa.

101. Diode Zener có $V_Z = 12\,V$, $P_{Zmax} = 600\,mW$. Dòng Zener cực đại gần đúng là:

   - **A.** $12\,mA$
   - **B.** $24\,mA$
   - **C.** $36\,mA$
   - **\textcolor{red}{D.}** $50\,mA$

   **Đáp án đúng:** **\textcolor{red}{D}**
   **Giải thích:** $I_{Zmax} = P_{Zmax}/V_Z = 0.6/12 = 0.05\,A = 50\,mA$.

102. Mạch ổn áp Zener có $V_{in} = 18\,V$, $V_Z = 6\,V$, $R = 240\,\Omega$, bỏ qua tải. Dòng qua Zener gần đúng là:

   - **A.** $10\,mA$
   - **B.** $20\,mA$
   - **\textcolor{red}{C.}** $50\,mA$
   - **D.** $75\,mA$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Không tải nên toàn bộ dòng qua điện trở đi qua Zener: $I_Z = (18-6)/240 = 0.05\,A$.

103. Trong mạch diode lý tưởng nối tiếp với điện trở tải, khi diode bị phân cực nghịch thì điện áp trên tải gần đúng bằng:

   - **\textcolor{red}{A.}** $0\,V$
   - **B.** Điện áp nguồn
   - **C.** Điện áp ngưỡng diode
   - **D.** Vô hạn

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** Diode nghịch lý tưởng tương đương hở mạch nên dòng bằng 0, vì vậy sụt áp trên điện trở tải bằng 0.

104. Với mạch chỉnh lưu cầu, số diode dẫn trong mỗi nửa chu kỳ là:

   - **A.** 1
   - **\textcolor{red}{B.}** 2
   - **C.** 3
   - **D.** 4

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Trong cầu chỉnh lưu, luôn có hai diode dẫn để tạo cùng cực tính trên tải trong mỗi bán kỳ.

105. Transistor BJT có $\beta = 100$ và $I_B = 30\,\mu A$. Nếu đang ở vùng active thì $I_C$ gần đúng bằng:

   - **A.** $0.3\,mA$
   - **B.** $1.5\,mA$
   - **\textcolor{red}{C.}** $3\,mA$
   - **D.** $30\,mA$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Trong vùng active, $I_C \approx \beta I_B = 100 \times 30\,\mu A = 3\,mA$.

106. Một BJT có $I_C = 2\,mA$ và $I_B = 20\,\mu A$. Hệ số $\beta$ gần đúng là:

   - **A.** 20
   - **B.** 50
   - **\textcolor{red}{C.}** 100
   - **D.** 200

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** $\beta = I_C/I_B = 2\,mA / 20\,\mu A = 100$.

107. Trong mạch CE, nếu $I_B$ tăng thì điện áp collector $V_C$ thường:

   - **A.** Tăng
   - **\textcolor{red}{B.}** Giảm
   - **C.** Không đổi
   - **D.** Đổi dấu

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** $I_C$ tăng làm sụt áp trên $R_C$ tăng, nên $V_C = V_{CC} - I_C R_C$ giảm.

108. Điểm Q của CE muốn đối xứng biên độ xoay chiều thường nên đặt:

   - **A.** Sát vùng ngắt
   - **B.** Sát vùng bão hòa
   - **\textcolor{red}{C.}** Gần giữa đường tải DC
   - **D.** Ở mọi vị trí đều như nhau

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Đặt gần giữa đường tải giúp tín hiệu ra dao động đối xứng trước khi cắt đỉnh ở hai phía.

109. Nếu tụ bypass emitter đủ lớn, trong phân tích AC điện trở emitter bên ngoài sẽ:

   - **A.** Tăng gấp đôi
   - **\textcolor{red}{B.}** Bị xem gần như ngắn mạch
   - **C.** Bị xem như hở mạch
   - **D.** Bằng $\beta R_C$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Tụ bypass lớn làm emitter gần mass AC, do đó $R_E$ không còn gây hồi tiếp âm mạnh cho tín hiệu xoay chiều.

110. Mạch CC thường được dùng làm tầng đệm vì:

   - **A.** Có độ lợi áp rất lớn
   - **B.** Có trở vào rất nhỏ
   - **\textcolor{red}{C.}** Có trở vào lớn và trở ra nhỏ
   - **D.** Luôn đảo pha $180^\circ$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** CC hay emitter follower phù hợp phối hợp trở kháng vì ít tải tầng trước và kéo tải sau tốt.

111. Trong mạch CB, đại lượng nào thường nhỏ nhất?

   - **A.** Trở ra
   - **\textcolor{red}{B.}** Trở vào
   - **C.** Độ lợi áp
   - **D.** Điện áp nguồn

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Tín hiệu đi vào phía emitter nên mạch CB có trở vào rất nhỏ.

112. Nếu $I_E = 2\,mA$ thì điện trở emitter vi sai gần đúng $r'_e$ bằng:

   - **A.** $5\,\Omega$
   - **B.** $8\,\Omega$
   - **\textcolor{red}{C.}** $12.5\,\Omega$
   - **D.** $25\,\Omega$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** $r'_e \approx 25\,mV/I_E = 25\,mV/2\,mA = 12.5\,\Omega$.

113. JFET kênh N có $I_{DSS} = 8\,mA$, $V_P = -4\,V$, $V_{GS} = -2\,V$. Dòng $I_D$ gần đúng là:

   - **A.** $1\,mA$
   - **B.** $4\,mA$
   - **\textcolor{red}{C.}** $2\,mA$
   - **D.** $8\,mA$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** $I_D = I_{DSS}(1 - V_{GS}/V_P)^2 = 8(1-0.5)^2 = 8 \times 0.25 = 2\,mA$.

114. Với JFET kênh N, khi $V_{GS} = 0$ thì:

   - **A.** $I_D = 0$
   - **\textcolor{red}{B.}** $I_D = I_{DSS}$
   - **C.** $I_D = V_P$
   - **D.** Gate bắt đầu dẫn mạnh

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Tại $V_{GS} = 0$, JFET cho dòng drain cực đại theo mô hình Shockley, bằng $I_{DSS}$.

115. Với E-MOSFET kênh N, nếu $V_{GS} < V_{TH}$ thì linh kiện ở:

   - **\textcolor{red}{A.}** Vùng cutoff
   - **B.** Vùng triode
   - **C.** Vùng saturation
   - **D.** Vùng breakdown

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** MOSFET tăng cường chưa tạo được kênh dẫn khi $V_{GS}$ chưa vượt ngưỡng.

116. Với E-MOSFET kênh N, điều kiện vùng triode là:

   - **A.** $V_{GS} < V_{TH}$
   - **B.** $V_{DS} > V_{GS} - V_{TH}$
   - **\textcolor{red}{C.}** $V_{DS} < V_{GS} - V_{TH}$
   - **D.** $V_{DS} = 0$ với mọi trường hợp

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Miền triode hay ohmic của E-MOSFET xảy ra khi transistor đã mở và $V_{DS}$ còn nhỏ hơn overdrive.

117. Nếu $V_{TH} = 2\,V$ và $V_{GS} = 5\,V$, giá trị overdrive $V_{OV} = V_{GS} - V_{TH}$ bằng:

   - **A.** $1\,V$
   - **B.** $2\,V$
   - **\textcolor{red}{C.}** $3\,V$
   - **D.** $7\,V$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Overdrive là phần điện áp vượt ngưỡng: $V_{OV} = 5 - 2 = 3\,V$.

118. Trong self-bias JFET kênh N, điện trở source $R_S$ tạo ra:

   - **A.** $V_{GS} > 0$
   - **\textcolor{red}{B.}** $V_{GS} < 0$
   - **C.** $I_G > I_D$
   - **D.** Gate dẫn mạnh

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Dòng drain tạo điện áp dương ở source, trong khi gate gần 0 V nên $V_{GS}$ âm.

119. Trong mạch CS dùng FET, tín hiệu ra thường:

   - **A.** Cùng pha với tín hiệu vào
   - **\textcolor{red}{B.}** Ngược pha với tín hiệu vào
   - **C.** Bằng 0 ở mọi tần số
   - **D.** Chỉ có thành phần DC

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Cấu hình common source tương tự CE của BJT nên đảo pha $180^\circ$.

120. Thông số $g_m$ của FET cho biết:

   - **A.** Điện trở ngõ vào
   - **B.** Điện áp ngưỡng
   - **\textcolor{red}{C.}** Mức thay đổi dòng drain theo điện áp điều khiển
   - **D.** Công suất cực đại

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** $g_m = \partial I_D / \partial V_{GS}$, nên phản ánh khả năng biến thiên dòng theo điện áp điều khiển.

121. Mạch op-amp đảo có $R_{in} = 10\,k\Omega$, $R_f = 47\,k\Omega$. Độ lợi gần đúng là:

   - **A.** $+4.7$
   - **\textcolor{red}{B.}** $-4.7$
   - **C.** $-5.7$
   - **D.** $+5.7$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Với mạch đảo, $A_v = -R_f/R_{in} = -47/10 = -4.7$.

122. Mạch op-amp không đảo có $R_f = 18\,k\Omega$, $R_1 = 2\,k\Omega$. Độ lợi gần đúng là:

   - **A.** 8
   - **B.** 9
   - **\textcolor{red}{C.}** 10
   - **D.** 19

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** $A_v = 1 + R_f/R_1 = 1 + 18/2 = 10$.

123. Trong mạch cộng đảo với ba đầu vào, nếu các điện trở vào bằng nhau thì đầu ra tỉ lệ với:

   - **A.** Hiệu của ba đầu vào
   - **\textcolor{red}{B.}** Tổng đại số có dấu âm của ba đầu vào
   - **C.** Tích của ba đầu vào
   - **D.** Căn bậc hai tổng các đầu vào

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Mạch cộng đảo cộng các dòng vào nút ảo rồi tạo đầu ra âm tương ứng tổng có trọng số.

124. Comparator không hồi tiếp âm mạnh thường cho đầu ra:

   - **A.** Luôn nằm trong vùng tuyến tính
   - **\textcolor{red}{B.}** Bão hòa về một trong hai mức nguồn
   - **C.** Luôn bằng 0
   - **D.** Chỉ có sóng sin

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Comparator khuếch đại sai biệt rất lớn nên đầu ra nhanh chóng về mức bão hòa cao hoặc thấp.

125. Schmitt trigger hữu ích vì nó:

   - **A.** Làm giảm trở vào
   - **B.** Tạo tích phân
   - **\textcolor{red}{C.}** Tạo hysteresis chống nhiễu ngưỡng
   - **D.** Biến op-amp thành DAC

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Hysteresis giúp tín hiệu nhiễu quanh ngưỡng không làm đầu ra rung lắc liên tục.

126. Nếu $V_+ > V_-$ trong comparator cấp nguồn đối xứng và chưa bão hòa giới hạn khác, đầu ra có xu hướng:

   - **\textcolor{red}{A.}** Lên mức dương
   - **B.** Xuống mức âm
   - **C.** Bằng 0
   - **D.** Không xác định

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** Dấu sai biệt dương làm op-amp khuếch đại đầu ra theo chiều dương cho đến gần mức bão hòa dương.

127. Mạch theo áp dùng để:

   - **A.** Khuếch đại áp lớn
   - **\textcolor{red}{B.}** Cách ly tải nhờ trở vào lớn và trở ra nhỏ
   - **C.** Tạo roll-off lớn
   - **D.** Tạo dao động Wien

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Voltage follower có gain gần 1 nhưng rất phù hợp làm bộ đệm.

128. Nếu op-amp lý tưởng ở chế độ tuyến tính có hồi tiếp âm, dòng vào hai chân vào gần đúng là:

   - **\textcolor{red}{A.}** Bằng 0
   - **B.** Bằng dòng ra
   - **C.** Bằng nhau và khác 0 lớn
   - **D.** Tùy ý không ràng buộc

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** Mô hình lý tưởng cho trở vào vô hạn nên dòng vào hai chân gần như bằng 0.

129. Mạch tích phân op-amp khi vào là điện áp DC lý tưởng sẽ cho đầu ra:

   - **A.** Cũng là DC không đổi
   - **\textcolor{red}{B.}** Ramp tuyến tính theo thời gian
   - **C.** Sóng sin
   - **D.** Luôn bằng 0

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Tích phân của hằng số là hàm bậc nhất theo thời gian nên đầu ra là dạng ramp.

130. Mạch vi phân op-amp nhạy nhất với tín hiệu vào nào sau đây?

   - **A.** Tín hiệu DC hằng
   - **B.** Tín hiệu thay đổi rất chậm
   - **\textcolor{red}{C.}** Tín hiệu thay đổi nhanh
   - **D.** Không phụ thuộc dạng vào

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Đạo hàm càng lớn khi tín hiệu biến thiên càng nhanh, nên mạch vi phân nhạy với cạnh nhanh.

131. Điều kiện Barkhausen về pha để dao động duy trì là tổng pha quanh vòng bằng:

   - **A.** $90^\circ$
   - **B.** $180^\circ$
   - **\textcolor{red}{C.}** $0^\circ$ hoặc $360^\circ$
   - **D.** $270^\circ$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Hồi tiếp phải đồng pha khi quay hết một vòng thì dao động mới tự duy trì được.

132. Nếu trong mạch dao động biên độ vòng $|A\beta| < 1$ thì:

   - **A.** Dao động tăng dần
   - **\textcolor{red}{B.}** Dao động tắt dần
   - **C.** Dao động giữ nguyên
   - **D.** Tần số tăng gấp đôi

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Sau mỗi vòng biên độ bị giảm đi nên dao động không tự duy trì.

133. Với Wien bridge đối xứng, nếu $R$ tăng gấp đôi còn $C$ giữ nguyên thì $f_0$ sẽ:

   - **A.** Tăng gấp đôi
   - **\textcolor{red}{B.}** Giảm một nửa
   - **C.** Giảm bốn lần
   - **D.** Không đổi

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** $f_0 = 1/(2\pi RC)$ nên khi $R$ tăng gấp đôi thì tần số giảm còn một nửa.

134. Bộ lọc RC bậc một có một pole nên độ dốc sau tần số cắt xấp xỉ:

   - **\textcolor{red}{A.}** $-20\,dB/dec$
   - **B.** $-10\,dB/dec$
   - **C.** $-40\,dB/dec$
   - **D.** $0\,dB/dec$

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** Mỗi pole bậc một đóng góp xấp xỉ $20\,dB/dec$ về độ dốc biên độ.

135. Mắc ba tầng lọc thông thấp bậc một giống nhau nối tiếp sẽ cho roll-off gần đúng:

   - **A.** $-20\,dB/dec$
   - **B.** $-40\,dB/dec$
   - **\textcolor{red}{C.}** $-60\,dB/dec$
   - **D.** $-80\,dB/dec$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Ba tầng bậc một tương ứng ba pole nên tổng độ dốc là $-60\,dB/dec$.

136. Một lọc thông cao bậc một có đặc điểm biên độ nào đúng?

   - **A.** Phẳng ở thấp tần và suy giảm ở cao tần
   - **\textcolor{red}{B.}** Suy giảm ở thấp tần và phẳng ở cao tần
   - **C.** Chỉ thông một tần số duy nhất
   - **D.** Không có điểm cắt

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Thông cao chặn vùng thấp tần và cho qua tốt vùng cao tần.

137. Trong bộ lọc thông dải, nếu $f_L$ tăng còn $f_H$ giữ nguyên thì băng thông sẽ:

   - **A.** Tăng
   - **\textcolor{red}{B.}** Giảm
   - **C.** Không đổi
   - **D.** Đổi dấu

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** $BW = f_H - f_L$, nên khi $f_L$ tăng thì khoảng cách giữa hai tần số cắt giảm.

138. Với bộ lọc thông dải, nếu $Q$ lớn thì:

   - **A.** Dải thông rộng hơn
   - **\textcolor{red}{B.}** Dải thông hẹp hơn và chọn lọc hơn
   - **C.** Không còn tần số trung tâm
   - **D.** Roll-off bằng 0

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** $Q = f_0/BW$, nên $Q$ lớn tương ứng với $BW$ nhỏ và đặc tính chọn lọc cao hơn.

139. Hàm truyền $H(s) = 1/(1+sRC)$ tương ứng với:

   - **\textcolor{red}{A.}** Lọc thông thấp bậc một
   - **B.** Lọc thông cao bậc một
   - **C.** Lọc thông dải
   - **D.** Mạch dao động

   **Đáp án đúng:** **\textcolor{red}{A}**
   **Giải thích:** Tại $s=0$ gain bằng 1, còn khi tần số tăng thì mẫu tăng theo $sRC$, đặc trưng của thông thấp bậc một.

140. Hàm truyền $H(s) = sRC/(1+sRC)$ tương ứng với:

   - **A.** Lọc thông thấp
   - **\textcolor{red}{B.}** Lọc thông cao
   - **C.** Mạch cộng đảo
   - **D.** Mạch chỉnh lưu

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Tại $s=0$ gain bằng 0 còn ở cao tần tiến đến 1, nên đây là thông cao bậc một.

141. Nếu một tín hiệu sin đi qua hệ tuyến tính bất biến với tần số nằm trong dải thông, đầu ra xác lập sẽ:

   - **A.** Mất hoàn toàn dạng sin
   - **\textcolor{red}{B.}** Vẫn là sin cùng tần số nhưng đổi biên độ và pha
   - **C.** Luôn thành sóng vuông
   - **D.** Luôn tăng gấp đôi tần số

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Với hệ LTI, tín hiệu sin là hàm riêng nên đầu ra vẫn cùng tần số, chỉ thay đổi biên độ và pha.

142. Tại tần số cắt của lọc bậc một, công suất trên tải còn gần bằng:

   - **A.** $100\%$
   - **B.** $75\%$
   - **\textcolor{red}{C.}** $50\%$
   - **D.** $25\%$

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Mức $-3\,dB$ tương ứng biên độ còn $1/\sqrt{2}$, nên công suất còn một nửa.

143. Nếu $|H(j\omega)| > 1$ tại một dải tần thì:

   - **A.** Mạch chắc chắn thụ động
   - **\textcolor{red}{B.}** Mạch có thể đang khuếch đại trong dải đó
   - **C.** Pha luôn bằng 0
   - **D.** Không thể có ở op-amp

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Biên độ lớn hơn 1 nghĩa là đầu ra lớn hơn đầu vào tại dải tần đó, nên mạch có gain lớn hơn 1.

144. Mỗi zero bậc một trong đồ thị Bode biên độ sẽ làm độ dốc thay đổi gần đúng:

   - **A.** $-20\,dB/dec$
   - **\textcolor{red}{B.}** $+20\,dB/dec$
   - **C.** $+10\,dB/dec$
   - **D.** $0\,dB/dec$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Zero làm biên độ tăng dốc lên thêm khoảng $20\,dB/dec$ sau tần số gãy của nó.

145. Nếu một mạch có hai pole trùng nhau tại cùng tần số gãy thì ngay sau tần số đó độ dốc gần đúng là:

   - **A.** $-20\,dB/dec$
   - **\textcolor{red}{B.}** $-40\,dB/dec$
   - **C.** $-60\,dB/dec$
   - **D.** $0\,dB/dec$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Hai pole cùng tác dụng tại một vị trí nên đóng góp cộng dồn thành $-40\,dB/dec$.

146. Một mạch có $f_L = 100\,Hz$ và $f_H = 10\,kHz$. Tần số trung tâm gần đúng là:

   - **A.** $100\,Hz$
   - **\textcolor{red}{B.}** $1\,kHz$
   - **C.** $5.05\,kHz$
   - **D.** $9.9\,kHz$

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** $f_0 = \sqrt{f_L f_H} = \sqrt{100 \times 10000} = 1000\,Hz = 1\,kHz$.

147. Với $f_L = 100\,Hz$ và $f_H = 10\,kHz$, hệ số chất lượng gần đúng là:

   - **A.** 0.01
   - **\textcolor{red}{B.}** 0.101
   - **C.** 1
   - **D.** 10

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** $BW = 9900\,Hz$ và $Q = f_0/BW \approx 1000/9900 \approx 0.101$.

148. Nếu mạch lọc active Sallen-Key bậc hai được ghép thêm một tầng RC bậc một nối tiếp thì bậc toàn mạch là:

   - **A.** 1
   - **B.** 2
   - **\textcolor{red}{C.}** 3
   - **D.** 4

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Bậc của toàn mạch bằng tổng bậc từng tầng khi ghép cascade, nên $2 + 1 = 3$.

149. Trong phân tích tần số, thay $s = j\omega$ vào hàm truyền có ý nghĩa là:

   - **A.** Chuyển sang miền thời gian
   - **\textcolor{red}{B.}** Khảo sát đáp ứng trên trục tần số điều hòa xác lập
   - **C.** Tìm công suất cực đại
   - **D.** Bỏ qua pha của hệ

   **Đáp án đúng:** **\textcolor{red}{B}**
   **Giải thích:** Việc đặt $s = j\omega$ lấy hàm truyền trên trục ảo, đúng với kích thích sin ở trạng thái xác lập.

150. Nhận định nào đúng nhất về mối liên hệ giữa số pole và độ khó chặn ngoài dải?

   - **A.** Số pole không ảnh hưởng vùng chặn
   - **B.** Pole chỉ đổi pha, không đổi biên độ
   - **\textcolor{red}{C.}** Nhiều pole hơn thường cho vùng chặn dốc hơn và chặn mạnh hơn
   - **D.** Chỉ zero mới quyết định khả năng lọc

   **Đáp án đúng:** **\textcolor{red}{C}**
   **Giải thích:** Tăng số pole làm tăng bậc lọc, từ đó roll-off dốc hơn và khả năng suy giảm ngoài dải mạnh hơn.

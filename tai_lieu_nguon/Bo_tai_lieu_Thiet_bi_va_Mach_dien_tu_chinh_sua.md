---
title: "Trắc nghiệm môn Các Thiết Bị và Mạch Điện Tử (Bản chỉnh công thức)"
author: "Biên soạn từ Slide/ và Slide_new/"
lang: "vi"
geometry: margin=2cm
fontsize: 11pt
---

# Trắc nghiệm môn Các Thiết Bị và Mạch Điện Tử

                            Biên soạn từ Slide/ và Slide_new/



Phạm vi tài liệu
Tài liệu này được tổng hợp từ hai thư mục nguồn:
  • Slide/
  • Slide_new/
Nội dung bao quát các chủ đề xuất hiện trong slide:
  • Đại cương và linh kiện điện tử cơ bản
  • Vật liệu bán dẫn, chuyển tiếp P-N, diode và ứng dụng
  • BJT: cấu tạo, nguyên lý, đặc tính, phân cực, điểm Q
  • Phân tích mạch khuếch đại CE, CB, CC
  • FET: JFET, MOSFET, phân cực và khuếch đại
  • Op-Amp: cấu tạo, đặc tính, hồi tiếp âm, ứng dụng
  • Mạch so sánh, cộng, trừ, tích phân, vi phân
  • Mạch dao động
  • Mạch lọc thụ động và mạch lọc tích cực


Bộ hình trực quan được thêm bằng Python
Tài liệu này đã được bổ sung các biểu đồ và mô hình hóa trực quan sinh tự động bằng:
  • scripts/generate_electronic_figures.py
Mục tiêu của phần hình là mô tả trực tiếp:
  • đặc tuyến dòng áp của linh kiện
  • dạng sóng vào ra của mạch
  • điểm làm việc và đường tải
  • vùng hoạt động của transistor
  • đáp ứng tần số của bộ lọc
  • sơ đồ khối cho các mạch và hệ thống
Hình này cho thấy luồng xử lý điển hình của hệ điện tử tương tự: tín hiệu tự nhiên được cảm
biến đổi sang tín hiệu điện, sau đó đi qua tiền xử lý, lọc, khuếch đại, khối xử lý và cuối cùng
cấp cho tải hoặc thiết bị hiển thị.





                     Hình 1: Mô hình hệ thống xử lý tín hiệu điện tử


1. Kiến thức nền tảng
1.1. Đại lượng điện cơ bản
Điện tích

  • Ký hiệu: Q
  • Đơn vị: Coulomb (C)
  • Công thức: $Q = I\,t$


Dòng điện

  • Ký hiệu: I
  • Đơn vị: Ampere (A)
  • Bản chất: dòng chuyển dời có hướng của hạt mang điện
  • Công thức trung bình: $I = \dfrac{\Delta Q}{\Delta t}$


Điện áp

  • Ký hiệu: V hoặc U
  • Đơn vị: Volt (V)
  • Công thức: $U_{AB} = V_A - V_B$


Công suất

  • Ký hiệu: P
  • Đơn vị: Watt (W)
  • Công thức: $P = U I$


1.2. Linh kiện thụ động
Điện trở

  • Ký hiệu: R
  • Đơn vị: Ohm (Ω)
  • Định luật Ohm: $U = I R$
  • Vai trò: hạn dòng, chia áp, định thiên, tạo hằng số thời gian




Tụ điện

  • Ký hiệu: C
  • Đơn vị: Farad (F)
  • Quan hệ dòng áp:
       – $i_C = C\,\dfrac{dv}{dt}$
       – $v_C = \dfrac{1}{C}\int i_C\,dt$
  • Trong DC xác lập: gần như hở mạch
  • Trong AC: trở kháng phụ thuộc tần số
       – $X_C = \dfrac{1}{2\pi f C}$


Cuộn cảm

  • Ký hiệu: L
  • Đơn vị: Henry (H)
  • Quan hệ dòng áp:
       – $v_L = L\,\dfrac{di}{dt}$
  • Trong DC xác lập: gần như ngắn mạch
  • Trong AC:
       – $X_L = 2\pi f L$


1.3. Công cụ phân tích mạch
  • KCL: tổng dòng vào nút bằng tổng dòng ra nút
  • KVL: tổng đại số điện áp trên vòng kín bằng 0
  • Chia áp: V_x = V_nguon . R_x / (R_tổng nối tiếp)
  • Chia dòng: dòng chia tỉ lệ nghịch với điện trở nhánh
  • Thevenin:
      – V_Th: điện áp hở mạch tại hai cực
      – R_Th: điện trở nhìn vào mạch khi triệt nguồn độc lập
  • Norton:
      – $I_N = \dfrac{V_{Th}}{R_{Th}}$
      – $R_N = R_{Th}$


2. Vật liệu bán dẫn và chuyển tiếp P-N
2.1. Phân loại vật liệu theo tính dẫn điện
  • Dẫn điện
  • Bán dẫn
  • Cách điện


2.2. Silicon và Germanium
Từ slide, Silicon được nhấn mạnh là vật liệu ổn định hơn Germanium trong linh kiện điện tử.
Trong thực tế:
  • Silicon chịu nhiệt tốt hơn
  • Dòng rò nhỏ hơn
  • Linh kiện ổn định hơn


2.3. Bản chất dẫn điện của bán dẫn
   • Khi được cung cấp năng lượng, electron có thể nhảy từ vùng hóa trị sang vùng dẫn
   • Dẫn điện diễn ra nhờ:
       – dòng electron
       – dòng lỗ trống


2.4. Pha tạp
Bán dẫn loại N

   • Pha tạp nguyên tố nhóm V
   • Hạt tải đa số: electron


Bán dẫn loại P

   • Pha tạp nguyên tố nhóm III
   • Hạt tải đa số: lỗ trống


2.5. Chuyển tiếp P-N
Khi ghép P và N:
   • Electron từ vùng N khuếch tán sang P
   • Lỗ trống từ vùng P khuếch tán sang N
   • Hình thành vùng hiếm và điện trường nội tại
Ý nghĩa:
   • Là nền tảng của diode, BJT và nhiều linh kiện bán dẫn khác


3. Diode
3.1. Cấu tạo và ký hiệu
   • Diode có 2 cực:
       – Anode (P)
       – Cathode (N)
   • Chức năng cơ bản: cho dòng đi theo một chiều thuận và chặn chiều ngược


3.2. Nguyên lý hoạt động
Phân cực thuận

   • Cực dương nối Anode
   • Cực âm nối Cathode
   • Khi V_D vượt điện áp ngưỡng, diode dẫn
Giá trị điển hình:
   • Silicon: $V_\gamma \approx 0.7\,\mathrm{V}$
   • Germanium: $V_\gamma \approx 0.3\,\mathrm{V}$



Phân cực nghịch

  • Cực dương nối Cathode
  • Cực âm nối Anode
  • Dòng rất nhỏ, xem như bằng 0 trong mô hình lý tưởng
  • Nếu điện áp ngược quá lớn: đánh thủng


3.3. Đặc tuyến V-I
Vùng thuận

  • Trước ngưỡng: dòng tăng ít
  • Sau ngưỡng: dòng tăng rất nhanh


Vùng nghịch

  • Có dòng rò nhỏ
  • Sau điện áp đánh thủng: dòng tăng mạnh




                             Hình 2: Đặc tuyến V-I của diode

Cách đọc hình:
  • phía phải mốc 0.7V: diode Silicon dẫn rất mạnh
  • quanh gốc tọa độ: diode gần như chưa dẫn
  • phía điện áp âm lớn: diode bước vào vùng đánh thủng nghịch
  • độ dốc của đặc tuyến tại điểm làm việc liên quan trực tiếp đến điện trở vi sai của diode





3.4. Các mô hình diode
Mô hình lý tưởng

  • Thuận: ngắn mạch
  • Nghịch: hở mạch


Mô hình thực xấp xỉ

  • Thuận: rơi áp cố định 0.7 V với diode Si
  • Nghịch: hở mạch


Mô hình hoàn chỉnh

  • Thuận: V_D = V_γ + I_D.r_d
  • Nghịch: có điện trở ngược rất lớn


3.5. Công thức thường dùng
  • Diode thuận nối tiếp điện trở:
      – I = (V_S - V_D) / R
  • Với mô hình thực:
      – I ≈ (V_S - 0.7) / R


3.6. Ứng dụng của diode
Chỉnh lưu nửa chu kỳ

  • Chỉ cho qua một bán kỳ
  • Điện áp DC trung bình thấp
  • Gợn sóng lớn


Chỉnh lưu toàn chu kỳ

  • Tận dụng cả hai bán kỳ
  • Điện áp trung bình lớn hơn
  • Tần số gợn bằng 2f_nguồn
Ý nghĩa trực quan:
  • dạng sóng đầu là điện áp AC đầu vào
  • dạng sóng giữa là chỉnh lưu bán kỳ, chỉ giữ nửa dương
  • dạng sóng cuối là chỉnh lưu toàn kỳ, cả hai bán kỳ đều trở thành điện áp dương
  • biên độ đầu ra thấp hơn đầu vào do sụt áp trên diode


Mạch lọc nguồn

  • Tụ lọc mắc song song tải để giảm độ nhấp nhô
  • Hệ số nhấp nhô phụ thuộc R_L, C, f





Hình 3: Dạng sóng trước và sau chỉnh lưu





Zener ổn áp

   • Làm việc vùng đánh thủng nghịch có kiểm soát
   • Điện áp ra gần bằng V_Z
Điều kiện dòng:
   • I_ZK <= I_Z <= I_ZM


3.7. Cách giải bài tập diode
Dạng 1: Xác định diode dẫn hay ngắt

  1. Chọn mô hình diode theo đề
  2. Giả sử diode dẫn
  3. Tính điện áp và dòng
  4. Kiểm tra điều kiện:
       • nếu V_D >= 0.7 V với diode Si thì giả sử dẫn hợp lý
       • nếu dòng âm hoặc điện áp không thỏa thì diode ngắt


Dạng 2: Tính điện áp ra mạch chỉnh lưu

  1. Xác định số diode dẫn trong mỗi bán kỳ
  2. Trừ tổng sụt áp diode khỏi đỉnh vào
  3. Vẽ dạng sóng sau chỉnh lưu
  4. Nếu có tụ lọc, xác định khoảng nạp và xả của tụ


Dạng 3: Ổn áp Zener

  1. Giả sử Zener làm việc vùng ổn áp
  2. Tính dòng qua điện trở hạn dòng:
       • I_R = (V_S - V_Z) / R
  3. Tính dòng tải:
       • I_L = V_Z / R_L
  4. Suy ra:
       • I_Z = I_R - I_L
  5. Kiểm tra I_ZK <= I_Z <= I_ZM


4. Transistor BJT
4.1. Cấu tạo
BJT có 3 cực:
   • Emitter (E)
   • Base (B)
   • Collector (C)
Hai loại:
   • NPN
   • PNP



4.2. Nguyên lý hoạt động NPN
  • Mối nối BE phân cực thuận
  • Mối nối BC phân cực nghịch khi làm việc vùng khuếch đại
  • Electron từ Emitter sang Base
  • Base mỏng và pha tạp nhẹ nên chỉ một phần nhỏ tạo thành I_B
  • Phần lớn bị hút sang Collector tạo I_C


4.3. Quan hệ dòng điện
  • I_E = I_B + I_C
  • β_DC = I_C / I_B
  • α_DC = I_C / I_E
  • Liên hệ:
       – α = β / (β + 1)
       – β = α / (1 - α)


4.4. Các vùng hoạt động
Cut-off

  • V_BE < 0.7 V xấp xỉ
  • I_B ≈ 0, I_C ≈ 0
  • Transistor tắt


Active (linear)

  • V_BE ≈ 0.7 V
  • V_CE > V_CEsat
  • I_C = β.I_B
  • Dùng cho khuếch đại


Saturation

  • BE thuận, BC cũng thuận
  • V_CE nhỏ, thường xấp xỉ 0.2 V
  • Transistor mở bão hòa
  • Dùng cho đóng cắt
Hình vùng hoạt động giúp phân biệt rõ:
  • vùng trái: transistor dễ bão hòa vì V_CE quá thấp
  • vùng giữa: vùng active để khuếch đại tuyến tính
  • khi dòng base rất nhỏ, transistor tiến dần tới cutoff


4.5. Đường tải DC và điểm Q
Khái niệm

  • Đường tải DC biểu diễn ràng buộc giữa I_C và V_CE
  • Điểm Q là điểm làm việc không tín hiệu AC



                      Hình 4: Mô hình các vùng hoạt động của BJT


Ý nghĩa

  • Điểm Q ở giữa vùng tuyến tính giúp biên độ dao động đầu ra đối xứng hơn
  • Giảm méo do cắt đỉnh hoặc bão hòa


Công thức cơ bản mạch CE đơn giản

  • V_CC = I_C.R_C + V_CE + I_E.R_E
  • Thường gần đúng I_E ≈ I_C
Hình này cần đọc theo đúng logic phân tích mạch:
  • giao điểm với trục V_CE là trạng thái không có dòng collector
  • giao điểm với trục I_C là trạng thái V_CE = 0
  • điểm Q là điểm phân cực DC thực tế của mạch
  • nếu tín hiệu AC làm mạch dao động quanh Q quá gần hai biên, đầu ra sẽ bị méo do
    cutoff hoặc saturation


4.6. Các kiểu phân cực
Base bias

  • Đơn giản nhưng kém ổn định


Collector-feedback bias

  • Có hồi tiếp ổn định hơn





                         Hình 5: Đường tải DC và điểm Q của BJT


Emitter bias

  • Ổn định hơn nhờ R_E


Voltage-divider bias

  • Phổ biến nhất
  • Ổn định tốt
Với cầu chia áp:
  • V_B ≈ V_CC . R_2 / (R_1 + R_2) nếu dòng base nhỏ
  • V_E = V_B - 0.7
  • I_E = V_E / R_E
  • I_C ≈ I_E
  • V_C = V_CC - I_C.R_C
  • V_CE = V_C - V_E
Nếu cần chính xác hơn:
  • Quy mạch phân áp về Thevenin:
      – V_Th = V_CC . R_2 / (R_1 + R_2)
      – R_Th = R_1 || R_2
  • Sau đó:
      – I_B = (V_Th - 0.7) / (R_Th + (β+1)R_E)
      – I_C = βI_B
      – I_E = (β+1)I_B





4.7. Mô hình tín hiệu nhỏ
Thường dùng:
  • r'_e ≈ 25mV / I_E
  • r_π = β.r'_e
  • g_m = I_C / V_T, với V_T ≈ 25mV


4.8. Ba cấu hình khuếch đại BJT
CE - Common Emitter

  • Khuếch đại áp lớn
  • Đảo pha 180 độ
  • Khuếch đại dòng khá lớn
Xấp xỉ:
  • A_v ≈ - (R_C || R_L) / r'_e nếu bỏ qua R_E bởi tụ bypass


CB - Common Base

  • Khuếch đại áp lớn
  • Không khuếch đại dòng đáng kể
  • Trở vào nhỏ
  • Không đảo pha


CC - Common Collector / emitter follower

  • A_v ≈ 1
  • Trở vào lớn
  • Trở ra nhỏ
  • Khuếch đại dòng tốt


4.9. Cách giải bài tập BJT
Dạng 1: Phân cực DC

  1. Xác định loại mạch phân cực
  2. Tính V_B, V_E, I_E, I_C
  3. Tính V_C, V_CE
  4. Kết luận transistor ở vùng nào


Dạng 2: Tìm điểm Q

  1. Viết phương trình đường tải DC
  2. Xác định hai giao điểm:
       • I_C = 0 => V_CE = V_CC
       • V_CE = 0 => I_C ≈ V_CC / (R_C + R_E)
  3. Tìm điểm Q bằng dòng base hoặc mạch phân cực
  4. Kiểm tra Q có nằm giữa vùng active không




Dạng 3: Khuếch đại tín hiệu nhỏ

  1. Đưa nguồn DC về mass AC
  2. Thay transistor bằng mô hình tín hiệu nhỏ
  3. Tính R_in, R_out, A_v, A_i
  4. Với CE, chú ý dấu âm do đảo pha


Dạng 4: Đánh giá méo

  1. So sánh biên độ tín hiệu AC với khoảng dao động quanh Q
  2. Nếu Q gần saturation: đỉnh âm hoặc dương dễ bị cắt
  3. Nếu Q gần cutoff: đầu ra dễ mất một nửa chu kỳ


5. FET: JFET và MOSFET
5.1. Đặc điểm chung
FET là transistor điều khiển bằng điện áp:
  • Trở kháng vào rất lớn
  • Dòng vào cổng gần như bằng 0


5.2. JFET
Bản chất

  • Dòng I_D chạy từ Drain đến Source qua kênh dẫn
  • Điện áp V_GS điều khiển độ rộng kênh


Thông số cơ bản

  • I_DSS: dòng drain khi V_GS = 0
  • V_GS(off) hoặc V_P: điện áp khóa kênh


Phương trình Shockley

  • I_D = I_DSS (1 - V_GS / V_P)^2
Lưu ý:
  • Với JFET kênh N, V_P < 0
  • Ở chế độ hoạt động bình thường, V_GS thường âm


Các kiểu phân cực JFET

  • Tự phân cực
  • Phân cực cầu chia áp
  • Phân cực nguồn dòng





Tự phân cực

  • V_G ≈ 0
  • V_S = I_D.R_S
  • V_GS = V_G - V_S = -I_D.R_S
Thay vào Shockley để giải I_D




                         Hình 6: Đặc tuyến truyền đạt của JFET

Đồ thị này mô hình hóa quan hệ điều khiển bằng điện áp của JFET:
  • tại V_GS = 0, dòng drain đạt I_DSS
  • khi V_GS giảm dần về âm, kênh dẫn bị thu hẹp và I_D giảm
  • tại V_GS(off) = V_P, kênh gần như bị khóa hoàn toàn


5.3. MOSFET
Đặc điểm

  • Cổng được cách điện bởi lớp oxide
  • Trở kháng vào rất lớn


Các loại

  • D-MOSFET (kênh liên tục)
  • E-MOSFET (kênh gián đoạn, thường dùng nhiều)


E-MOSFET kênh N

  • Chỉ dẫn khi V_GS > V_TH
  • Miền bão hòa xấp xỉ:
      – I_D = K(V_GS - V_TH)^2


5.4. Khuếch đại FET
Cấu hình CS - Common Source

  • Tương tự CE của BJT
  • Có khuếch đại áp lớn
  • Đảo pha 180 độ
Xấp xỉ:
  • A_v ≈ -g_m (R_D || R_L || r_d)


Tham số tín hiệu nhỏ

  • g_m = ΔI_D / ΔV_GS
  • Với JFET:
      – g_m = g_m0 (1 - V_GS / V_P)
      – g_m0 = 2I_DSS / |V_P|


5.5. Cách giải bài tập FET
Dạng 1: Tính điểm làm việc JFET

  1. Viết V_G, V_S, V_GS
  2. Dùng Shockley:
       • I_D = I_DSS (1 - V_GS / V_P)^2
  3. Giải hệ để tìm I_D
  4. Tính:
       • V_D = V_DD - I_D.R_D
       • V_DS = V_D - V_S


Dạng 2: Phân tích khuếch đại CS

  1. Tính Q-point trước
  2. Tính g_m
  3. Thay bằng mô hình tín hiệu nhỏ
  4. Tính A_v, Z_i, Z_o


6. Op-Amp
6.1. Khái niệm
Op-Amp là bộ khuếch đại vi sai có:
  • độ lợi vòng hở rất lớn
  • trở kháng vào rất lớn
  • trở kháng ra rất nhỏ
  • khả năng khử nhiễu đồng pha tốt





6.2. Hai chế độ hoạt động chính
Differential mode

  • Hai đầu vào khác nhau
  • Có thể:
      – single-ended
      – double-ended


Common mode

  • Hai đầu vào cùng pha, cùng biên độ
  • Lý tưởng: đầu ra bằng 0


6.3. Thông số quan trọng
  • A_OL: độ lợi vòng hở
  • Z_in: trở kháng đầu vào
  • Z_out: trở kháng đầu ra
  • CMRR: hệ số khử đồng pha
  • Slew rate
  • Input offset voltage
  • Input bias current
  • Maximum output swing
  • Bandwidth


Hệ số CMRR

  • CMRR = A_DM / A_CM
  • Theo dB:
      – CMRR_dB = 20 log10(CMRR)


6.4. Quy tắc vàng khi có hồi tiếp âm và op-amp lý tưởng
Nếu op-amp làm việc tuyến tính và chưa bão hòa:
  • I+ = I- = 0
  • V+ ≈ V-


6.5. Mạch khuếch đại cơ bản
Mạch đảo

  • A_v = V_o / V_i = -R_f / R_in
  • Trở vào xấp xỉ R_in
Các chi tiết quan trọng trên mô hình:
  • đầu không đảo nối mass nên đầu đảo hình thành mass ảo khi có hồi tiếp âm
  • R_in đặt dòng vào nút đảo
  • R_f đưa tín hiệu hồi tiếp từ ngõ ra về
  • dấu âm trong công thức là hệ quả trực tiếp của cấu trúc hồi tiếp này



                     Hình 7: Mô hình mạch khuếch đại đảo dùng Op-Amp


Mạch không đảo

  • A_v = 1 + R_f / R_1
  • Trở vào rất lớn


Mạch theo áp

  • A_v = 1
  • Dùng để đệm trở kháng


6.6. Ảnh hưởng của hồi tiếp âm
Từ nội dung slide:
  • tăng ổn định
  • giảm méo
  • mở rộng băng thông
  • tăng trở vào ở mạch không đảo
  • giảm trở ra
Quan hệ điển hình:
  • A_CL = A_OL / (1 + A_OLβ)


6.7. Băng thông và độ lợi
  • Op-amp có tích độ lợi-băng thông gần như hằng số trong nhiều loại phổ thông
  • Tăng độ lợi vòng kín thì băng thông giảm


6.8. Cách giải bài tập Op-Amp cơ bản
  1. Kiểm tra có hồi tiếp âm không
  2. Nếu có và chưa bão hòa:
       • đặt V+ = V-



       • đặt dòng vào hai cổng bằng 0
  3. Viết KCL tại nút vào
  4. Giải V_out
  5. Kiểm tra đầu ra có vượt giới hạn nguồn cấp không


7. Ứng dụng Op-Amp
7.1. Mạch so sánh
  • Không làm việc tuyến tính
  • Đầu ra bão hòa dương hoặc âm tùy:
      – V+ > V- => V_out ≈ +V_sat
      – V+ < V- => V_out ≈ -V_sat


Schmitt trigger

  • Có hồi tiếp dương
  • Tạo ngưỡng trên UTP và ngưỡng dưới LTP
  • Chống nhiễu tốt hơn




                     Hình 8: Dạng sóng của mạch so sánh Op-Amp

Hình biểu diễn rõ nguyên lý comparator:
  • khi V_in vượt V_ref, đầu ra bật lên mức bão hòa dương
  • khi V_in thấp hơn V_ref, đầu ra rơi xuống mức bão hòa âm
  • vì vậy comparator biến tín hiệu analog thành tín hiệu hai mức rất trực quan



7.2. Mạch cộng
Với mạch cộng đảo:
  • V_out = -R_f (V_1/R_1 + V_2/R_2 + ... + V_n/R_n)
Nếu R_1 = R_2 = ... = R_f:
  • V_out = -(V_1 + V_2 + ... + V_n)


7.3. Mạch trừ
Nếu điện trở ghép đúng tỉ lệ:
  • V_out = (R_2/R_1)(V_2 - V_1)


7.4. Mạch tích phân
  • V_out = -(1/RC) int(V_in dt)
Đặc tính:
  • vào xung vuông -> ra tam giác
  • vào DC -> ra dốc tuyến tính


7.5. Mạch vi phân
  • V_out = -RC . dV_in/dt
Đặc tính:
  • nhạy với cạnh xung
  • dễ khuếch đại nhiễu tần số cao


7.6. Cách giải bài tập ứng dụng Op-Amp
Mạch so sánh

  1. So sánh hai đầu vào
  2. Suy ra dấu đầu ra
  3. Giới hạn ở ±V_sat


Mạch cộng/trừ

  1. Dùng quy tắc V+ = V- nếu hồi tiếp âm
  2. Viết KCL tại nút vào đảo
  3. Rút V_out


Mạch tích phân/vi phân

  1. Xác định quan hệ toán học giữa vào và ra
  2. Chia tín hiệu vào theo từng đoạn thời gian
  3. Tính độ dốc hoặc diện tích để vẽ dạng sóng ra




8. Mạch dao động
8.1. Điều kiện Barkhausen
Để mạch dao động tự duy trì:
  • Tổng lệch pha quanh vòng bằng 0° hoặc 360°
  • Độ lợi vòng |Aβ| = 1 khi dao động ổn định
Điều kiện khởi động:
  • Ban đầu cần |Aβ| > 1


8.2. Dao động cầu Wien
Theo slide:
  • dùng mạng lead-lag RC
  • thích hợp tạo sin tần số thấp, thường dưới 1 MHz
  • tại tần số cộng hưởng:
       – lệch pha bằng 0
       – độ suy hao mạng hồi tiếp khoảng 1/3
Điều kiện khuếch đại:
  • mạch khuếch đại cần có độ lợi khoảng 3
Tần số dao động với phần tử đối xứng:
  • f_0 = 1 / (2πRC)




                   Hình 9: Quá trình khởi động của dao động cầu Wien

Đây là hình đặc biệt quan trọng vì nó mô tả động học khởi động:
  • dao động ban đầu rất nhỏ, xuất phát từ nhiễu
  • khi |Aβ| > 1, biên độ tăng dần
  • khi cơ chế ổn định tác động, biên độ dừng lại và mạch tạo sóng sin gần ổn định



8.3. Dạng bài tập dao động
  1. Xác định loại dao động
  2. Viết điều kiện pha
  3. Viết điều kiện biên độ
  4. Suy ra tần số dao động
  5. Tìm điện trở đặt độ lợi nếu đề yêu cầu


9. Mạch lọc thụ động
9.1. Khái niệm
Mạch lọc cho tín hiệu mong muốn đi qua và làm suy giảm tín hiệu không mong muốn theo
tần số.


9.2. Các loại cơ bản
  • Thông thấp (low-pass)
  • Thông cao (high-pass)
  • Thông dải (band-pass)
  • Triệt dải (band-stop/notch)


9.3. Đáp ứng tần số
Các khái niệm cần nhớ:
  • Tần số cắt f_c
  • Băng thông BW
  • Độ dốc suy giảm roll-off
  • Độ lợi theo dB:
      – A_v(dB) = 20 log10(V_out/V_in)


9.4. Mạch RC bậc nhất
Thông thấp RC

  • f_c = 1 / (2πRC)
  • Với f << f_c: tín hiệu qua gần như nguyên vẹn
  • Với f >> f_c: suy giảm mạnh


Thông cao RC

  • f_c = 1 / (2πRC)
  • Với f << f_c: suy giảm
  • Với f >> f_c: qua tốt
Từ đồ thị Bode này có thể quan sát ngay:
  • lọc thông thấp giữ tốt thành phần thấp tần rồi suy giảm sau f_c
  • lọc thông cao loại bỏ miền thấp tần và tiến dần tới miền qua tốt ở tần số cao
  • tại f_c, độ lợi xấp xỉ -3 dB



                      Hình 10: Đáp ứng tần số của lọc RC bậc một


9.5. Thông dải và triệt dải
  • Có thể ghép thông cao và thông thấp
  • Tần số trung tâm:
      – f_0 = sqrt(f_L.f_H)
  • Băng thông:
      – BW = f_H - f_L
Hình này mô tả bản chất của thông dải:
  • chỉ một miền quanh f_0 được cho qua
  • hai phía hai bên đều suy giảm
  • độ nhọn của đỉnh phản ánh mức chọn lọc hay hệ số Q


9.6. Cách giải bài tập lọc thụ động
 1. Nhận dạng loại mạch lọc
 2. Xác định linh kiện thấy ở ngõ ra
 3. Dùng giới hạn:
      • f = 0
      • f -> ∞
 4. Suy ra loại lọc
 5. Tính f_c từ 1/(2πRC)
 6. Nếu cần vẽ Bode, đánh dấu:
      • vùng bằng phẳng
      • điểm -3 dB
      • độ dốc 20 dB/dec mỗi cực





                        Hình 11: Đáp ứng của mạch lọc thông dải


10. Mạch lọc tích cực
10.1. Khái niệm
Mạch lọc tích cực dùng op-amp kết hợp R, C để:
  • lọc tín hiệu
  • có thể khuếch đại
  • tránh dùng cuộn cảm trong nhiều trường hợp




                         Hình 12: Mô hình hóa mạch lọc tích cực

Hình này giúp nhìn mạch lọc tích cực đúng bản chất chức năng:
  • mạng RC quyết định miền tần số được chọn
  • op-amp nâng mức tín hiệu và cách ly tải
  • nhánh hồi tiếp đặt ra dạng đáp ứng và độ lợi của cả hệ





10.2. Các dạng chính
  • Thông thấp tích cực
  • Thông cao tích cực
  • Thông dải tích cực
  • Triệt dải tích cực


10.3. Bộ lọc bậc một
Thông thấp bậc một

  • f_c = 1 / (2πRC)
  • A_v = 1 + R_f/R_1 với cấu hình không đảo nếu có khuếch đại


Thông cao bậc một

  • f_c = 1 / (2πRC)
  • roll-off = 20 dB/dec


10.4. Bộ lọc bậc hai
Sallen-Key

  • Rất phổ biến
  • Độ dốc:
      – 40 dB/dec cho bậc hai
Các đáp ứng:
  • Butterworth: biên độ phẳng trong băng thông
  • Có thể phải chọn tỉ số điện trở để đạt đáp ứng chuẩn


10.5. Dạng bài tập lọc tích cực
 1. Xác định bậc lọc
 2. Nhận dạng loại đáp ứng
 3. Tính f_c hoặc f_0
 4. Nếu đề yêu cầu Butterworth, dùng điều kiện hệ số khuếch đại hay tỉ số điện trở tương
    ứng
 5. Kiểm tra độ dốc:
      • bậc 1: 20 dB/dec
      • bậc 2: 40 dB/dec


11. Công thức trọng tâm cần học thuộc
11.1. Cơ sở
  • $Q = I\,t$
  • $I = \dfrac{\Delta Q}{\Delta t}$
  • $U = I R$
  • $P = U I$



  • X_C = 1/(2πfC)
  • $X_L = 2\pi f L$


11.2. Diode
  • I ≈ (V_S - 0.7)/R
  • V_D = V_γ + I_D.r_d


11.3. BJT
  • I_E = I_B + I_C
  • β = I_C/I_B
  • α = I_C/I_E
  • I_C = βI_B
  • r'_e ≈ 25mV/I_E


11.4. JFET/MOSFET
  • I_D = I_DSS (1 - V_GS/V_P)^2
  • A_v ≈ -g_m(R_D || R_L || r_d)


11.5. Op-Amp
  • A_CL = A_OL/(1 + A_OLβ)
  • Mạch đảo: A_v = -R_f/R_in
  • Mạch không đảo: A_v = 1 + R_f/R_1
  • Tích phân: V_out = -(1/RC) int(V_in dt)
  • Vi phân: V_out = -RC dV_in/dt


11.6. Lọc
  • f_c = 1/(2πRC)
  • A_v(dB) = 20log10(V_out/V_in)
  • f_0 = sqrt(f_L.f_H)
  • BW = f_H - f_L


12. Chiến lược học và làm bài thi
12.1. Khi gặp bài phân tích mạch
 1. Xác định mạch DC hay AC
 2. Xác định linh kiện đang làm việc ở chế độ nào
 3. Chọn mô hình phù hợp:
      • diode lý tưởng hay thực
      • BJT active/cutoff/saturation
      • JFET với Shockley
      • op-amp lý tưởng có hồi tiếp âm
 4. Viết công thức trước khi thay số
 5. Kiểm tra kết quả có hợp lý vật lý hay không


Nên gắn cách giải với hình minh họa:
  • diode: xác định ngay đang nằm ở vùng nào trên đặc tuyến
  • BJT: đặt điểm Q lên đường tải trước khi phân tích khuếch đại
  • JFET: dùng đồ thị truyền đạt để ước lượng I_D
  • op-amp: nhìn chiều hồi tiếp để phân biệt tuyến tính hay so sánh
  • bộ lọc: nhìn Bode để hiểu miền tần số qua và chặn trước khi thay số


12.2. Khi vẽ dạng sóng
  1. Xác định dạng tín hiệu vào
  2. Xác định mốc ngưỡng chuyển trạng thái
  3. Xét theo từng khoảng thời gian
  4. Đánh dấu mức bão hòa hoặc mức rơi áp diode


12.3. Sai lầm thường gặp
  • Quên kiểm tra giả thiết diode dẫn/ngắt
  • Dùng I_C = βI_B ngay cả khi BJT đã bão hòa
  • Quên V_BE ≈ 0.7V
  • Quên đưa nguồn DC về mass khi phân tích tín hiệu nhỏ
  • Áp dụng V+ = V- cho op-amp trong mạch không có hồi tiếp âm
  • Nhầm thông thấp với thông cao do chọn sai điểm lấy V_out


13. Phụ lục mô hình hóa trực quan
13.1. Danh sách hình đã sinh bằng Python
  • figures/01_signal_chain.png: sơ đồ khối hệ xử lý tín hiệu
  • figures/02_diode_vi_curve.png: đặc tuyến dòng áp diode
  • figures/03_rectifier_waveforms.png: dạng sóng chỉnh lưu bán kỳ và toàn kỳ
  • figures/04_bjt_load_line.png: đường tải DC và điểm Q
  • figures/05_bjt_regions.png: các vùng hoạt động của BJT
  • figures/06_jfet_transfer.png: đặc tuyến truyền đạt của JFET
  • figures/07_opamp_inverting_model.png: sơ đồ mô hình của mạch đảo op-amp
  • figures/08_opamp_comparator_waveform.png: dạng sóng vào ra của comparator
  • figures/09_rc_filter_bode.png: Bode thông thấp và thông cao
  • figures/10_bandpass_response.png: đáp ứng thông dải
  • figures/11_wien_oscillator_waveform.png: khởi động dao động cầu Wien
  • figures/12_active_filter_block.png: mô hình chức năng của lọc tích cực


13.2. Tái tạo lại toàn bộ hình
Lệnh chạy:
python3 scripts/generate_electronic_figures.py
Toàn bộ hình sẽ được sinh lại trong thư mục figures/.





14. Kết luận ngắn gọn theo từng chương
  • Chương diode: nắm bản chất P-N, đặc tuyến, mô hình và chỉnh lưu
  • Chương BJT: nắm vùng hoạt động, phân cực, điểm Q và ba cấu hình khuếch đại
  • Chương FET: nắm Shockley, bias và mạch CS
  • Chương op-amp: nắm hai quy tắc vàng, mạch đảo/không đảo, cộng trừ tích phân vi
    phân
  • Chương dao động: nắm điều kiện Barkhausen và cầu Wien
  • Chương lọc: nắm f_c, đồ thị Bode, phân biệt các loại lọc và lọc tích cực


15. Nguồn tổng hợp
  • Các slide trong Slide/
  • Các slide trong Slide_new/
  • File liên kết tham khảo: Slide/ElectronicDevicesLink.txt


Phần A. Câu hỏi trắc nghiệm
1. Kiến thức cơ bản
 1. Điện tích được tính theo công thức nào? A. Q = U/R B. $Q = I\,t$ C. Q = P.t D. Q = U.I
 2. Đơn vị của điện dung là: A. Henry B. Volt C. Farad D. Ohm
 3. Trong mạch DC xác lập, tụ điện lý tưởng được xem gần đúng là: A. Ngắn mạch B. Hở
    mạch C. Nguồn áp D. Nguồn dòng
 4. Công thức định luật Ohm là: A. $U = I R$ B. $P = U I$ C. $Q = I\,t$ D. I = U + R
 5. Trở kháng dung kháng được xác định bởi: A. X_C = 2πfC B. X_C = 1/(2πfC) C. X_C =
    R/C D. X_C = 2πRC

2. Bán dẫn và diode
 6. Trong bán dẫn loại N, hạt tải đa số là: A. Lỗ trống B. Ion âm C. Electron D. Photon
 7. Trong diode, cực P được gọi là: A. Cathode B. Anode C. Drain D. Gate
 8. Với diode Silicon, điện áp ngưỡng xấp xỉ là: A. 0.1V B. 0.3V C. 0.7V D. 1.5V
 9. Khi diode phân cực nghịch bình thường: A. Dẫn mạnh B. Dòng gần như bằng 0 C. Điện
    trở bằng 0 D. Tăng dòng tuyến tính
10. Mô hình diode lý tưởng xem diode thuận là: A. Hở mạch B. Biến áp C. Ngắn mạch D.
    Nguồn dòng
11. Chức năng nổi bật của diode Zener là: A. Khuếch đại dòng B. Dao động C. Ổn áp D.
    Cộng điện áp
12. Trong mạch chỉnh lưu toàn chu kỳ, tần số gợn sóng đầu ra bằng: A. f B. f/2 C. 2f D. 4f





3. BJT
13. BJT có ba cực: A. Anode, Cathode, Gate B. Drain, Gate, Source C. Emitter, Base, Collector
    D. Input, Output, Ground
14. Trong vùng active của BJT: A. I_C = 0 B. I_C = βI_B C. V_BE = 0 D. V_CE = 0
15. Quan hệ đúng là: A. I_B = I_C + I_E B. I_C = I_B + I_E C. I_E = I_B + I_C D.
    I_E = I_B - I_C
16. Khi transistor bão hòa: A. I_C luôn bằng βI_B B. V_CE rất nhỏ C. V_BE < 0 D. transistor
    ngắt
17. Điểm Q của transistor là: A. Điểm gãy trên đặc tuyến diode B. Điểm làm việc DC C.
    Điểm cộng hưởng D. Điểm ngắn mạch
18. Mạch khuếch đại CE có đặc điểm: A. Không đảo pha, A_v ≈ 1 B. Đảo pha 180 độ, khuếch
    đại áp lớn C. Trở vào rất nhỏ, không khuếch đại dòng D. Chỉ dùng cho dao động
19. Mạch khuếch đại CC có đặc điểm nổi bật: A. A_v rất lớn âm B. Trở vào nhỏ C. A_v gần
    bằng 1 D. Không khuếch đại dòng
20. Công thức gần đúng của điện trở emitter vi sai là: A. r'_e ≈ 25mV/I_E B. r'_e ≈
    I_E/25mV C. r'_e = β/I_C D. r'_e = V_CC/I_B

4. FET
21. JFET là linh kiện: A. Điều khiển bằng dòng B. Điều khiển bằng điện áp C. Điều khiển
    bằng công suất D. Không điều khiển được
22. Trong JFET, dòng vào cổng Gate lý tưởng là: A. Rất lớn B. Bằng dòng Drain C. Gần bằng
    0 D. Luôn âm
23. Phương trình Shockley của JFET là: A. I_D = βI_B B. I_D = I_DSS(1 - V_GS/V_P)^2
    C. I_D = V/R D. I_D = C.dv/dt
24. Cấu hình khuếch đại CS của FET tương tự với cấu hình nào của BJT? A. CE B. CC C. CB
    D. Darlington
25. MOSFET khác JFET ở điểm nổi bật là: A. Gate của MOSFET được cách điện bởi oxide B.
    MOSFET không có cực source C. JFET không có dòng drain D. MOSFET luôn là loại PNP


5. Op-Amp
26. Op-Amp lý tưởng có: A. Trở vào nhỏ, trở ra lớn B. Trở vào lớn, trở ra nhỏ C. Trở vào và
    trở ra đều nhỏ D. Trở vào và trở ra đều lớn
27. Trong chế độ tuyến tính có hồi tiếp âm: A. V+ = 0 B. V- = 0 C. V+ ≈ V- D. V_out = 0
28. Hệ số khuếch đại của mạch đảo là: A. A_v = R_f/R_in B. A_v = -R_f/R_in C. A_v =
    1 + R_f/R_in D. A_v = 0
29. Hệ số khuếch đại của mạch không đảo là: A. A_v = -R_f/R_1 B. A_v = 1 + R_f/R_1
    C. A_v = R_1/R_f D. A_v = -1
30. Mạch theo áp có hệ số khuếch đại gần: A. 0 B. 1 C. 10 D. vô cùng





31. CMRR thể hiện khả năng: A. Khuếch đại tín hiệu đồng pha B. Triệt tín hiệu đồng pha C.
    Tăng dòng bias D. Ổn áp nguồn
32. Mạch so sánh dùng op-amp thường làm việc ở: A. Vùng tuyến tính hẹp B. Vùng bão hòa
    đầu ra C. Vùng ngắt hoàn toàn D. Chỉ miền common mode
33. Mạch cộng đảo có đầu ra là: A. Tổng đại số có dấu âm của các đầu vào B. Hiệu của hai
    đầu vào C. Tích phân của đầu vào D. Đạo hàm của đầu vào
34. Mạch tích phân op-amp có đầu ra tỉ lệ với: A. Đạo hàm của đầu vào B. Tích phân của
    đầu vào C. Bình phương đầu vào D. Căn bậc hai đầu vào
35. Mạch vi phân op-amp có đầu ra tỉ lệ với: A. Tích phân của đầu vào B. Trung bình của
    đầu vào C. Đạo hàm của đầu vào D. Giá trị hiệu dụng


6. Dao động và lọc
36. Điều kiện Barkhausen để dao động ổn định là: A. |Aβ| = 0 B. |Aβ| = 1 C. |Aβ| > 10
    D. β = 0
37. Mạch cầu Wien thường dùng để tạo: A. Xung vuông công suất lớn B. Sóng sin tần số
    thấp C. Dòng DC ổn định D. Xung kim
38. Tần số cắt của mạch RC bậc một là: A. f_c = 2πRC B. f_c = 1/(2πRC) C. f_c =
    R/(2πC) D. f_c = C/(2πR)
39. Bộ lọc thông thấp cho qua tốt: A. Tần số cao B. Tần số thấp C. Chỉ một tần số duy nhất
    D. Không cho tín hiệu nào qua
40. Độ dốc suy giảm của bộ lọc bậc một xấp xỉ: A. 10 dB/dec B. 20 dB/dec C. 40 dB/dec
    D. 60 dB/dec
41. Bộ lọc Sallen-Key bậc hai có độ dốc xấp xỉ: A. 20 dB/dec B. 30 dB/dec C. 40 dB/dec
    D. 80 dB/dec
42. Butterworth là đáp ứng: A. Có gợn mạnh trong băng thông B. Phẳng trong băng thông
    C. Chỉ dùng cho mạch số D. Không phụ thuộc linh kiện


Phần B. Đáp án
 1. B
 2. C
 3. B
 4. A
 5. B
 6. C
 7. B
 8. C
 9. B
10. C
11. C
12. C
13. C
14. B


15. C
16. B
17. B
18. B
19. C
20. A
21. B
22. C
23. B
24. A
25. A
26. B
27. C
28. B
29. B
30. B
31. B
32. B
33. A
34. B
35. C
36. B
37. B
38. B
39. B
40. B
41. C
42. B


Phần C. Gợi ý ôn tập theo nhóm câu
 • Câu 1-5: công thức nền tảng, phần tử thụ động
 • Câu 6-12: bán dẫn, diode, chỉnh lưu, Zener
 • Câu 13-20: BJT, điểm Q, cấu hình khuếch đại
 • Câu 21-25: JFET, MOSFET, mô hình điều khiển bằng điện áp
 • Câu 26-35: op-amp, hồi tiếp âm và các ứng dụng
 • Câu 36-42: dao động, lọc thụ động và lọc tích cực





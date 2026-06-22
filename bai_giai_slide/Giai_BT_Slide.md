---
title: "Giai Bai Tap Slide Mach Dien Tu"
author: "Tong hop tu Slide va Slide_new"
lang: vi
mainfont: DejaVu Sans
monofont: Noto Sans Mono
geometry: margin=1.6cm
fontsize: 10pt
header-includes:
  - \usepackage{amsmath}
---

# Giai bai tap tu slide

Tài liệu này gồm các bài tập tính toán được lấy từ hai thư mục `Slide` và `Slide_new`. Ảnh bài tập được capture từ nội dung slide và đặt ngay trước lời giải. Các slide trùng nội dung giữa bộ cũ và bộ mới được gom một lần.

Lưu ý kỹ thuật: môi trường hiện tại không có LibreOffice để render PowerPoint nguyên bản, nên ảnh capture được dựng lại từ XML và media nhúng trong `.pptx`; nội dung, hình mạch và chữ trong slide được giữ theo nguồn, nhưng bố cục có thể không pixel-perfect như khi mở bằng PowerPoint.

## BT01 - Mạch điện một chiều RAB

![](bai_giai_slide/captures/bt01_dc_resistor.png){ width=94% }

*Nguon: slide 35 trong file PowerPoint goc.*

**Lời giải**

Do sơ đồ trong slide là mạng điện trở hỗn hợp, cách giải chuẩn là rút gọn từ phía xa nguồn về hai cực A-B.

1. Nhóm các điện trở nối tiếp: cộng trực tiếp $R_{nt} = R_{a} + R_{b} + ...$.
2. Nhóm các điện trở song song: dùng $R_{ss} = (R_{a} R_{b})/(R_{a} + R_{b})$ với 2 nhánh, hoặc $1/R_{ss} = \sum(1/R_{i})$ với nhiều nhánh.
3. Sau khi tìm được $R_{\,\mathrm{A}B}$, dòng nguồn là $I = U_{\,\mathrm{A}B}/R_{\,\mathrm{A}B}$.
4. Muốn tìm dòng qua một điện trở nhánh, dùng quy tắc chia dòng: $I_{k} = I_{branch} . R_{other}/(R_{k} + R_{other})$.
5. Muốn tìm áp trên một điện trở: $U_{R} = I_{R} R$.

Vì các ký hiệu nút/nhánh trong hình gốc rất nhỏ, phần đáp số nên kiểm lại trực tiếp trên slide PowerPoint khi phóng to. Công thức trên là quy trình thế số cho cả hai mạch a và b.


## BT02 - Mạch xoay chiều pha

![](bai_giai_slide/captures/bt02_ac_phasor.png){ width=94% }

*Nguon: slide 36 trong file PowerPoint goc.*

**Lời giải**

Đổi toàn bộ phần tử về trở kháng phức.

- Điện trở: $Z_{R} = R$.
- Tụ điện: $Z_{C} = 1/(jωC) = -j/(ωC)$.
- Cuộn cảm: $Z_{L} = jωL$.

Sau đó rút gọn mạch theo nối tiếp/song song để có $Z_{eq}$. Dòng tổng:

$I = E/Z_{eq}$.

Dòng nhánh:

$I_{1} = \,\mathrm{V}_{branch}/Z_{1}$, $I_{2} = \,\mathrm{V}_{branch}/Z_{2}$.

Công suất trung bình do nguồn phát ra và trên điện trở:

$P = Re{E I*}$ và $P_{R} = I_{R}^2 R$ với giá trị hiệu dụng. Nếu chỉ có điện trở tiêu tán công suất thật thì $P_{source} = \sum P_{R}$; tụ/cuộn cảm lý tưởng chỉ trao đổi công suất phản kháng.


## BT03 - Tương đương Thevenin

![](bai_giai_slide/captures/bt03_thevenin.png){ width=94% }

*Nguon: slide 37 trong file PowerPoint goc.*

**Lời giải**

Để tìm dòng `I` qua tải bằng Thevenin:

1. Tháo tải tại hai cực cần xét.
2. Tính điện áp hở mạch $\,\mathrm{V}_{Th}$ giữa hai cực đó.
3. Triệt tiêu nguồn độc lập để tìm $R_{Th}$: nguồn áp ngắn mạch, nguồn dòng hở mạch.
4. Lắp lại tải $R_{L}$: $I = \,\mathrm{V}_{Th}/(R_{Th} + R_{L})$.

Nếu mạch có nguồn phụ thuộc, không triệt tiêu nguồn phụ thuộc. Khi đó đặt nguồn thử $\,\mathrm{V}_{x}$ hoặc $I_{x}$ tại cửa ra rồi dùng $R_{Th} = \,\mathrm{V}_{x}/I_{x}$.


## BT04 - Dạng sóng chỉnh lưu

![](bai_giai_slide/captures/bt04_rectifier_wave.png){ width=94% }

*Nguon: slide 34 trong file PowerPoint goc.*

**Lời giải**

Với mô hình diode thực, mỗi diode dẫn bị sụt khoảng $\,\mathrm{V}_{D} = 0.7 \,\mathrm{V}$.

- Mạch chỉnh lưu bán kỳ: chỉ giữ nửa chu kỳ làm diode phân cực thuận. Đỉnh ra xấp xỉ $\,\mathrm{V}_{om} = \,\mathrm{V}_{im} - \,\mathrm{V}_{D}$.
- Mạch chỉnh lưu toàn kỳ cầu: mỗi nửa chu kỳ có 2 diode dẫn, nên $\,\mathrm{V}_{om} = \,\mathrm{V}_{im} - 2\,\mathrm{V}_{D}$.
- Sai số tương đối do sụt áp diode: $ε = (n \,\mathrm{V}_{D} / \,\mathrm{V}_{im}) . 100\%$, với $n = 1$ cho bán kỳ một diode, $n = 2$ cho cầu chỉnh lưu.

Kết luận: khi $\,\mathrm{V}_{im}$ lớn hơn nhiều so với $\,\mathrm{V}_{D}$, sai số nhỏ và có thể bỏ qua mô hình thực để tính nhanh.


## BT05 - PIV cầu chỉnh lưu

![](bai_giai_slide/captures/bt05_piv.png){ width=94% }

*Nguon: slide 36 trong file PowerPoint goc.*

**Lời giải**

Máy biến áp có tỉ số `10:1`, nên điện áp thứ cấp bằng $1/10$ điện áp sơ cấp theo cùng loại giá trị đo.

Với cầu chỉnh lưu, diode không dẫn phải chịu xấp xỉ đỉnh điện áp thứ cấp:

$PI\,\mathrm{V}_{bridge} \approx \,\mathrm{V}_{s}(peak)$.

Nếu điện áp vào sơ cấp trong hình là giá trị hiệu dụng $\,\mathrm{V}_{p}(rms)$, thì:

$\,\mathrm{V}_{s}(rms) = \,\mathrm{V}_{p}(rms)/10$,
$\,\mathrm{V}_{s}(peak) = \sqrt{2} \,\mathrm{V}_{s}(rms)$,
$PI\,\mathrm{V} \approx \,\mathrm{V}_{s}(peak)$.

Chọn diode thực tế có định mức PIV lớn hơn giá trị tính được ít nhất 2 lần để có biên an toàn.


## BT06 - Hệ số nhấp nhô nguồn DC

![](bai_giai_slide/captures/bt06_ripple.png){ width=94% }

*Nguon: slide 41 trong file PowerPoint goc.*

**Lời giải**

Với chỉnh lưu cầu có tụ lọc, tần số nhấp nhô là $f_{r} = 2f_{line}$.

1. Đỉnh điện áp trên tụ: $\,\mathrm{V}_{p} \approx \,\mathrm{V}_{s}(peak) - 2\,\mathrm{V}_{D}$ vì cầu có 2 diode dẫn.
2. Dòng tải xấp xỉ: $I_{L} \approx \,\mathrm{V}_{DC}/R_{L}$.
3. Điện áp nhấp nhô đỉnh-đỉnh: $\,\mathrm{V}_{r}(pp) \approx I_{L}/(f_{r} C)$.
4. Giá trị hiệu dụng của thành phần nhấp nhô tam giác: $\,\mathrm{V}_{r}(rms) = \,\mathrm{V}_{r}(pp)/(2\sqrt{3})$.
5. Hệ số nhấp nhô: $r = \,\mathrm{V}_{r}(rms)/\,\mathrm{V}_{DC}$.

Với diode 1N4001, dùng $\,\mathrm{V}_{D} = 0.7 \,\mathrm{V}$. Nếu muốn giảm `r`, tăng `C`, tăng $R_{L}$, hoặc dùng chỉnh lưu toàn kỳ để tăng $f_{r}$.


## BT07 - Ổn áp Zener

![](bai_giai_slide/captures/bt07_zener.png){ width=94% }

*Nguon: slide 47 trong file PowerPoint goc.*

**Lời giải**

Khi Zener làm việc trong vùng đánh thủng ổn áp, điện áp ra xấp xỉ bằng điện áp Zener:

$\,\mathrm{V}_{OUT} \approx \,\mathrm{V}_{Z}$.

Dòng qua điện trở hạn dòng:

$I_{R} = (\,\mathrm{V}_{IN} - \,\mathrm{V}_{Z})/R$.

Nếu có tải $R_{L}$, dòng tải $I_{L} = \,\mathrm{V}_{Z}/R_{L}$, dòng Zener $I_{Z} = I_{R} - I_{L}$. Điều kiện ổn áp đúng là:

$I_{Z}(min) \le I_{Z} \le I_{Z}(max)$.

Từ hình, thay trực tiếp giá trị `R`, mã diode Zener và thang trục đặc tuyến để lấy $\,\mathrm{V}_{Z}$. Điện áp vào tối thiểu để bắt đầu ổn áp là $\,\mathrm{V}_{IN}(min) = \,\mathrm{V}_{Z} + R(I_{L} + I_{Z}(min))$.


## BT08 - BJT DC bài 1

![](bai_giai_slide/captures/bt08_bjt_dc_1.png){ width=94% }

*Nguon: slide 16 trong file PowerPoint goc.*

**Lời giải**

Dữ kiện: $\,\mathrm{V}_{BE} = 0.7 \,\mathrm{V}$, $\beta  = 90$, $R_{B} = 22 \,\mathrm{k\Omega}$, $R_{C} = 220 \Omega$, $\,\mathrm{V}_{BB} = 6 \,\mathrm{V}$, $\,\mathrm{V}_{CC} = 9 \,\mathrm{V}$.

$I_{B} = (\,\mathrm{V}_{BB} - \,\mathrm{V}_{BE})/R_{B} = (6 - 0.7)/22k = 0.240 \,\mathrm{mA}$.

$I_{C} = \beta  I_{B} = 90 . 0.240 = 21.6 \,\mathrm{mA}$.

$I_{E} = I_{C} + I_{B} = 21.84 \,\mathrm{mA}$.

$\,\mathrm{V}_{CE} = \,\mathrm{V}_{CC} - I_{C} R_{C} = 9 - 21.6\,\mathrm{mA} . 220 = 4.25 \,\mathrm{V}$.

$\,\mathrm{V}_{CB} = \,\mathrm{V}_{CE} - \,\mathrm{V}_{BE} = 4.25 - 0.7 = 3.55 \,\mathrm{V}$.

Đáp số: $I_{B} = 0.24 \,\mathrm{mA}$, $I_{C} = 21.6 \,\mathrm{mA}$, $I_{E} = 21.84 \,\mathrm{mA}$, $\,\mathrm{V}_{CE} = 4.25 \,\mathrm{V}$, $\,\mathrm{V}_{CB} = 3.55 \,\mathrm{V}$.


## BT09 - BJT DC bài 2

![](bai_giai_slide/captures/bt09_bjt_dc_2.png){ width=94% }

*Nguon: slide 18 trong file PowerPoint goc.*

**Lời giải**

Dữ kiện như bài trước nhưng $\,\mathrm{V}_{BB} = 9 \,\mathrm{V}$.

$I_{B} = (9 - 0.7)/22k = 0.377 \,\mathrm{mA} \approx 0.38 \,\mathrm{mA}$.

$I_{C} = \beta  I_{B} = 90 . 0.377 = 34.0 \,\mathrm{mA}$.

$I_{E} = I_{C} + I_{B} \approx 34.37 \,\mathrm{mA}$.

$\,\mathrm{V}_{CE} = 9 - 34.0\,\mathrm{mA} . 220 = 1.53 \,\mathrm{V}$.

$\,\mathrm{V}_{CB} = \,\mathrm{V}_{CE} - \,\mathrm{V}_{BE} = 1.53 - 0.7 = 0.83 \,\mathrm{V}$.

Transistor vẫn còn gần vùng tuyến tính vì $\,\mathrm{V}_{CE}$ chưa về 0.


## BT10 - BJT bão hòa

![](bai_giai_slide/captures/bt10_bjt_saturation.png){ width=94% }

*Nguon: slide 19 trong file PowerPoint goc.*

**Lời giải**

Dữ kiện như bài trước nhưng $\,\mathrm{V}_{BB} = 10.7 \,\mathrm{V}$.

Theo công thức tuyến tính:

$I_{B} = (10.7 - 0.7)/22k = 0.455 \,\mathrm{mA}$.

$I_{C},lin = \beta  I_{B} = 40.9 \,\mathrm{mA}$.

Nếu dùng $R_{C} = 220 \Omega$, dòng cực đại mà mạch collector cho phép xấp xỉ:

$I_{C}(sat) \approx \,\mathrm{V}_{CC}/R_{C} = 9/220 = 40.9 \,\mathrm{mA}$.

Vì dòng tính toán đã chạm giới hạn tải, transistor vào bão hòa. Khi đó slide lấy $\,\mathrm{V}_{CE} \approx 0 \,\mathrm{V}$, nên:

$I_{E} \approx I_{C} + I_{B} = 41.35 \,\mathrm{mA}$,
$\,\mathrm{V}_{CB} = \,\mathrm{V}_{CE} - \,\mathrm{V}_{BE} = -0.7 \,\mathrm{V}$.


## BT11 - Phân cực cầu chia áp lý tưởng

![](bai_giai_slide/captures/bt11_bjt_divider_ideal.png){ width=94% }

*Nguon: slide 41 trong file PowerPoint goc.*

**Lời giải**

Giả thiết $I_{B}$ rất nhỏ so với dòng qua $R_{2}$, nên cầu chia áp không bị tải bởi cực B.

1. Điện áp base: $\,\mathrm{V}_{B} = \,\mathrm{V}_{CC} . R_{2}/(R_{1} + R_{2})$.
2. Điện áp emitter: $\,\mathrm{V}_{E} = \,\mathrm{V}_{B} - \,\mathrm{V}_{BE}$.
3. Dòng emitter: $I_{E} = \,\mathrm{V}_{E}/R_{E}$.
4. Với $\beta $ lớn, $I_{C} \approx I_{E}$.
5. Điện áp collector-emitter: $\,\mathrm{V}_{CE} = \,\mathrm{V}_{CC} - I_{C} R_{C} - I_{E} R_{E}$.

Theo đáp số trên slide: $I_{C} \approx 5.16 \,\mathrm{mA}$, $\,\mathrm{V}_{CE} \approx 1.95 \,\mathrm{V}$.


## BT12 - Phân cực cầu chia áp có IB

![](bai_giai_slide/captures/bt12_bjt_thevenin.png){ width=94% }

*Nguon: slide 42 trong file PowerPoint goc.*

**Lời giải**

Thay cầu chia áp $R_{1}, R_{2}$ nhìn từ cực B bằng Thevenin:

$U_{Th} = \,\mathrm{V}_{CC} . R_{2}/(R_{1} + R_{2})$,
$R_{Th} = R_{1} \parallel R_{2}$.

Dòng base:

$I_{B} = (U_{Th} - \,\mathrm{V}_{BE})/(R_{Th} + (\beta +1)R_{E})$.

Sau đó:

$I_{C} = \beta  I_{B}$,
$I_{E} = (\beta +1)I_{B}$,
$\,\mathrm{V}_{CE} = \,\mathrm{V}_{CC} - I_{C} R_{C} - I_{E} R_{E}$.

Theo đáp số trên slide: $U_{Th} = 3.59 \,\mathrm{V}$, $R_{Th} = 3.59 \,\mathrm{k\Omega}$, $I_{C} = 4.85 \,\mathrm{mA}$, $\,\mathrm{V}_{CE} = 2.43 \,\mathrm{V}$.


## BT13 - Khuếch đại CE tín hiệu lớn

![](bai_giai_slide/captures/bt13_ce_dc.png){ width=94% }

*Nguon: slide 4 trong file PowerPoint goc.*

**Lời giải**

Bài này yêu cầu điểm làm việc DC của mạch CE.

Quy trình:

1. Tụ ghép và tụ bypass hở mạch ở DC.
2. Quy đổi cầu phân áp base sang Thevenin: $\,\mathrm{V}_{Th}$, $R_{Th}$.
3. Tính $I_{B} = (\,\mathrm{V}_{Th} - \,\mathrm{V}_{BE})/(R_{Th} + (\beta +1)R_{E})$.
4. Tính $I_{C} = \beta  I_{B}$, $I_{E} = (\beta +1)I_{B}$.
5. Tính $\,\mathrm{V}_{E} = I_{E} R_{E}$, $\,\mathrm{V}_{B} = \,\mathrm{V}_{E} + 0.7$, $\,\mathrm{V}_{C} = \,\mathrm{V}_{CC} - I_{C} R_{C}$.
6. Kiểm tra vùng hoạt động: $\,\mathrm{V}_{CE} = \,\mathrm{V}_{C} - \,\mathrm{V}_{E}$. Nếu $\,\mathrm{V}_{CE} > 0.2 \,\mathrm{V}$, transistor chưa bão hòa.

Các công thức này thay trực tiếp các giá trị trên hình để ra $I_{E}, I_{C}, \,\mathrm{V}_{E}, \,\mathrm{V}_{B}, \,\mathrm{V}_{C}$.


## BT14 - Khuếch đại CE tín hiệu nhỏ

![](bai_giai_slide/captures/bt14_ce_ac.png){ width=94% }

*Nguon: slide 5 trong file PowerPoint goc.*

**Lời giải**

Ở miền AC trung tần: nguồn DC nối đất AC, tụ ghép xem như ngắn mạch, tụ bypass emitter nếu đủ lớn cũng xem như ngắn mạch.

1. Tính điện trở emitter vi sai: $r_{e} \approx 26m\,\mathrm{V}/I_{E}$.
2. Trở vào tại base: $R_{in}(base) \approx \beta  r_{e}$ nếu emitter được bypass; nếu không bypass thì $R_{in}(base) \approx \beta (r_{e} + R_{E})$.
3. Trở vào toàn mạch: $R_{in} = R_{1} \parallel R_{2} \parallel R_{in}(base)$.
4. Độ lợi áp CE có bypass emitter: $\,\mathrm{A}_{v} \approx -R_{C}/r_{e}$ hoặc $\,\mathrm{A}_{v} \approx -(R_{C} \parallel R_{L})/r_{e}$ khi có tải.
5. Độ lợi dòng: $\,\mathrm{A}_{i} = i_{o}/i_{i}$.
6. Độ lợi công suất: $\,\mathrm{A}_{p} = |\,\mathrm{A}_{v} \,\mathrm{A}_{i}|$.

Dấu âm của $\,\mathrm{A}_{v}$ thể hiện tín hiệu ra đảo pha 180 độ so với tín hiệu vào.


## BT15 - E-MOSFET phân cực 1

![](bai_giai_slide/captures/bt15_emosfet_1.png){ width=94% }

*Nguon: slide 39 trong file PowerPoint goc.*

**Lời giải**

Với E-MOSFET:

$I_{D} = K(\,\mathrm{V}_{GS} - \,\mathrm{V}_{GS}(th))^2$,
$K = I_{D}(on)/(\,\mathrm{V}_{GS}(on) - \,\mathrm{V}_{GS}(th))^2$.

Dữ kiện: $I_{D}(on)=200 \,\mathrm{mA}$, $\,\mathrm{V}_{GS}(on)=4 \,\mathrm{V}$, $\,\mathrm{V}_{GS}(th)=2 \,\mathrm{V}$.

$K = 0.2/(4-2)^2 = 0.05 \,\mathrm{A}/\,\mathrm{V}^2$.

Từ hình, tính $\,\mathrm{V}_{G} = \,\mathrm{V}_{DD} . R_{2}/(R_{1}+R_{2})$. Vì gate gần như không hút dòng, $\,\mathrm{V}_{GS} = \,\mathrm{V}_{G}$ nếu source nối đất.

Sau đó:

$I_{D} = 0.05(\,\mathrm{V}_{GS} - 2)^2$,
$\,\mathrm{V}_{DS} = \,\mathrm{V}_{DD} - I_{D} R_{D}$.

Nếu $\,\mathrm{V}_{DS} \ge \,\mathrm{V}_{GS} - \,\mathrm{V}_{th}$, MOSFET ở vùng bão hòa/khuếch đại và phép tính hợp lệ.


## BT16 - E-MOSFET phân cực 2

![](bai_giai_slide/captures/bt16_emosfet_2.png){ width=94% }

*Nguon: slide 40 trong file PowerPoint goc.*

**Lời giải**

Voltmeter trong hình đo điện áp tại cực gate/source theo sơ đồ. Nếu giá trị đo là `5 V` và source nối đất thì:

$\,\mathrm{V}_{GS} = 5 \,\mathrm{V}$.

Dùng lại hằng số từ dữ kiện transistor:

$K = I_{D}(on)/(\,\mathrm{V}_{GS}(on)-\,\mathrm{V}_{th})^2$.

Sau đó:

$I_{D} = K(5 - \,\mathrm{V}_{th})^2$,
$\,\mathrm{V}_{DS} = \,\mathrm{V}_{DD} - I_{D} R_{D}$ nếu source nối đất; nếu có $R_{S}$ thì $\,\mathrm{V}_{DS} = \,\mathrm{V}_{DD} - I_{D}(R_{D} + R_{S})$.

Cuối cùng kiểm tra điều kiện vùng bão hòa: $\,\mathrm{V}_{DS} \ge \,\mathrm{V}_{GS} - \,\mathrm{V}_{th}$.


## BT17 - JFET bài 1

![](bai_giai_slide/captures/bt17_jfet_1.png){ width=94% }

*Nguon: slide 1 trong file PowerPoint goc.*

**Lời giải**

Dữ kiện: $I_{DSS} = 1.65 \,\mathrm{mA}$, $\,\mathrm{V}_{PO} = 2 \,\mathrm{V}$. Điều kiện đề cho:

$\,\mathrm{V}_{GS} + \,\mathrm{V}_{PO} = 0.63$ nên $\,\mathrm{V}_{GS} = 0.63 - 2 = -1.37 \,\mathrm{V}$.

Dùng phương trình Shockley với $\,\mathrm{V}_{P} = -2 \,\mathrm{V}$:

$I_{D} = I_{DSS}(1 - \,\mathrm{V}_{GS}/\,\mathrm{V}_{P})^2$
$= 1.65\,\mathrm{mA}(1 - (-1.37)/(-2))^2$
$= 1.65\,\mathrm{mA}(0.315)^2 \approx 0.164 \,\mathrm{mA}$.

Hệ số truyền dẫn:

$g_{m0} = 2I_{DSS}/|\,\mathrm{V}_{P}| = 2(1.65\,\mathrm{mA})/2 = 1.65 \,\mathrm{mS}$,
$g_{m} = g_{m0}(1 - \,\mathrm{V}_{GS}/\,\mathrm{V}_{P}) = 1.65\,\mathrm{mS} . 0.315 \approx 0.52 \,\mathrm{mS}$.


## BT18 - JFET 2N5458

![](bai_giai_slide/captures/bt18_jfet_2.png){ width=94% }

*Nguon: slide 2 trong file PowerPoint goc.*

**Lời giải**

Dòng rỉ gate tạo ra áp phân cực trên $R_{G}$:

$\,\mathrm{V}_{GS} \approx -I_{GS} R_{G} = -(1n\,\mathrm{A})(100\,\mathrm{M\Omega}) = -0.1 \,\mathrm{V}$.

Vì $\,\mathrm{V}_{GS}$ nhỏ, dòng drain gần với dải $I_{DSS}$ của linh kiện. Với $R_{D} = 2 \,\mathrm{k\Omega}$, $\,\mathrm{V}_{DD} = 20 \,\mathrm{V}$:

- Nếu $I_{D} = 2 \,\mathrm{mA}$: $\,\mathrm{V}_{DS} \approx 20 - 2\,\mathrm{mA} . 2k = 16 \,\mathrm{V}$.
- Nếu $I_{D} = 9 \,\mathrm{mA}$: $\,\mathrm{V}_{DS} \approx 20 - 9\,\mathrm{mA} . 2k = 2 \,\mathrm{V}$.

Độ lợi điện áp gần đúng:

$\,\mathrm{A}_{\,\mathrm{V}} \approx -g_{m} R_{D}$.

Với $g_{m} = 1500 \mu S$: $\,\mathrm{A}_{\,\mathrm{V}} \approx -0.0015 . 2000 = -3$.
Với $g_{m} = 5000 \mu S$: $\,\mathrm{A}_{\,\mathrm{V}} \approx -0.005 . 2000 = -10$.

Vì vậy độ lợi nằm khoảng $-3$ đến $-10$, tùy mẫu JFET cụ thể.


## BT19 - JFET điểm tĩnh và Av

![](bai_giai_slide/captures/bt19_jfet_3.png){ width=94% }

*Nguon: slide 3 trong file PowerPoint goc.*

**Lời giải**

Dữ kiện: $I_{DSS} = 10 \,\mathrm{mA}$, $\,\mathrm{V}_{P} = -4 \,\mathrm{V}$, $\,\mathrm{V}_{GS} = -1 \,\mathrm{V}$, $R_{D} = 1.5 \,\mathrm{k\Omega}$, $\,\mathrm{V}_{DD} = 15 \,\mathrm{V}$, $\,\mathrm{V}_{i} = 20 m\,\mathrm{V}$.

Dòng tĩnh:

$I_{DQ} = 10\,\mathrm{mA}(1 - (-1)/(-4))^2 = 10\,\mathrm{mA}(0.75)^2 = 5.625 \,\mathrm{mA}$.

Điện áp drain-source nếu source nối đất:

$\,\mathrm{V}_{DSQ} = \,\mathrm{V}_{DD} - I_{D} R_{D} = 15 - 5.625\,\mathrm{mA} . 1.5k = 6.56 \,\mathrm{V}$.

Hệ số truyền dẫn:

$g_{m0} = 2I_{DSS}/|\,\mathrm{V}_{P}| = 5 \,\mathrm{mS}$,
$g_{m} = g_{m0}(1 - \,\mathrm{V}_{GS}/\,\mathrm{V}_{P}) = 5\,\mathrm{mS} . 0.75 = 3.75 \,\mathrm{mS}$.

Độ lợi áp:

$\,\mathrm{A}_{\,\mathrm{V}} \approx -g_{m} R_{D} = -3.75\,\mathrm{mS} . 1.5k = -5.625$.

Điện áp ra nhỏ-signal:

$v_{o} = \,\mathrm{A}_{\,\mathrm{V}} v_{i} = -5.625 . 20m\,\mathrm{V} = -112.5 m\,\mathrm{V}$.


## BT20 - JFET phân áp có tải

![](bai_giai_slide/captures/bt20_jfet_4.png){ width=94% }

*Nguon: slide 4 trong file PowerPoint goc.*

**Lời giải**

Điện áp gate từ cầu phân áp:

$\,\mathrm{V}_{G} = 24 . 1/(5.6+1) = 3.64 \,\mathrm{V}$.

Với $I_{DQ} = 2.5 \,\mathrm{mA}$, $R_{S} = 2.7 \,\mathrm{k\Omega}$:

$\,\mathrm{V}_{S} = I_{D} R_{S} = 6.75 \,\mathrm{V}$,
$\,\mathrm{V}_{GSQ} = \,\mathrm{V}_{G} - \,\mathrm{V}_{S} = -3.11 \,\mathrm{V}$.

Điện áp drain:

$\,\mathrm{V}_{D} = 24 - I_{D} R_{D} = 24 - 2.5\,\mathrm{mA} . 2.7k = 17.25 \,\mathrm{V}$,
$\,\mathrm{V}_{DSQ} = \,\mathrm{V}_{D} - \,\mathrm{V}_{S} = 10.5 \,\mathrm{V}$.

Không tải, với $r_{d} = 100 \,\mathrm{k\Omega}$:

$R_{D}' = R_{D} \parallel r_{d} \approx 2.63 \,\mathrm{k\Omega}$,
$\,\mathrm{A}_{\,\mathrm{V}} \approx -g_{m} R_{D}'/(1 + g_{m} R_{S}) = -0.003 . 2629/(1 + 0.003 . 2700) \approx -0.87$.

$Z_{i} = R_{1} \parallel R_{2} \approx 848 \,\mathrm{k\Omega}$, $Z_{o} \approx R_{D} \parallel r_{d} \approx 2.63 \,\mathrm{k\Omega}$.

Khi có $R_{L} = 10 \,\mathrm{k\Omega}$ và $R_{sig} = 100 \,\mathrm{k\Omega}$:

$R_{D}'' = R_{D} \parallel r_{d} \parallel R_{L} \approx 2.08 \,\mathrm{k\Omega}$,
$\,\mathrm{A}_{\,\mathrm{V}},circuit \approx -0.69$,
$\,\mathrm{A}_{\,\mathrm{V}},total \approx \,\mathrm{A}_{\,\mathrm{V}} . Z_{i}/(Z_{i}+R_{sig}) \approx -0.69 . 0.895 \approx -0.62$.


## BT21 - JFET phân áp bài 6

![](bai_giai_slide/captures/bt21_jfet_6.png){ width=94% }

*Nguon: slide 6 trong file PowerPoint goc.*

**Lời giải**

Cầu phân áp gate:

$\,\mathrm{V}_{G} = 18 . 10/(110+10) = 1.5 \,\mathrm{V}$.

Với $R_{S} = 750 \Omega$, đặt $I_{D}$ theo mA thì:

$\,\mathrm{V}_{GS} = \,\mathrm{V}_{G} - I_{D} R_{S} = 1.5 - 0.75I_{D}$.

Phương trình Shockley:

$I_{D} = 6(1 - \,\mathrm{V}_{GS}/(-3))^2$.

Thay $\,\mathrm{V}_{GS}$ vào:

$I_{D} = 6(1.5 - 0.25I_{D})^2$.

Giải phương trình cho nghiệm vật lý trong khoảng $0 \le I_{D} \le I_{DSS}$:

$I_{DQ} \approx 3.12 \,\mathrm{mA}$.

$\,\mathrm{V}_{GSQ} = 1.5 - 0.75 . 3.12 \approx -0.84 \,\mathrm{V}$.

$\,\mathrm{V}_{DS} = 18 - I_{D}(R_{D} + R_{S}) = 18 - 3.12\,\mathrm{mA}(1.8k + 0.75k) \approx 10.05 \,\mathrm{V}$.


## BT22 - Op-Amp vòng hở

![](bai_giai_slide/captures/bt22_opamp_open_loop.png){ width=94% }

*Nguon: slide 18 trong file PowerPoint goc.*

**Lời giải**

Điện áp vi sai:

$v_{d} = \,\mathrm{V}_+ - \,\mathrm{V}_- = 100 sin(2\pi t) \mu \,\mathrm{V}$.

Khuếch đại vòng hở:

$v_{o},lin = \,\mathrm{A} v_{d} = 10^5 . 100\mu \,\mathrm{V} sin(2\pi t) = 10 sin(2\pi t) \,\mathrm{V}$.

Nhưng nguồn cấp chỉ `±5 V` nên đầu ra bị giới hạn:

$v_{out} = +5 \,\mathrm{V}$ khi $10 sin(2\pi t) > 5$,
$v_{out} = -5 \,\mathrm{V}$ khi $10 sin(2\pi t) < -5$,
$v_{out} = 10 sin(2\pi t)$ ở đoạn còn lại.

Đỉnh-đỉnh thực tế xấp xỉ `10 Vpp`. Dạng sóng là sin bị cắt đỉnh ở `±5 V`.


## BT23 - Chứng minh gain đảo/không đảo

![](bai_giai_slide/captures/bt23_opamp_gain_proof.png){ width=94% }

*Nguon: slide 10 trong file PowerPoint goc.*

**Lời giải**

Giả thiết Op-Amp lý tưởng có hồi tiếp âm: $\,\mathrm{V}_+ = \,\mathrm{V}_-$ và dòng vào hai cổng bằng 0.

Mạch đảo:

$\,\mathrm{V}_+ = 0$ nên $\,\mathrm{V}_- \approx 0$ là mass ảo. Dòng qua $R_{i}$ bằng dòng qua $R_{f}$:

$\,\mathrm{V}_{in}/R_{i} = -\,\mathrm{V}_{out}/R_{f}$.

Suy ra:

$\,\mathrm{A}_{cl}(I) = \,\mathrm{V}_{out}/\,\mathrm{V}_{in} = -R_{f}/R_{i}$.

Mạch không đảo:

$\,\mathrm{V}_+ = \,\mathrm{V}_{in}$, nên $\,\mathrm{V}_- = \,\mathrm{V}_{in}$. Cầu chia áp hồi tiếp cho:

$\,\mathrm{V}_- = \,\mathrm{V}_{out} . R_{i}/(R_{i} + R_{f})$.

Suy ra:

$\,\mathrm{V}_{in} = \,\mathrm{V}_{out} . R_{i}/(R_{i} + R_{f})$,
$\,\mathrm{A}_{cl}(NI) = \,\mathrm{V}_{out}/\,\mathrm{V}_{in} = 1 + R_{f}/R_{i}$.


## BT24 - Tính Rf theo Acl

![](bai_giai_slide/captures/bt24_opamp_rf.png){ width=94% }

*Nguon: slide 22 trong file PowerPoint goc.*

**Lời giải**

Công thức đóng vòng:

- Không đảo: $\,\mathrm{A}_{cl}(NI) = 1 + R_{f}/R_{i}$ nên $R_{f} = (\,\mathrm{A}_{cl} - 1)R_{i}$.
- Đảo: $\,\mathrm{A}_{cl}(I) = -R_{f}/R_{i}$; nếu dùng độ lớn $|\,\mathrm{A}_{cl}|$ thì $R_{f} = |\,\mathrm{A}_{cl}|R_{i}$.

Cách làm từng mạch trong hình:

1. Xác định mạch đảo hay không đảo theo chân nhận tín hiệu.
2. Đọc $R_{i}$ và hệ số khuếch đại yêu cầu trên hình.
3. Thay vào công thức tương ứng.
4. Kiểm tra dấu: mạch đảo cho đầu ra ngược pha, mạch không đảo cho đầu ra cùng pha.


## BT25 - Op-Amp so sánh bài 1-2

![](bai_giai_slide/captures/bt25_comparator_1_2.png){ width=94% }

*Nguon: slide 3 trong file PowerPoint goc.*

**Lời giải**

Bài 1:

$\,\mathrm{V}_{o} = \,\mathrm{A}_{OL} \,\mathrm{V}_{d} = 80000 . 0.15m\,\mathrm{V} = 12 \,\mathrm{V}$.

Vì đầu ra tối đa là `±12 V`, tín hiệu ra chạm mức bão hòa. Nếu xét biên độ hai cực thì:

$\,\mathrm{V}_{o}(p-p) = 2 . 12 = 24 \,\mathrm{\,\mathrm{V}pp}$.

Bài 2:

Với mạch so sánh lý tưởng:

- Nếu $\,\mathrm{V}_+ > \,\mathrm{V}_-$ thì $\,\mathrm{V}_{out} = +\,\mathrm{V}_{sat}$.
- Nếu $\,\mathrm{V}_+ < \,\mathrm{V}_-$ thì $\,\mathrm{V}_{out} = -\,\mathrm{V}_{sat}$.

Đọc từng hình trong slide: so sánh mức tín hiệu đặt ở chân $+$ và chân $-$, sau đó gán đầu ra về rail dương hoặc rail âm tương ứng.


## BT26 - Schmitt trigger

![](bai_giai_slide/captures/bt26_schmitt_1.png){ width=94% }

*Nguon: slide 4 trong file PowerPoint goc.*

**Lời giải**

Mạch dùng hồi tiếp dương nên có hai ngưỡng chuyển trạng thái.

Với cấu hình không đảo thường gặp, điện áp tại chân so sánh là phần chia của đầu ra:

$\,\mathrm{V}_{ref} = \beta  \,\mathrm{V}_{out}$, với $\beta  = R_{2}/(R_{1}+R_{2})$ nếu $R_{2}$ nối về mass.

Do đó:

$UTP = +\beta \,\mathrm{V}_{sat}$,
$LTP = -\beta \,\mathrm{V}_{sat}$.

Nếu có điện áp chuẩn khác 0, cộng thêm thành phần offset do nguồn chuẩn tạo ra. Dạng sóng ra là sóng vuông: khi tín hiệu vào vượt `UTP`, đầu ra đổi trạng thái; khi tín hiệu giảm xuống dưới `LTP`, đầu ra đổi ngược lại.


## BT27 - Mạch cộng đảo 1

![](bai_giai_slide/captures/bt27_summing_1.png){ width=94% }

*Nguon: slide 8 trong file PowerPoint goc.*

**Lời giải**

Mạch (a): $R_{f} = R_{1} = R_{2} = 10 \,\mathrm{k\Omega}$, $\,\mathrm{V}_{1} = 1 \,\mathrm{V}$, $\,\mathrm{V}_{2} = 1.5 \,\mathrm{V}$.

$\,\mathrm{V}_{out} = -R_{f}(\,\mathrm{V}_{1}/R_{1} + \,\mathrm{V}_{2}/R_{2}) = -(1 + 1.5) = -2.5 \,\mathrm{V}$.

Mạch (b): $R_{f} = 22 \,\mathrm{k\Omega}$, ba điện trở vào đều $10 \,\mathrm{k\Omega}$, các nguồn `0.1 V`, `1 V`, `0.5 V`.

$\,\mathrm{V}_{out} = -22k[(0.1/10k) + (1/10k) + (0.5/10k)]$
$= -2.2(1.6) = -3.52 \,\mathrm{V}$.


## BT28 - Mạch cộng đảo 2 và chọn Rf

![](bai_giai_slide/captures/bt28_summing_2_3.png){ width=94% }

*Nguon: slide 9 trong file PowerPoint goc.*

**Lời giải**

Bài 2: $R_{f} = R_{1} = R_{2} = 22 \,\mathrm{k\Omega}$, $\,\mathrm{V}_{1} = 1 \,\mathrm{V}$, $\,\mathrm{V}_{2} = 1.8 \,\mathrm{V}$.

$\,\mathrm{V}_{out} = -(\,\mathrm{V}_{1} + \,\mathrm{V}_{2}) = -2.8 \,\mathrm{V}$.

Bài 3: đề muốn $\,\mathrm{V}_{OUT} = 5(\,\mathrm{V}_{1} + \,\mathrm{V}_{2})$. Với mạch cộng đảo có $R_{1} = R_{2} = R$, công thức là:

$\,\mathrm{V}_{out} = -(R_{f}/R)(\,\mathrm{V}_{1} + \,\mathrm{V}_{2})$.

Để độ lớn hệ số bằng 5: $R_{f} = 5R$. Nếu $R = 10 \,\mathrm{k\Omega}$ thì $R_{f} = 50 \,\mathrm{k\Omega}$.

Lưu ý dấu: mạch cộng đảo cho $-5(\,\mathrm{V}_{1}+\,\mathrm{V}_{2})$. Muốn đúng dấu dương $+5(\,\mathrm{V}_{1}+\,\mathrm{V}_{2})$, thêm một tầng đảo gain $-1$ sau mạch cộng, hoặc dùng cấu hình cộng không đảo.


## BT29 - Thiết kế mạch cộng trọng số

![](bai_giai_slide/captures/bt29_weighted_sum.png){ width=94% }

*Nguon: slide 12 trong file PowerPoint goc.*

**Lời giải**

Với mạch cộng đảo:

$\,\mathrm{V}_{out} = -R_{f}(\,\mathrm{V}_{1}/R_{1} + \,\mathrm{V}_{2}/R_{2} + \,\mathrm{V}_{3}/R_{3} + \,\mathrm{V}_{4}/R_{4})$.

Đề yêu cầu độ lớn:

$|\,\mathrm{V}_{out}| = 0.1\,\mathrm{V}_{1} + 0.2\,\mathrm{V}_{2} + 0.3\,\mathrm{V}_{3} + 0.4\,\mathrm{V}_{4}$, $R_{f} = 10 \,\mathrm{k\Omega}$.

Chọn:

$R_{1} = R_{f}/0.1 = 100 \,\mathrm{k\Omega}$,
$R_{2} = R_{f}/0.2 = 50 \,\mathrm{k\Omega}$,
$R_{3} = R_{f}/0.3 \approx 33.3 \,\mathrm{k\Omega}$,
$R_{4} = R_{f}/0.4 = 25 \,\mathrm{k\Omega}$.

Nếu cần đầu ra dương đúng như đề, thêm tầng đảo unity gain sau mạch cộng đảo.


## BT30 - Mạch vi phân/tích phân

![](bai_giai_slide/captures/bt30_diff_integral.png){ width=94% }

*Nguon: slide 13 trong file PowerPoint goc.*

**Lời giải**

Mạch vi phân đảo lý tưởng:

$\,\mathrm{V}_{out} = -R_{f} C . d\,\mathrm{V}_{in}/dt$.

Rate of change của đoạn tuyến tính trong hình:

$d\,\mathrm{V}_{in}/dt = Δ\,\mathrm{V}/Δt$.

Thay vào công thức để lấy mức ra hằng trong từng đoạn ramp. Ramp đi lên cho đầu ra âm; ramp đi xuống cho đầu ra dương.

Mạch tích phân đảo:

$\,\mathrm{V}_{out}(t) = -1/(RC) \int \,\mathrm{V}_{in}(t) dt + \,\mathrm{V}_{out}(0)$.

Với xung vuông đầu vào, đầu ra là dạng tam giác/ramp. Độ dốc từng đoạn:

$d\,\mathrm{V}_{out}/dt = -\,\mathrm{V}_{in}/(RC)$.


## BT31 - Lọc tích cực thông thấp

![](bai_giai_slide/captures/bt31_active_lp.png){ width=94% }

*Nguon: slide 11 trong file PowerPoint goc.*

**Lời giải**

Với bộ lọc thông thấp bậc hai kiểu Sallen-Key có các linh kiện bằng nhau, tần số cắt:

$f_{c} = 1/(2\pi RC)$.

Từ giá trị `R`, `C` trong hình slide suy ra:

$f_{c} \approx 7.23 \,\mathrm{k\,\mathrm{Hz}}$.

Điều kiện Butterworth cho đáp ứng phẳng là hệ số hãm tương ứng $D = 1.414$, thường quy về hệ số khuếch đại vòng kín:

$\,\mathrm{A}_{v} = 3 - D \approx 1.586$.

Với op-amp không đảo: $\,\mathrm{A}_{v} = 1 + R_{2}/R_{1}$. Từ đó chọn điện trở hồi tiếp trong hình, slide cho đáp số:

$R_{1} \approx 586 \Omega$.


## BT32 - Lọc thông thấp hai tầng

![](bai_giai_slide/captures/bt32_two_stage_lp.png){ width=94% }

*Nguon: slide 13 trong file PowerPoint goc.*

**Lời giải**

Với mỗi tầng Sallen-Key có $R_{\,\mathrm{A}} = R_{B} = R$ và hai tụ bằng `C`:

$f_{c} = 1/(2\pi RC)$.

Dữ kiện $R = 1.8 \,\mathrm{k\Omega}$, $f_{c} = 2.68 \,\mathrm{k\,\mathrm{Hz}}$:

$C = 1/(2\pi  . 1.8k . 2.68k) \approx 33 \,\mathrm{nF}$.

Để đáp ứng Butterworth bậc cao, hai tầng dùng hệ số khuếch đại khác nhau theo bảng hệ số. Slide cho đáp số điện trở hồi tiếp:

$R_{1} \approx 274 \Omega$, $R_{3} \approx 2.22 \,\mathrm{k\Omega}$.

Các giá trị này được chọn để tạo hệ số hãm đúng cho từng tầng, không chỉ để đặt $f_{c}$.


## BT33 - Lọc tích cực thông cao

![](bai_giai_slide/captures/bt33_active_hp.png){ width=94% }

*Nguon: slide 16 trong file PowerPoint goc.*

**Lời giải**

Với mạch thông cao bậc hai có `R` bằng nhau và `C` bằng nhau:

$f_{c} = 1/(2\pi RC)$.

Đề yêu cầu $f_{c} = 20 \,\mathrm{k\,\mathrm{Hz}}$. Chọn trước một giá trị tụ tiện dụng, ví dụ $C = 1 \,\mathrm{nF}$:

$R = 1/(2\pi f_{cC}) = 1/(2\pi  . 20k . 1\,\mathrm{nF}) \approx 7.96 \,\mathrm{k\Omega}$.

Chọn chuẩn gần nhất $R = 8.2 \,\mathrm{k\Omega}$ hoặc $7.87 \,\mathrm{k\Omega}$ tùy dãy linh kiện.

Điều kiện Butterworth: đặt hệ số khuếch đại không đảo $\,\mathrm{A}_{v} \approx 1.586$, tức $1 + R_{2}/R_{1} = 1.586$. Có thể chọn $R_{1} = 10 \,\mathrm{k\Omega}$, $R_{2} = 5.86 \,\mathrm{k\Omega}$.


## BT34 - Lọc thông dải đa hồi tiếp

![](bai_giai_slide/captures/bt34_mfb_bandpass.png){ width=94% }

*Nguon: slide 21 trong file PowerPoint goc.*

**Lời giải**

Với mạch multiple-feedback band-pass trong slide, dùng các công thức chuẩn:

$f_0 = \frac{1}{2\pi C}\sqrt{\frac{R_1+R_3}{R_1R_2R_3}}$ nếu hai tụ bằng nhau.

Độ lợi tại tần số trung tâm:

$\,\mathrm{A}_{0} = R_{2}/(2R_{1})$ theo cấu hình thường gặp trong slide.

Hệ số chọn lọc:

$Q = f_{0}/BW$.

Băng thông:

$BW = f_{0}/Q$.

Cách làm: đọc $R_{1}, R_{2}, R_{3}, C_{1}, C_{2}$ trên hình, thay vào công thức. Nếu $C_{1} = C_{2} = C$, dùng dạng rút gọn ở trên; nếu không bằng nhau, dùng công thức tổng quát của MFB band-pass.


# Bài tập bổ sung có hình mạch

## BS01 - Diode nối tiếp

![](bai_giai_slide/extra/extra01_diode.png){ width=82% }

**Đề:** Diode silicon có $\,\mathrm{V}_{D} \approx 0.7 \,\mathrm{V}$. Tính dòng mạch và $\,\mathrm{V}_{o}$.

**Giải:** Khi $\,\mathrm{V}_{i} = 12 \,\mathrm{V}$, diode phân cực thuận. Tổng điện trở nối tiếp là $R + R_{L} = 1k + 2k = 3\,\mathrm{k\Omega}$. Dòng mạch $I = (12 - 0.7)/3k = 3.77 \,\mathrm{mA}$. Điện áp ra trên tải: $\,\mathrm{V}_{o} = I R_{L} = 3.77\,\mathrm{mA} . 2k = 7.53 \,\mathrm{V}$.

## BS02 - Phân cực BJT CE

![](bai_giai_slide/extra/extra02_bjt.png){ width=82% }

**Đề:** Tính $I_{C}$, $\,\mathrm{V}_{B}$, $\,\mathrm{V}_{E}$, $\,\mathrm{V}_{C}$, $\,\mathrm{V}_{CE}$. Cho $\beta =100$, $\,\mathrm{V}_{BE}=0.7 \,\mathrm{V}$.

**Giải:** $\,\mathrm{V}_{Th} = 12 . 10/(47+10) = 2.105 \,\mathrm{V}$, $R_{Th} = 47k \parallel 10k = 8.25 \,\mathrm{k\Omega}$. $I_{E} = (\,\mathrm{V}_{Th} - 0.7)/(R_{E} + R_{Th}/(\beta +1)) = 1.405/(680 + 81.7) = 1.845 \,\mathrm{mA}$. $I_{C} \approx \beta /(\beta +1)I_{E} = 1.827 \,\mathrm{mA}$. $\,\mathrm{V}_{E} = 1.255 \,\mathrm{V}$, $\,\mathrm{V}_{B} = 1.955 \,\mathrm{V}$, $\,\mathrm{V}_{C} = 12 - 1.827\,\mathrm{mA} . 2.2k = 7.98 \,\mathrm{V}$, $\,\mathrm{V}_{CE} = 7.98 - 1.255 = 6.73 \,\mathrm{V}$.

## BS03 - JFET tự phân cực

![](bai_giai_slide/extra/extra03_jfet.png){ width=82% }

**Đề:** Tính $I_{D}$, $\,\mathrm{V}_{GS}$, $\,\mathrm{V}_{DS}$. Cho $I_{DSS}=8 \,\mathrm{mA}$, $\,\mathrm{V}_{P}=-4 \,\mathrm{V}$.

**Giải:** Gate nối mass qua $R_{G}$ nên $\,\mathrm{V}_{G}\approx0$, $\,\mathrm{V}_{GS}=-I_{D} R_{S}$. Đặt $I_{D}$ theo mA: $\,\mathrm{V}_{GS}=-I_{D}$. Phương trình Shockley: $I_{D} = 8(1 - I_{D}/4)^2$. Giải được hai nghiệm `2 mA` và `8 mA`; nghiệm vật lý phù hợp là $I_{D}=2 \,\mathrm{mA}$ vì $\,\mathrm{V}_{GS}=-2 \,\mathrm{V}$ nằm trong vùng `0` đến $\,\mathrm{V}_{P}$. $\,\mathrm{V}_{D}=15 - 2\,\mathrm{mA} . 2.2k = 10.6 \,\mathrm{V}$, $\,\mathrm{V}_{S}=2 \,\mathrm{V}$, nên $\,\mathrm{V}_{DS}=8.6 \,\mathrm{V}$.

## BS04 - Mạch cộng đảo Op-Amp

![](bai_giai_slide/extra/extra04_sum.png){ width=82% }

**Đề:** Tính $\,\mathrm{V}_{o}$.

**Giải:** Với op-amp lý tưởng, nút đảo là mass ảo. $\,\mathrm{V}_{o} = -R_{f}(\,\mathrm{V}_{1}/R_{1} + \,\mathrm{V}_{2}/R_{2}) = -40k(1/10k + 2/20k) = -8 \,\mathrm{V}$. Nếu op-amp cấp nguồn nhỏ hơn ±8 V thì đầu ra sẽ bị bão hòa tại rail nguồn.

## BS05 - Lọc RC thông cao có tải

![](bai_giai_slide/extra/extra05_filter.png){ width=82% }

**Đề:** Tính tần số cắt xấp xỉ và độ lợi ở tần số cao.

**Giải:** Tụ ghép nhìn thấy điện trở Thevenin hai phía là $R + R_{L} = 3.3k + 10k = 13.3 \,\mathrm{k\Omega}$, nên $f_{c} = 1/(2\pi (R+R_{L})C) = 1/(2\pi  . 13.3k . 10\,\mathrm{nF}) \approx 1.20 \,\mathrm{k\,\mathrm{Hz}}$. Ở tần số cao, tụ gần như ngắn mạch, độ lợi chia áp $\,\mathrm{A}_{v}\infty = R_{L}/(R+R_{L}) = 10/13.3 = 0.752$.

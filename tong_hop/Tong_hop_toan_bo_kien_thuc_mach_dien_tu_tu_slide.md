---
title: "Tổng hợp toàn bộ kiến thức mạch điện tử (từ Slide)"
author: "Tổng hợp từ Slide/ và Slide_new/"
lang: "vi"
geometry: margin=2cm
fontsize: 11pt
---

# Tài liệu tổng hợp kiến thức mạch điện tử

# Phạm vi tài liệu

Tài liệu này được tổng hợp từ hai thư mục nguồn:

- `Slide/`
- `Slide_new/`

Nội dung bao quát các chủ đề xuất hiện trong slide:

- Đại cương và linh kiện điện tử cơ bản
- Vật liệu bán dẫn, chuyển tiếp P-N, diode và ứng dụng
- BJT: cấu tạo, nguyên lý, đặc tính, phân cực, điểm Q
- Phân tích mạch khuếch đại CE, CB, CC
- FET: JFET, MOSFET, phân cực và khuếch đại
- Op-Amp: cấu tạo, đặc tính, hồi tiếp âm, ứng dụng
- Mạch so sánh, cộng, trừ, tích phân, vi phân
- Mạch dao động
- Mạch lọc thụ động và mạch lọc tích cực

## Bộ hình trực quan được thêm bằng Python

Tài liệu này đã được bổ sung các biểu đồ và mô hình hóa trực quan sinh tự động bằng:

- `scripts/generate_electronic_figures.py`

Mục tiêu của phần hình là mô tả trực tiếp:

- đặc tuyến dòng áp của linh kiện
- dạng sóng vào ra của mạch
- điểm làm việc và đường tải
- vùng hoạt động của transistor
- đáp ứng tần số của bộ lọc
- sơ đồ khối cho các mạch và hệ thống

![Mô hình hệ thống xử lý tín hiệu điện tử](figures/01_signal_chain.png){ width=95% }

Hình này cho thấy luồng xử lý điển hình của hệ điện tử tương tự: tín hiệu tự nhiên được cảm biến đổi sang tín hiệu điện, sau đó đi qua tiền xử lý, lọc, khuếch đại, khối xử lý và cuối cùng cấp cho tải hoặc thiết bị hiển thị.

# 1. Kiến thức nền tảng

## 1.1. Đại lượng điện cơ bản

### Điện tích

- Ký hiệu: `Q`
- Đơn vị: Coulomb `(C)`
- Công thức: `Q = I.t`

### Dòng điện

- Ký hiệu: `I`
- Đơn vị: Ampere `(A)`
- Bản chất: dòng chuyển dời có hướng của hạt mang điện
- Công thức trung bình: `I = ΔQ / Δt`

### Điện áp

- Ký hiệu: `V` hoặc `U`
- Đơn vị: Volt `(V)`
- Công thức: $U_{AB} = V_A - V_B$

### Công suất

- Ký hiệu: `P`
- Đơn vị: Watt `(W)`
- Công thức: `P = U.I`

## 1.2. Linh kiện thụ động

### Điện trở

- Ký hiệu: `R`
- Đơn vị: Ohm `(Ω)`
- Định luật Ohm: `U = I.R`
- Vai trò: hạn dòng, chia áp, định thiên, tạo hằng số thời gian

### Tụ điện

- Ký hiệu: `C`
- Đơn vị: Farad `(F)`
- Quan hệ dòng áp:
  - $i_C = C\,\dfrac{dv}{dt}$
  - $v_C = \dfrac{1}{C}\int i_C\,dt$
- Trong DC xác lập: gần như hở mạch
- Trong AC: trở kháng phụ thuộc tần số
  - $X_C = \dfrac{1}{2\pi f C}$

### Cuộn cảm

- Ký hiệu: `L`
- Đơn vị: Henry `(H)`
- Quan hệ dòng áp:
  - $v_L = L\,\dfrac{di}{dt}$
- Trong DC xác lập: gần như ngắn mạch
- Trong AC:
  - $X_L = 2\pi f L$

## 1.3. Công cụ phân tích mạch

- KCL: tổng dòng vào nút bằng tổng dòng ra nút
- KVL: tổng đại số điện áp trên vòng kín bằng 0
- Chia áp: $V_x = V_{\text{nguồn}} \dfrac{R_x}{R_{\text{tổng nối tiếp}}}$
- Chia dòng: dòng chia tỉ lệ nghịch với điện trở nhánh
- Thevenin:
  - $V_{Th}$: điện áp hở mạch tại hai cực
  - $R_{Th}$: điện trở nhìn vào mạch khi triệt nguồn độc lập
- Norton:
  - $I_N = \dfrac{V_{Th}}{R_{Th}}$
  - $R_N = R_{Th}$

# 2. Vật liệu bán dẫn và chuyển tiếp P-N

## 2.1. Phân loại vật liệu theo tính dẫn điện

- Dẫn điện
- Bán dẫn
- Cách điện

## 2.2. Silicon và Germanium

Từ slide, Silicon được nhấn mạnh là vật liệu ổn định hơn Germanium trong linh kiện điện tử. Trong thực tế:

- Silicon chịu nhiệt tốt hơn
- Dòng rò nhỏ hơn
- Linh kiện ổn định hơn

## 2.3. Bản chất dẫn điện của bán dẫn

- Khi được cung cấp năng lượng, electron có thể nhảy từ vùng hóa trị sang vùng dẫn
- Dẫn điện diễn ra nhờ:
  - dòng electron
  - dòng lỗ trống

## 2.4. Pha tạp

### Bán dẫn loại N

- Pha tạp nguyên tố nhóm V
- Hạt tải đa số: electron

### Bán dẫn loại P

- Pha tạp nguyên tố nhóm III
- Hạt tải đa số: lỗ trống

## 2.5. Chuyển tiếp P-N

Khi ghép P và N:

- Electron từ vùng N khuếch tán sang P
- Lỗ trống từ vùng P khuếch tán sang N
- Hình thành vùng hiếm và điện trường nội tại

Ý nghĩa:

- Là nền tảng của diode, BJT và nhiều linh kiện bán dẫn khác

# 3. Diode

## 3.1. Cấu tạo và ký hiệu

- Diode có 2 cực:
  - Anode `(P)`
  - Cathode `(N)`
- Chức năng cơ bản: cho dòng đi theo một chiều thuận và chặn chiều ngược

## 3.2. Nguyên lý hoạt động

### Phân cực thuận

- Cực dương nối Anode
- Cực âm nối Cathode
- Khi $V_D$ vượt điện áp ngưỡng, diode dẫn

Giá trị điển hình:

- Silicon: $V_\gamma \approx 0.7\,\mathrm{V}$
- Germanium: $V_\gamma \approx 0.3\,\mathrm{V}$

### Phân cực nghịch

- Cực dương nối Cathode
- Cực âm nối Anode
- Dòng rất nhỏ, xem như bằng 0 trong mô hình lý tưởng
- Nếu điện áp ngược quá lớn: đánh thủng

## 3.3. Đặc tuyến V-I

### Vùng thuận

- Trước ngưỡng: dòng tăng ít
- Sau ngưỡng: dòng tăng rất nhanh

### Vùng nghịch

- Có dòng rò nhỏ
- Sau điện áp đánh thủng: dòng tăng mạnh

![Đặc tuyến V-I của diode](figures/02_diode_vi_curve.png){ width=82% }

Cách đọc hình:

- phía phải mốc $0.7\,\mathrm{V}$: diode Silicon dẫn rất mạnh
- quanh gốc tọa độ: diode gần như chưa dẫn
- phía điện áp âm lớn: diode bước vào vùng đánh thủng nghịch
- độ dốc của đặc tuyến tại điểm làm việc liên quan trực tiếp đến điện trở vi sai của diode

## 3.4. Các mô hình diode

### Mô hình lý tưởng

- Thuận: ngắn mạch
- Nghịch: hở mạch

### Mô hình thực xấp xỉ

- Thuận: rơi áp cố định $0.7\,\mathrm{V}$ với diode Si
- Nghịch: hở mạch

### Mô hình hoàn chỉnh

- Thuận: $V_D = V_\gamma + I_D r_d$
- Nghịch: có điện trở ngược rất lớn

## 3.5. Công thức thường dùng

- Diode thuận nối tiếp điện trở:
  - $I = \dfrac{V_S - V_D}{R}$
- Với mô hình thực:
  - $I \approx \dfrac{V_S - 0.7}{R}$

## 3.6. Ứng dụng của diode

### Chỉnh lưu nửa chu kỳ

- Chỉ cho qua một bán kỳ
- Điện áp DC trung bình thấp
- Gợn sóng lớn

Giải thích cụ thể:

- Trong nửa chu kỳ thuận, diode phân cực thuận nên dẫn; tải nhận được điện áp gần bằng nửa dương của nguồn vào, trừ đi sụt áp trên diode nếu dùng mô hình thực.
- Trong nửa chu kỳ nghịch, diode bị phân cực nghịch nên ngắt; điện áp trên tải gần bằng 0.
- Vì tải chỉ nhận năng lượng ở một nửa chu kỳ, điện áp trung bình nhỏ và độ nhấp nhô lớn.

Công thức hay dùng với điện áp vào hình sin có biên độ đỉnh $V_m$:

- Lý tưởng:

$$
V_{DC} = \frac{V_m}{\pi}
$$

- Nếu tính sụt áp một diode silicon gần đúng:

$$
V_{DC} \approx \frac{V_m - V_D}{\pi}
$$

- Giá trị hiệu dụng của điện áp ra lý tưởng:

$$
V_{rms} = \frac{V_m}{2}
$$

- Tần số gợn:

$$
f_r = f_{\text{nguồn}}
$$

Đặc điểm đi kèm:

- Mạch đơn giản, ít linh kiện.
- Hiệu suất sử dụng nguồn AC thấp hơn chỉnh lưu toàn kỳ.
- Tụ lọc nếu có sẽ phải làm việc vất vả hơn vì thời gian xả dài hơn.

### Chỉnh lưu toàn chu kỳ

- Tận dụng cả hai bán kỳ
- Điện áp trung bình lớn hơn
- Tần số gợn bằng $2f_{\text{nguồn}}$

Giải thích cụ thể:

- Ở cấu hình dùng biến áp có điểm giữa hoặc cầu diode, cả hai bán kỳ của tín hiệu vào đều được biến thành điện áp cùng cực tính trên tải.
- Vì nửa âm cũng được "lật lên" thành nửa dương nên tải nhận năng lượng ở cả hai nửa chu kỳ.
- Kết quả là điện áp trung bình lớn hơn, lọc dễ hơn và độ gợn sau lọc nhỏ hơn so với bán kỳ.

Công thức hay dùng với điện áp vào hình sin đỉnh $V_m$:

- Lý tưởng:

$$
V_{DC} = \frac{2V_m}{\pi}
$$

- Nếu là cầu diode, mỗi nửa chu kỳ thường có hai diode dẫn nên gần đúng:

$$
V_{DC} \approx \frac{2(V_m - 2V_D)}{\pi}
$$

- Nếu là chỉnh lưu toàn kỳ dùng điểm giữa, mỗi lần chỉ qua một diode:

$$
V_{DC} \approx \frac{2(V_m - V_D)}{\pi}
$$

- Giá trị hiệu dụng lý tưởng:

$$
V_{rms} = \frac{V_m}{\sqrt{2}}
$$

- Tần số gợn:

$$
f_r = 2f_{\text{nguồn}}
$$

Đặc điểm đi kèm:

- Điện áp DC trung bình cao hơn bán kỳ.
- Cùng một tụ lọc thì điện áp ra mịn hơn do tụ được nạp lại thường xuyên hơn.
- Đây là lý do chỉnh lưu toàn kỳ được dùng nhiều hơn trong nguồn DC thực tế.

![Dạng sóng trước và sau chỉnh lưu](figures/03_rectifier_waveforms.png){ width=90% }

Ý nghĩa trực quan:

- dạng sóng đầu là điện áp AC đầu vào
- dạng sóng giữa là chỉnh lưu bán kỳ, chỉ giữ nửa dương
- dạng sóng cuối là chỉnh lưu toàn kỳ, cả hai bán kỳ đều trở thành điện áp dương
- biên độ đầu ra thấp hơn đầu vào do sụt áp trên diode

### Điện áp ngược cực đại PIV

Trong mạch chỉnh lưu, diode không chỉ cần dẫn đúng lúc mà còn phải chịu được điện áp ngược khi bị khóa.

- PIV là điện áp ngược cực đại diode phải chịu.
- Khi chọn linh kiện, điện áp chịu đựng ngược của diode phải lớn hơn PIV thực tế, thường có hệ số an toàn.

Ý nghĩa:

- Nếu chọn diode có điện áp ngược định mức quá thấp, diode có thể bị đánh thủng khi mạch đang chạy bình thường.
- Nhiều bài tập nguồn sẽ yêu cầu tính PIV trước khi chọn diode.

### Mạch lọc nguồn

- Tụ lọc mắc song song tải để giảm độ nhấp nhô
- Hệ số nhấp nhô phụ thuộc $R_L$, $C$, $f$

Giải thích cụ thể:

- Gần đỉnh sóng chỉnh lưu, diode dẫn và nạp tụ lên gần giá trị đỉnh.
- Khi điện áp nguồn giảm xuống thấp hơn điện áp trên tụ, diode ngắt.
- Tụ xả qua tải trong khoảng thời gian giữa hai lần nạp nên điện áp ra không còn bằng phẳng tuyệt đối mà có gợn.

Công thức gần đúng thường dùng:

- Biên độ gợn điện áp với tụ lọc:

$$
V_{r(pp)} \approx \frac{I_L}{f_r C}
$$

trong đó $f_r$ là tần số gợn, bằng $f_{\text{nguồn}}$ với bán kỳ và $2f_{\text{nguồn}}$ với toàn kỳ.

- Điện áp DC sau lọc gần đúng:

$$
V_{DC} \approx V_p - \frac{V_{r(pp)}}{2}
$$

với $V_p$ là điện áp đỉnh sau khi đã trừ sụt áp diode.

### Zener ổn áp

- Làm việc vùng đánh thủng nghịch có kiểm soát
- Điện áp ra gần bằng $V_Z$

Điều kiện dòng:

- $I_{ZK} \le I_Z \le I_{ZM}$

Giải thích cụ thể:

- Diode Zener được phân cực nghịch.
- Khi điện áp nghịch chưa tới vùng Zener, dòng rất nhỏ.
- Khi đạt đến vùng đánh thủng có kiểm soát, điện áp trên diode gần như giữ quanh $V_Z$ trong khi dòng có thể thay đổi trong một khoảng cho phép.

Điều này làm Zener thích hợp để:

- tạo điện áp chuẩn
- ổn áp đơn giản cho tải nhỏ
- kẹp mức điện áp

Công thức cơ bản của mạch ổn áp Zener:

$$
I_R = \frac{V_S - V_Z}{R}
$$

$$
I_L = \frac{V_Z}{R_L}
$$

$$
I_Z = I_R - I_L
$$

Điều kiện công suất:

$$
P_Z = V_Z I_Z \le P_{Z(max)}
$$

## 3.7. Cách giải bài tập diode

### Dạng 1: Xác định diode dẫn hay ngắt

1. Chọn mô hình diode theo đề
2. Giả sử diode dẫn
3. Tính điện áp và dòng
4. Kiểm tra điều kiện:
   - nếu $V_D \ge 0.7\,\mathrm{V}$ với diode Si thì giả sử dẫn hợp lý
   - nếu dòng âm hoặc điện áp không thỏa thì diode ngắt

### Dạng 2: Tính điện áp ra mạch chỉnh lưu

1. Xác định số diode dẫn trong mỗi bán kỳ
2. Trừ tổng sụt áp diode khỏi đỉnh vào
3. Vẽ dạng sóng sau chỉnh lưu
4. Nếu có tụ lọc, xác định khoảng nạp và xả của tụ

### Dạng 2a: Bài chỉnh lưu bán kỳ

Cách giải:

1. Xác định điện áp đỉnh của nguồn vào:

$$
V_m = \sqrt{2}\,V_{rms}
$$

2. Xác định diode lý tưởng hay thực.
3. Tính đỉnh điện áp ra:

- lý tưởng: $V_{p(out)} = V_m$
- thực: $V_{p(out)} \approx V_m - V_D$

4. Nếu đề hỏi điện áp DC trung bình:

$$
V_{DC} \approx \frac{V_{p(out)}}{\pi}
$$

5. Nếu có tải điện trở:

$$
I_{DC} = \frac{V_{DC}}{R_L}
$$

6. Nếu có tụ lọc, dùng:

$$
V_{r(pp)} \approx \frac{I_L}{f_{\text{nguồn}} C}
$$

### Dạng 2b: Bài chỉnh lưu toàn kỳ

Cách giải:

1. Xác định mạch là cầu diode hay biến áp có điểm giữa.
2. Tính điện áp đỉnh sau chỉnh lưu:

- cầu diode: $V_{p(out)} \approx V_m - 2V_D$
- điểm giữa: $V_{p(out)} \approx V_m - V_D$

3. Tính điện áp DC trung bình:

$$
V_{DC} \approx \frac{2V_{p(out)}}{\pi}
$$

4. Nếu có tụ lọc, dùng tần số gợn:

$$
f_r = 2f_{\text{nguồn}}
$$

5. Tính gần đúng gợn:

$$
V_{r(pp)} \approx \frac{I_L}{2f_{\text{nguồn}} C}
$$

6. Tính điện áp DC sau lọc:

$$
V_{DC} \approx V_{p(out)} - \frac{V_{r(pp)}}{2}
$$

### Dạng 2c: Bài tính PIV

Cách giải:

1. Xác định thời điểm diode bị phân cực nghịch mạnh nhất.
2. Dùng sơ đồ điện áp ở đúng thời điểm đó để tính điện áp ngược trên diode.
3. Kết luận:

$$
V_{RRM(\text{diode})} > \mathrm{PIV}
$$

thường nên có hệ số dự trữ an toàn.

### Dạng 3: Ổn áp Zener

1. Giả sử Zener làm việc vùng ổn áp
2. Tính dòng qua điện trở hạn dòng:
   - $I_R = \dfrac{V_S - V_Z}{R}$
3. Tính dòng tải:
   - $I_L = \dfrac{V_Z}{R_L}$
4. Suy ra:
   - $I_Z = I_R - I_L$
5. Kiểm tra $I_{ZK} \le I_Z \le I_{ZM}$

Nếu bài hỏi mạch có còn ổn áp không, hãy làm đúng thứ tự:

1. Tính $I_R$ từ nguồn và điện trở hạn dòng.
2. Tính $I_L$ từ tải.
3. Lấy hiệu để ra $I_Z$.
4. Kiểm tra cả hai điều kiện:

$$
I_{ZK} \le I_Z \le I_{ZM}
$$

và

$$
P_Z = V_Z I_Z \le P_{Z(max)}
$$

Nếu một trong hai điều kiện sai, Zener không còn làm việc đúng vùng ổn áp.

# 4. Transistor BJT

## 4.1. Cấu tạo

BJT có 3 cực:

- Emitter `(E)`
- Base `(B)`
- Collector `(C)`

Hai loại:

- NPN
- PNP

## 4.2. Nguyên lý hoạt động NPN

- Mối nối `BE` phân cực thuận
- Mối nối `BC` phân cực nghịch khi làm việc vùng khuếch đại
- Electron từ Emitter sang Base
- Base mỏng và pha tạp nhẹ nên chỉ một phần nhỏ tạo thành $I_B$
- Phần lớn bị hút sang Collector tạo $I_C$

## 4.3. Quan hệ dòng điện

- $I_E = I_B + I_C$
- $\beta_{DC} = \dfrac{I_C}{I_B}$
- $\alpha_{DC} = \dfrac{I_C}{I_E}$
- Liên hệ:
  - $\alpha = \dfrac{\beta}{\beta + 1}$
  - $\beta = \dfrac{\alpha}{1 - \alpha}$

## 4.4. Các vùng hoạt động

Để đọc đúng đặc tuyến của BJT, cần tách rõ ba đại lượng:

- $V_{BE}$ quyết định tiếp giáp base-emitter có được phân cực thuận đủ mạnh hay không.
- $I_B$ là đại lượng chọn ra từng đường trong họ đặc tuyến ra.
- $V_{CE}$ quyết định transistor đang ở vùng khuếch đại hay đã bị ép sang bão hòa.

### Đặc tuyến vào của BJT

Đặc tuyến vào mô tả quan hệ giữa dòng base và điện áp base-emitter:

- Trục ngang: $V_{BE}$
- Trục đứng: $I_B$

![Đặc tuyến vào của BJT](figures/13_bjt_input_characteristic.png){ width=78% }

Giải thích cực kỳ cụ thể:

- Khi $V_{BE}$ còn nhỏ, tiếp giáp $BE$ chưa được phân cực thuận đủ mạnh nên $I_B$ gần như bằng 0. Đây là lý do BJT còn tắt.
- Khi $V_{BE}$ tiến gần vùng khoảng $0.6$ đến $0.7\,\mathrm{V}$, tiếp giáp PN bắt đầu dẫn rõ rệt.
- Sau điểm này, chỉ cần tăng thêm một lượng điện áp rất nhỏ thì $I_B$ tăng rất nhanh. Đó là dấu hiệu đặc trưng của phần tử có bản chất tiếp giáp diode.

Đặc điểm đi kèm:

- BJT nhạy với thay đổi nhỏ của $V_{BE}$.
- Vì đặc tuyến vào rất dốc, mạch phân cực luôn cần điện trở hạn dòng hoặc mạch phân áp để tránh $I_B$ tăng mất kiểm soát.
- Khi giải bài, nếu chưa biết transistor có dẫn không, hãy kiểm tra trước $V_{BE}$.

### Họ đặc tuyến ra của BJT

Họ đặc tuyến ra biểu diễn:

- Trục ngang: $V_{CE}$
- Trục đứng: $I_C$
- Mỗi đường ứng với một giá trị $I_B$ cố định

![Họ đặc tuyến ra của BJT](figures/14_bjt_output_characteristic.png){ width=82% }

Cách đọc họ đặc tuyến này:

- Chọn một đường, ví dụ một giá trị $I_B$ cụ thể. Khi đó ta đang khảo sát transistor với mức kích base cố định.
- Di chuyển từ trái sang phải dọc theo đường đó để xem khi $V_{CE}$ tăng thì $I_C$ biến thiên như thế nào.
- Gần gốc tọa độ, $V_{CE}$ quá nhỏ nên transistor không thể giữ chế độ khuếch đại bình thường và rơi vào bão hòa.
- Ở đoạn tương đối phẳng, $I_C$ hầu như không đổi nhiều theo $V_{CE}$; đây là vùng active, nơi BJT khuếch đại tốt nhất.

Cơ sở công thức ở vùng active:

$$
I_C \approx \beta I_B
$$

Nhưng cần nhớ rất kỹ:

- Công thức trên chỉ dùng an toàn khi transistor đang ở vùng active.
- Nếu transistor đã bão hòa, $I_C$ không còn tăng tuyến tính theo $I_B$ như trước.

### Cut-off

- $V_{BE} < 0.7\,\mathrm{V}$ xấp xỉ
- $I_B \approx 0$, $I_C \approx 0$
- Transistor tắt

Đặc điểm của vùng này:

- Tiếp giáp $BE$ chưa đủ mở nên gần như không có dòng base.
- Do đó dòng collector cũng gần như bằng 0.
- Trong mạch CE có điện trở $R_C$, collector thường bị kéo lên gần $V_{CC}$.
- Đây là trạng thái OFF khi dùng BJT như công tắc.

### Active (linear)

- $V_{BE} \approx 0.7\,\mathrm{V}$
- $V_{CE} > V_{CE(sat)}$
- $I_C = \beta I_B$
- Dùng cho khuếch đại

Đặc điểm của vùng này:

- Tiếp giáp $BE$ phân cực thuận, còn tiếp giáp $BC$ phân cực nghịch.
- BJT lúc này hoạt động như một phần tử khuếch đại dòng.
- Tín hiệu nhỏ ở base có thể tạo dao động lớn hơn ở collector.
- Đây là vùng bắt buộc phải có nếu muốn phân tích khuếch đại tuyến tính, tính $A_v$, $A_i$, mô hình tín hiệu nhỏ hay điểm $Q$.

### Saturation

- `BE` thuận, `BC` cũng thuận
- $V_{CE}$ nhỏ, thường xấp xỉ $0.2\,\mathrm{V}$
- Transistor mở bão hòa
- Dùng cho đóng cắt

Đặc điểm của vùng này:

- Cả hai tiếp giáp đều thuận, nên transistor không còn giữ quan hệ khuếch đại chuẩn.
- Tăng thêm $I_B$ không làm $I_C$ tăng đáng kể như trong vùng active.
- Đây là trạng thái ON khi dùng BJT như công tắc, vì sụt áp $V_{CE}$ nhỏ nên tổn hao công suất nhỏ hơn.

![Mô hình các vùng hoạt động của BJT](figures/05_bjt_regions.png){ width=82% }

Hình vùng hoạt động giúp phân biệt rõ:

- vùng trái: transistor dễ bão hòa vì $V_{CE}$ quá thấp
- vùng giữa: vùng active để khuếch đại tuyến tính
- khi dòng base rất nhỏ, transistor tiến dần tới cutoff

## 4.5. Đường tải DC và điểm Q

### Khái niệm

- Đường tải DC biểu diễn ràng buộc giữa $I_C$ và $V_{CE}$
- Điểm Q là điểm làm việc không tín hiệu AC

### Ý nghĩa

- Điểm Q ở giữa vùng tuyến tính giúp biên độ dao động đầu ra đối xứng hơn
- Giảm méo do cắt đỉnh hoặc bão hòa

### Công thức cơ bản mạch CE đơn giản

- $V_{CC} = I_C R_C + V_{CE} + I_E R_E$
- Thường gần đúng $I_E \approx I_C$

![Đường tải DC và điểm Q của BJT](figures/04_bjt_load_line.png){ width=82% }

Hình này cần đọc theo đúng logic phân tích mạch:

- giao điểm với trục $V_{CE}$ là trạng thái không có dòng collector
- giao điểm với trục $I_C$ là trạng thái $V_{CE} = 0$
- điểm $Q$ là điểm phân cực DC thực tế của mạch
- nếu tín hiệu AC làm mạch dao động quanh `Q` quá gần hai biên, đầu ra sẽ bị méo do cutoff hoặc saturation

## 4.6. Các kiểu phân cực

### Base bias

- Đơn giản nhưng kém ổn định

### Collector-feedback bias

- Có hồi tiếp ổn định hơn

### Emitter bias

- Ổn định hơn nhờ $R_E$

### Voltage-divider bias

- Phổ biến nhất
- Ổn định tốt

Với cầu chia áp:

- $V_B \approx V_{CC}\dfrac{R_2}{R_1 + R_2}$ nếu dòng base nhỏ
- $V_E = V_B - 0.7$
- $I_E = \dfrac{V_E}{R_E}$
- $I_C \approx I_E$
- $V_C = V_{CC} - I_C R_C$
- $V_{CE} = V_C - V_E$

Nếu cần chính xác hơn:

- Quy mạch phân áp về Thevenin:
  - $V_{Th} = V_{CC}\dfrac{R_2}{R_1 + R_2}$
  - $R_{Th} = R_1 \parallel R_2$
- Sau đó:
  - $I_B = \dfrac{V_{Th} - 0.7}{R_{Th} + (\beta+1)R_E}$
  - $I_C = \beta I_B$
  - $I_E = (\beta+1)I_B$

## 4.7. Mô hình tín hiệu nhỏ

Thường dùng:

- $r'_e \approx \dfrac{25\,\mathrm{mV}}{I_E}$
- $r_\pi = \beta r'_e$
- $g_m = \dfrac{I_C}{V_T}$, với $V_T \approx 25\,\mathrm{mV}$

Các dạng tương đương rất hay dùng:

- $g_m \approx \dfrac{1}{r'_e}$
- $r_\pi = \dfrac{\beta}{g_m}$

Ý nghĩa:

- $r'_e$ là điện trở vi sai ở cực emitter
- $r_\pi$ là điện trở nhìn vào base trong mô hình $\pi$
- $g_m$ cho biết dòng collector đổi mạnh đến đâu khi $v_{be}$ thay đổi

Đây là 3 thông số gốc nhất khi làm bài tín hiệu nhỏ BJT.

## 4.8. Ba cấu hình khuếch đại BJT

### CE - Common Emitter

- Khuếch đại áp lớn
- Đảo pha 180 độ
- Khuếch đại dòng khá lớn

Xấp xỉ:

- $A_v \approx - \dfrac{R_C \parallel R_L}{r'_e}$ nếu bỏ qua $R_E$ bởi tụ bypass

Các công thức tín hiệu nhỏ thường dùng cho CE:

- Nếu emitter được bypass tốt:

$$
A_v \approx - \dfrac{R_C \parallel R_L}{r'_e}
$$

- Nếu xét điện trở ra nội tại transistor:

$$
A_v \approx -g_m (R_C \parallel R_L \parallel r_o)
$$

- Trở vào nhìn từ base nếu emitter được bypass:

$$
R_{in(base)} \approx r_\pi = \beta r'_e
$$

- Nếu không bypass emitter:

$$
R_{in(base)} \approx \beta (r'_e + R_E)
$$

- Nếu cần trở vào toàn mạch tại ngõ vào:

$$
R_{in} \approx R_B \parallel R_{in(base)}
$$

trong đó $R_B$ là điện trở phân cực tương đương nhìn vào base.

- Trở ra gần đúng:

$$
R_{out} \approx R_C
$$

nếu bỏ qua $r_o$ của transistor.

Ý nghĩa phải nhớ:

- dấu âm cho biết CE đảo pha $180^\circ$
- tụ bypass càng tốt thì gain CE càng lớn
- thêm $R_E$ không bypass sẽ làm gain giảm nhưng ổn định hơn

### CB - Common Base

- Khuếch đại áp lớn
- Không khuếch đại dòng đáng kể
- Trở vào nhỏ
- Không đảo pha

Xấp xỉ thường dùng:

- $A_v$ lớn và dương
- trở vào rất nhỏ, gần cỡ $r'_e$

$$
R_{in} \approx r'_e
$$

### CC - Common Collector / emitter follower

- $A_v \approx 1$
- Trở vào lớn
- Trở ra nhỏ
- Khuếch đại dòng tốt

Các công thức tín hiệu nhỏ gần đúng:

- Gain điện áp:

$$
A_v \approx 1
$$

- Trở vào nhìn từ base:

$$
R_{in(base)} \approx \beta (r'_e + R_E)
$$

- Trở ra nhỏ, xấp xỉ:

$$
R_{out} \approx r'_e
$$

về trực giác thì CC không khuếch đại áp mạnh nhưng rất tốt để đệm tải.

## 4.9. Cách giải bài tập BJT

### Dạng 1: Phân cực DC

1. Xác định loại mạch phân cực
2. Tính $V_B$, $V_E$, $I_E$, $I_C$
3. Tính $V_C$, $V_{CE}$
4. Kết luận transistor ở vùng nào

### Dạng 2: Tìm điểm Q

1. Viết phương trình đường tải DC
2. Xác định hai giao điểm:
   - $I_C = 0 \Rightarrow V_{CE} = V_{CC}$
   - $V_{CE} = 0 \Rightarrow I_C \approx \dfrac{V_{CC}}{R_C + R_E}$
3. Tìm điểm Q bằng dòng base hoặc mạch phân cực
4. Kiểm tra Q có nằm giữa vùng active không

### Dạng 3: Khuếch đại tín hiệu nhỏ

1. Đưa nguồn DC về mass AC
2. Thay transistor bằng mô hình tín hiệu nhỏ
3. Tính $R_{in}$, $R_{out}$, $A_v$, $A_i$
4. Với CE, chú ý dấu âm do đảo pha

### Dạng 4: Đánh giá méo

1. So sánh biên độ tín hiệu AC với khoảng dao động quanh Q
2. Nếu Q gần saturation: đỉnh âm hoặc dương dễ bị cắt
3. Nếu Q gần cutoff: đầu ra dễ mất một nửa chu kỳ

# 5. FET: JFET và MOSFET

## 5.1. Đặc điểm chung

FET là transistor điều khiển bằng điện áp:

- Trở kháng vào rất lớn
- Dòng vào cổng gần như bằng 0

## 5.2. JFET

### Bản chất

- Dòng $I_D$ chạy từ Drain đến Source qua kênh dẫn
- Điện áp $V_{GS}$ điều khiển độ rộng kênh

### Thông số cơ bản

- $I_{DSS}$: dòng drain khi $V_{GS} = 0$
- $V_{GS(off)}$ hoặc $V_P$: điện áp khóa kênh

### Phương trình Shockley

- $I_D = I_{DSS}\left(1 - \dfrac{V_{GS}}{V_P}\right)^2$

Lưu ý:

- Với JFET kênh N, $V_P < 0$
- Ở chế độ hoạt động bình thường, $V_{GS}$ thường âm

### Các kiểu phân cực JFET

- Tự phân cực
- Phân cực cầu chia áp
- Phân cực nguồn dòng

### Tự phân cực

- $V_G \approx 0$
- $V_S = I_D R_S$
- $V_{GS} = V_G - V_S = -I_D R_S$

Thay vào Shockley để giải $I_D$

![Đặc tuyến truyền đạt của JFET](figures/06_jfet_transfer.png){ width=78% }

Đồ thị này mô hình hóa quan hệ điều khiển bằng điện áp của JFET:

- tại $V_{GS} = 0$, dòng drain đạt $I_{DSS}$
- khi $V_{GS}$ giảm dần về âm, kênh dẫn bị thu hẹp và $I_D$ giảm
- tại $V_{GS(off)} = V_P$, kênh gần như bị khóa hoàn toàn

Giải thích chi tiết:

- Đây là đặc tuyến truyền đạt, nghĩa là nó cho biết điện áp điều khiển ở cổng đã làm dòng drain biến đổi ra sao.
- JFET là phần tử điều khiển bằng điện áp; gate gần như không hút dòng nên tác động điều khiển đến từ điện trường chứ không phải do dòng cổng.
- Khi $V_{GS}$ âm hơn, vùng nghèo mở rộng vào trong kênh dẫn, tiết diện dẫn dòng nhỏ dần nên $I_D$ giảm.

### Họ đặc tuyến ra của JFET

Họ đặc tuyến ra giúp nhìn trực tiếp vùng ohmic và vùng active của JFET:

- Trục ngang: $V_{DS}$
- Trục đứng: $I_D$
- Mỗi đường ứng với một giá trị $V_{GS}$ cố định

![Họ đặc tuyến ra của JFET](figures/15_jfet_output_characteristic.png){ width=82% }

Cách đọc đồ thị:

- Khi $V_{DS}$ còn nhỏ, JFET làm việc gần giống một điện trở. Đây là vùng ohmic.
- Khi $V_{DS}$ tăng đến mức đủ lớn, kênh bị thắt lại ở gần drain, JFET đi vào vùng pinch-off/active.
- Trong vùng active, $I_D$ phụ thuộc chủ yếu vào $V_{GS}$, còn phụ thuộc ít hơn vào $V_{DS}$; do đó vùng này phù hợp cho khuếch đại.

Đặc điểm đi kèm theo vùng:

- Vùng ohmic: có thể dùng như điện trở điều khiển bằng điện áp.
- Vùng active: dùng cho khuếch đại common-source.
- Vùng cutoff: khi $V_{GS}$ âm đến gần $V_P$, kênh gần như đóng hoàn toàn và dòng drain rất nhỏ.

## 5.3. MOSFET

### Đặc điểm

- Cổng được cách điện bởi lớp oxide
- Trở kháng vào rất lớn

### Các loại

- D-MOSFET (kênh liên tục)
- E-MOSFET (kênh gián đoạn, thường dùng nhiều)

### E-MOSFET kênh N

- Chỉ dẫn khi $V_{GS} > V_{TH}$
- Miền bão hòa xấp xỉ:
  - $I_D = K(V_{GS} - V_{TH})^2$

### Đặc tuyến của E-MOSFET kênh N

Muốn hình dung đúng MOSFET, cần nhìn cả đặc tuyến truyền đạt và họ đặc tuyến ra:

![Đặc tuyến của E-MOSFET kênh N](figures/16_mosfet_characteristics.png){ width=95% }

Đồ thị bên trái là đặc tuyến truyền đạt $I_D$ theo $V_{GS}$:

- Khi $V_{GS} < V_{TH}$, kênh đảo chưa hình thành nên transistor gần như ngắt.
- Khi $V_{GS}$ vừa vượt ngưỡng, dòng bắt đầu xuất hiện.
- Khi tăng tiếp $V_{GS}$, mật độ điện tích trong kênh tăng và $I_D$ tăng mạnh theo quan hệ bình phương.

Đồ thị bên phải là họ đặc tuyến ra $I_D$ theo $V_{DS}$:

- Vùng đầu khi $V_{DS}$ nhỏ là vùng triode/ohmic, nơi MOSFET hành xử gần giống một điện trở điều khiển được.
- Khi thỏa:

$$
V_{DS} \ge V_{GS} - V_{TH}
$$

MOSFET đi vào vùng bão hòa theo nghĩa của linh kiện FET.

Đặc điểm của từng vùng:

- Cutoff: $V_{GS} < V_{TH}$, transistor tắt, phù hợp trạng thái OFF.
- Triode/ohmic: dòng tăng theo cả $V_{GS}$ lẫn $V_{DS}$, phù hợp mạch đóng cắt dẫn tốt.
- Bão hòa: dòng phụ thuộc chủ yếu vào $V_{GS}$, phù hợp cho khuếch đại tương tự.

Một điểm rất hay bị nhầm:

- "Bão hòa" của MOSFET trong mạch khuếch đại lại là vùng làm việc tốt cho khuếch đại.
- "Bão hòa" của BJT thì lại là vùng không còn khuếch đại tuyến tính tốt nữa.

## 5.4. Khuếch đại FET

### Cấu hình CS - Common Source

- Tương tự CE của BJT
- Có khuếch đại áp lớn
- Đảo pha 180 độ

Xấp xỉ:

- $A_v \approx -g_m (R_D \parallel R_L \parallel r_d)$

### Tham số tín hiệu nhỏ

- $g_m = \dfrac{\Delta I_D}{\Delta V_{GS}}$
- Với JFET:
  - $g_m = g_{m0}\left(1 - \dfrac{V_{GS}}{V_P}\right)$
  - $g_{m0} = \dfrac{2I_{DSS}}{|V_P|}$

Ý nghĩa vật lý của $g_m$:

- Nó đo xem điện áp gate thay đổi rất nhỏ sẽ kéo dòng drain thay đổi mạnh đến đâu.
- $g_m$ càng lớn thì khả năng biến đổi tín hiệu điều khiển điện áp thành biến thiên dòng càng mạnh.
- Vì vậy $g_m$ là tham số quan trọng nhất khi tính độ lợi của tầng common-source.

## 5.5. Cách giải bài tập FET

### Dạng 1: Tính điểm làm việc JFET

1. Viết $V_G$, $V_S$, $V_{GS}$
2. Dùng Shockley:
   - $I_D = I_{DSS}\left(1 - \dfrac{V_{GS}}{V_P}\right)^2$
3. Giải hệ để tìm $I_D$
4. Tính:
   - $V_D = V_{DD} - I_D R_D$
   - $V_{DS} = V_D - V_S$

### Dạng 2: Phân tích khuếch đại CS

1. Tính Q-point trước
2. Tính $g_m$
3. Thay bằng mô hình tín hiệu nhỏ
4. Tính $A_v$, $Z_i$, $Z_o$

# 6. Op-Amp

## 6.1. Khái niệm

Op-Amp là bộ khuếch đại vi sai có:

- độ lợi vòng hở rất lớn
- trở kháng vào rất lớn
- trở kháng ra rất nhỏ
- khả năng khử nhiễu đồng pha tốt

## 6.2. Hai chế độ hoạt động chính

### Differential mode

- Hai đầu vào khác nhau
- Có thể:
  - single-ended
  - double-ended

### Common mode

- Hai đầu vào cùng pha, cùng biên độ
- Lý tưởng: đầu ra bằng 0

## 6.3. Đặc tuyến truyền đạt vòng hở

Muốn hiểu op-amp làm comparator hay làm khuếch đại tuyến tính, phải nhìn đặc tuyến truyền đạt vòng hở:

- Trục ngang: $V_d = V_+ - V_-$
- Trục đứng: $V_{out}$

![Đặc tuyến truyền đạt vòng hở của Op-Amp](figures/17_opamp_transfer_characteristic.png){ width=82% }

Giải thích rất cụ thể:

- Khi $V_d$ dương, nghĩa là đầu không đảo cao hơn đầu đảo, đầu ra có xu hướng tăng dương.
- Khi $V_d$ âm, đầu ra có xu hướng giảm âm.
- Vì độ lợi vòng hở $A_{OL}$ rất lớn, vùng tuyến tính chỉ tồn tại trong một khoảng $V_d$ cực nhỏ quanh 0.
- Chỉ cần một sai khác đầu vào rất nhỏ là đầu ra đã lao nhanh tới gần mức bão hòa dương hoặc âm.

Cơ sở công thức:

$$
V_{out} = A_{OL}(V_+ - V_-)
$$

nhưng biểu thức này chỉ đúng khi đầu ra còn chưa chạm giới hạn nguồn. Trong thực tế luôn có ràng buộc:

$$
-|V_{sat}| \le V_{out} \le |V_{sat}|
$$

Đặc điểm của từng vùng:

- Vùng tuyến tính rất hẹp quanh $V_d = 0$: dùng trong mạch có hồi tiếp âm như mạch đảo, không đảo, theo áp, tích phân, vi phân.
- Vùng bão hòa dương: đầu ra gần $+V_{sat}$, thường xuất hiện khi dùng op-amp như comparator.
- Vùng bão hòa âm: đầu ra gần $-V_{sat}$, cũng là chế độ comparator.

Điều phải ghi nhớ:

- Không có hồi tiếp âm thì op-amp rất dễ bão hòa.
- Có hồi tiếp âm thì mạch tự ép $V_+ \approx V_-$ để giữ đầu ra trong vùng tuyến tính.

## 6.4. Thông số quan trọng

- $A_{OL}$: độ lợi vòng hở
- $Z_{in}$: trở kháng đầu vào
- $Z_{out}$: trở kháng đầu ra
- $\mathrm{CMRR}$: hệ số khử đồng pha
- Slew rate
- Input offset voltage
- Input bias current
- Maximum output swing
- Bandwidth

### Hệ số CMRR

- $\mathrm{CMRR} = \dfrac{A_{DM}}{A_{CM}}$
- Theo dB:
  - $\mathrm{CMRR}_{dB} = 20 \log_{10}(\mathrm{CMRR})$

## 6.5. Quy tắc vàng khi có hồi tiếp âm và op-amp lý tưởng

Nếu op-amp làm việc tuyến tính và chưa bão hòa:

- $I_+ = I_- = 0$
- $V_+ \approx V_-$

## 6.6. Mạch khuếch đại cơ bản

### Mạch đảo

- $A_v = \dfrac{V_o}{V_i} = -\dfrac{R_f}{R_{in}}$
- Trở vào xấp xỉ $R_{in}$

![Mô hình mạch khuếch đại đảo dùng Op-Amp](figures/07_opamp_inverting_model.png){ width=92% }

Các chi tiết quan trọng trên mô hình:

- đầu không đảo nối mass nên đầu đảo hình thành mass ảo khi có hồi tiếp âm
- $R_{in}$ đặt dòng vào nút đảo
- $R_f$ đưa tín hiệu hồi tiếp từ ngõ ra về
- dấu âm trong công thức là hệ quả trực tiếp của cấu trúc hồi tiếp này

### Mạch không đảo

- $A_v = 1 + \dfrac{R_f}{R_1}$
- Trở vào rất lớn

### Mạch theo áp

- $A_v = 1$
- Dùng để đệm trở kháng

## 6.7. Ảnh hưởng của hồi tiếp âm

Từ nội dung slide:

- tăng ổn định
- giảm méo
- mở rộng băng thông
- tăng trở vào ở mạch không đảo
- giảm trở ra

Quan hệ điển hình:

- $A_{CL} = \dfrac{A_{OL}}{1 + A_{OL}\beta}$

## 6.8. Băng thông và độ lợi

- Op-amp có tích độ lợi-băng thông gần như hằng số trong nhiều loại phổ thông
- Tăng độ lợi vòng kín thì băng thông giảm

## 6.9. Cách giải bài tập Op-Amp cơ bản

1. Kiểm tra có hồi tiếp âm không
2. Nếu có và chưa bão hòa:
   - đặt `V+ = V-`
   - đặt dòng vào hai cổng bằng 0
3. Viết KCL tại nút vào
4. Giải $V_{out}$
5. Kiểm tra đầu ra có vượt giới hạn nguồn cấp không

# 7. Ứng dụng Op-Amp

## 7.1. Mạch so sánh

- Không làm việc tuyến tính
- Đầu ra bão hòa dương hoặc âm tùy:
  - $V_+ > V_-$ $\Rightarrow$ $V_{out} \approx +V_{sat}$
  - $V_+ < V_-$ $\Rightarrow$ $V_{out} \approx -V_{sat}$

### Schmitt trigger

- Có hồi tiếp dương
- Tạo ngưỡng trên `UTP` và ngưỡng dưới `LTP`
- Chống nhiễu tốt hơn

![Dạng sóng của mạch so sánh Op-Amp](figures/08_opamp_comparator_waveform.png){ width=90% }

Hình biểu diễn rõ nguyên lý comparator:

- khi $V_{in}$ vượt $V_{ref}$, đầu ra bật lên mức bão hòa dương
- khi $V_{in}$ thấp hơn $V_{ref}$, đầu ra rơi xuống mức bão hòa âm
- vì vậy comparator biến tín hiệu analog thành tín hiệu hai mức rất trực quan

## 7.2. Mạch cộng

Với mạch cộng đảo:

- $V_{out} = -R_f \left(\dfrac{V_1}{R_1} + \dfrac{V_2}{R_2} + \cdots + \dfrac{V_n}{R_n}\right)$

Nếu $R_1 = R_2 = \cdots = R_f$:

- $V_{out} = -(V_1 + V_2 + \cdots + V_n)$

Nếu là mạch cộng có trọng số:

$$
V_{out} = -\left(\dfrac{R_f}{R_1}V_1 + \dfrac{R_f}{R_2}V_2 + \cdots + \dfrac{R_f}{R_n}V_n\right)
$$

Ý nghĩa:

- điện trở nào nhỏ hơn thì tín hiệu tương ứng có trọng số lớn hơn
- đây là cơ sở của các mạch cộng có trọng số và DAC điện trở

## 7.3. Mạch trừ

Nếu điện trở ghép đúng tỉ lệ:

- $V_{out} = \left(\dfrac{R_2}{R_1}\right)(V_2 - V_1)$

Điều kiện để công thức trên đúng:

$$
\dfrac{R_2}{R_1} = \dfrac{R_4}{R_3}
$$

Khi đó mạch hoạt động như bộ trừ điện áp hay bộ khuếch đại sai biệt.

Trường hợp đặc biệt nếu:

$$
R_1 = R_3,\qquad R_2 = R_4
$$

thì:

$$
V_{out} = \left(\dfrac{R_2}{R_1}\right)(V_2 - V_1)
$$

Nếu tiếp tục có:

$$
R_1 = R_2 = R_3 = R_4
$$

thì:

$$
V_{out} = V_2 - V_1
$$

Đây là dạng rất hay gặp trong bài trắc nghiệm và bài tính nhanh.

## 7.4. Mạch vi sai

Mạch vi sai op-amp thực chất là mạch lấy hiệu hai tín hiệu vào rồi khuếch đại hiệu đó.

Công thức tổng quát trong trường hợp điện trở ghép đúng tỉ lệ:

$$
V_{out} = A_d (V_2 - V_1)
$$

với:

$$
A_d = \dfrac{R_2}{R_1} = \dfrac{R_4}{R_3}
$$

Trường hợp cân bằng đơn giản nhất:

$$
R_1 = R_3,\qquad R_2 = R_4
$$

thì:

$$
V_{out} = \left(\dfrac{R_2}{R_1}\right)(V_2 - V_1)
$$

Trường hợp gain bằng 1:

$$
R_1 = R_2 = R_3 = R_4
$$

thì:

$$
V_{out} = V_2 - V_1
$$

Ý nghĩa phải nhớ:

- mạch vi sai khuếch đại phần chênh lệch giữa hai tín hiệu
- nếu cả hai đầu vào cùng tăng giống nhau thì đầu ra lý tưởng không đổi
- đây là nền tảng của khái niệm khử tín hiệu đồng pha
## 7.5. Mạch tích phân

- $V_{out} = -\dfrac{1}{RC}\int V_{in}\,dt$

Đặc tính:

- vào xung vuông -> ra tam giác
- vào DC -> ra dốc tuyến tính

## 7.6. Mạch vi phân

- $V_{out} = -RC \,\dfrac{dV_{in}}{dt}$

Đặc tính:

- nhạy với cạnh xung
- dễ khuếch đại nhiễu tần số cao

## 7.7. Cách giải bài tập ứng dụng Op-Amp

### Mạch so sánh

1. So sánh hai đầu vào
2. Suy ra dấu đầu ra
3. Giới hạn ở $\pm V_{sat}$

### Mạch cộng/trừ

1. Dùng quy tắc `V+ = V-` nếu hồi tiếp âm
2. Viết KCL tại nút vào đảo
3. Rút $V_{out}$

### Mạch tích phân/vi phân

1. Xác định quan hệ toán học giữa vào và ra
2. Chia tín hiệu vào theo từng đoạn thời gian
3. Tính độ dốc hoặc diện tích để vẽ dạng sóng ra

# 8. Mạch dao động

## 8.1. Điều kiện Barkhausen

Để mạch dao động tự duy trì:

- Tổng lệch pha quanh vòng bằng `0°` hoặc `360°`
- Độ lợi vòng $|A\beta| = 1$ khi dao động ổn định

Điều kiện khởi động:

- Ban đầu cần $|A\beta| > 1$

## 8.2. Dao động cầu Wien

Theo slide:

- dùng mạng `lead-lag RC`
- thích hợp tạo sin tần số thấp, thường dưới `1 MHz`
- tại tần số cộng hưởng:
  - lệch pha bằng `0`
  - độ suy hao mạng hồi tiếp khoảng `1/3`

Điều kiện khuếch đại:

- mạch khuếch đại cần có độ lợi khoảng `3`

Tần số dao động với phần tử đối xứng:

- $f_0 = \dfrac{1}{2\pi R C}$

![Quá trình khởi động của dao động cầu Wien](figures/11_wien_oscillator_waveform.png){ width=88% }

Đây là hình đặc biệt quan trọng vì nó mô tả động học khởi động:

- dao động ban đầu rất nhỏ, xuất phát từ nhiễu
- khi $|A\beta| > 1$, biên độ tăng dần
- khi cơ chế ổn định tác động, biên độ dừng lại và mạch tạo sóng sin gần ổn định

## 8.3. Công thức trọng tâm của mạch dao động

### 8.3.1. Điều kiện Barkhausen dưới dạng công thức

Muốn một mạch tự dao động, tín hiệu sau khi đi hết một vòng khuếch đại và hồi tiếp phải quay trở lại **đúng pha** và **đủ lớn** để tự duy trì.

Công thức chuẩn:

- Điều kiện pha:

$$
\angle A\beta = 0^\circ \quad \text{hoặc} \quad 360^\circ
$$

- Điều kiện biên độ khi dao động ổn định:

$$
|A\beta| = 1
$$

- Điều kiện khởi động thực tế:

$$
|A\beta| > 1
$$

- Dạng gộp ngắn gọn:

$$
A\beta = 1\angle 0^\circ
$$

Ý nghĩa:

- nếu $|A\beta| < 1$ thì sau mỗi vòng, biên độ giảm dần và dao động tắt
- nếu $|A\beta| > 1$ thì sau mỗi vòng, biên độ tăng dần
- nếu $|A\beta| = 1$ thì biên độ giữ ổn định

Đây là bộ công thức nền tảng nhất của toàn bộ chương dao động.

### 8.3.2. Công thức của mạch dao động cầu Wien

Với cầu Wien đối xứng:

- $R_1 = R_2 = R$
- $C_1 = C_2 = C$

thì tần số dao động là:

$$
f_0 = \dfrac{1}{2\pi RC}
$$

và tần số góc:

$$
\omega_0 = 2\pi f_0 = \dfrac{1}{RC}
$$

Ý nghĩa:

- tăng $R$ thì $f_0$ giảm
- tăng $C$ thì $f_0$ giảm
- giảm một trong hai đại lượng $R$ hoặc $C$ thì $f_0$ tăng

Nếu đề yêu cầu thiết kế ngược:

$$
R = \dfrac{1}{2\pi f_0 C}
$$

hoặc:

$$
C = \dfrac{1}{2\pi f_0 R}
$$

Đây là hai công thức cực hay gặp khi đề cho trước tần số dao động rồi bắt tính linh kiện.

### 8.3.3. Hệ số hồi tiếp của cầu Wien

Tại đúng tần số dao động, mạng RC của cầu Wien:

- không làm lệch pha
- nhưng làm suy hao biên độ

Giá trị hồi tiếp gần đúng:

$$
\beta = \dfrac{1}{3}
$$

Do đó điều kiện Barkhausen về biên độ:

$$
A\beta = 1
$$

suy ra:

$$
A = \dfrac{1}{\beta} = \dfrac{1}{1/3} = 3
$$

Kết luận rất quan trọng:

- khi dao động đã ổn định, bộ khuếch đại cần gain xấp xỉ `3`
- khi mới khởi động, trong thực tế thường cần gain hơi lớn hơn `3` để bù tổn hao

Nói ngắn gọn:

- `khởi động`: $A > 3$
- `ổn định`: $A \approx 3$

### 8.3.4. Nếu bộ khuếch đại là op-amp không đảo

Với op-amp mắc không đảo:

$$
A_v = 1 + \dfrac{R_f}{R_g}
$$

Muốn thỏa điều kiện cầu Wien ở trạng thái ổn định:

$$
A_v = 3
$$

nên:

$$
1 + \dfrac{R_f}{R_g} = 3
$$

$$
\dfrac{R_f}{R_g} = 2
$$

$$
R_f = 2R_g
$$

Đây là công thức rất hay dùng trong bài thiết kế điện trở của mạch cầu Wien.

### 8.3.5. Quan hệ giữa khởi động và méo dạng sóng

Nếu chọn gain quá nhỏ:

$$
|A\beta| < 1
$$

thì mạch không thể tự dao động hoặc dao động sẽ tắt dần.

Nếu chọn gain quá lớn:

$$
|A\beta| \gg 1
$$

thì biên độ tăng nhanh, op-amp hoặc transistor sẽ tiến tới bão hòa, làm dạng sóng bị méo.

Vì vậy trong mạch thực thường có cơ chế ổn định biên độ để đưa hệ về gần:

$$
|A\beta| = 1
$$

Đây là cơ sở vật lý giải thích vì sao đề bài thường hỏi:

- vì sao dao động không khởi động
- vì sao dao động bị cắt đỉnh
- vì sao gain không nên chọn quá lớn

### 8.3.6. Tóm tắt công thức cần nhớ nhanh

- Điều kiện pha:

$$
\angle A\beta = 0^\circ \text{ hoặc } 360^\circ
$$

- Điều kiện biên độ ổn định:

$$
|A\beta| = 1
$$

- Điều kiện khởi động:

$$
|A\beta| > 1
$$

- Cầu Wien đối xứng:

$$
f_0 = \dfrac{1}{2\pi RC}
$$

$$
\omega_0 = \dfrac{1}{RC}
$$

- Hệ số hồi tiếp tại $f_0$:

$$
\beta = \dfrac{1}{3}
$$

- Gain bộ khuếch đại cần có:

$$
A = 3
$$

- Nếu dùng op-amp không đảo:

$$
A_v = 1 + \dfrac{R_f}{R_g}
$$

$$
R_f = 2R_g
$$

## 8.4. Dạng bài tập dao động

1. Xác định loại dao động
2. Viết điều kiện pha
3. Viết điều kiện biên độ
4. Suy ra tần số dao động
5. Tìm điện trở đặt độ lợi nếu đề yêu cầu

# 9. Mạch lọc thụ động

## 9.1. Khái niệm

Mạch lọc cho tín hiệu mong muốn đi qua và làm suy giảm tín hiệu không mong muốn theo tần số.

## 9.2. Các loại cơ bản

- Thông thấp (low-pass)
- Thông cao (high-pass)
- Thông dải (band-pass)
- Triệt dải (band-stop/notch)

## 9.3. Đáp ứng tần số

Các khái niệm cần nhớ:

- Tần số cắt $f_c$
- Băng thông `BW`
- Tần số trung tâm $f_0$
- Pole (cực)
- Độ dốc suy giảm `roll-off`
- Độ lợi theo dB:
- $A_v(\mathrm{dB}) = 20\log_{10}\left(\dfrac{V_{out}}{V_{in}}\right)$

### Pole là gì

Pole là nghiệm của mẫu số hàm truyền. Nếu:

$$
H(s) = \frac{N(s)}{D(s)}
$$

thì pole là các giá trị của $s$ sao cho:

$$
D(s) = 0
$$

Về trực giác mạch điện:

- pole là nguyên nhân làm đáp ứng bắt đầu suy giảm theo tần số
- mỗi pole thường gắn với một cơ chế tích trữ năng lượng do `C` hoặc `L`
- số pole thường trùng với bậc của mạch lọc

Ví dụ:

- lọc RC bậc một có `1 pole`
- lọc bậc hai kiểu Sallen-Key có `2 pole`

### Roll-off là gì

`Roll-off` là độ dốc suy giảm của đáp ứng biên độ khi tần số đi ra khỏi dải thông.

Đơn vị thường dùng:

- `dB/decade`
- `dB/octave`

Trong thực hành mạch điện tử, thường dùng nhất là `dB/dec`.

Ý nghĩa:

- `-20 dB/dec` nghĩa là khi tần số tăng `10 lần`, biên độ giảm `20 dB`
- `-40 dB/dec` nghĩa là suy giảm nhanh hơn, lọc sắc hơn

### Quan hệ giữa pole và roll-off

Mỗi pole bậc một đóng góp gần đúng:

$$
-20\,\mathrm{dB/dec}
$$

Do đó:

- `1 pole` $\rightarrow -20\,\mathrm{dB/dec}$
- `2 pole` $\rightarrow -40\,\mathrm{dB/dec}$
- `3 pole` $\rightarrow -60\,\mathrm{dB/dec}$

Đây là quy tắc đọc Bode rất quan trọng:

- pole là nguyên nhân
- roll-off là biểu hiện của pole trên đồ thị biên độ

### Ý nghĩa thực tế của pole và roll-off

- Nếu số pole ít, mạch đơn giản nhưng khả năng chặn tần số ngoài dải không quá mạnh.
- Nếu số pole nhiều, mạch lọc chặn mạnh hơn nhưng thiết kế phức tạp hơn và nhạy hơn với sai số linh kiện.
- Trong bài tập, chỉ cần nhìn số pole là có thể ước lượng nhanh độ dốc của Bode mà chưa cần thay số chi tiết.

### Điểm `-3 dB`

Với bộ lọc bậc một, tại tần số cắt:

$$
|H(j\omega_c)| = \frac{1}{\sqrt{2}}
$$

nên:

$$
A_v(\mathrm{dB}) = 20\log_{10}\left(\frac{1}{\sqrt{2}}\right) \approx -3\,\mathrm{dB}
$$

Vì vậy trên đồ thị Bode, $f_c$ thường được xác định tại mức `-3 dB`.

## 9.4. Mạch RC bậc nhất

### Thông thấp RC

- $f_c = \dfrac{1}{2\pi R C}$
- Với $f \ll f_c$: tín hiệu qua gần như nguyên vẹn
- Với $f \gg f_c$: suy giảm mạnh

### Thông cao RC

- $f_c = \dfrac{1}{2\pi R C}$
- Với $f \ll f_c$: suy giảm
- Với $f \gg f_c$: qua tốt

![Đáp ứng tần số của lọc RC bậc một](figures/09_rc_filter_bode.png){ width=88% }

Từ đồ thị Bode này có thể quan sát ngay:

- lọc thông thấp giữ tốt thành phần thấp tần rồi suy giảm sau $f_c$
- lọc thông cao loại bỏ miền thấp tần và tiến dần tới miền qua tốt ở tần số cao
- tại $f_c$, độ lợi xấp xỉ $-3\,\mathrm{dB}$
- với mạch bậc một, độ dốc suy giảm có độ lớn xấp xỉ `20 dB/dec`
- độ dốc này xuất hiện vì mạch chỉ có `1 pole`

## 9.5. Thông dải và triệt dải

- Có thể ghép thông cao và thông thấp
- Tần số trung tâm:
  - $f_0 = \sqrt{f_L f_H}$
- Băng thông:
  - $BW = f_H - f_L$

![Đáp ứng của mạch lọc thông dải](figures/10_bandpass_response.png){ width=84% }

Hình này mô tả bản chất của thông dải:

- chỉ một miền quanh `f_0` được cho qua
- hai phía hai bên đều suy giảm
- độ nhọn của đỉnh phản ánh mức chọn lọc hay hệ số `Q`

## 9.6. Cách giải bài tập lọc thụ động

1. Nhận dạng loại mạch lọc
2. Xác định linh kiện thấy ở ngõ ra
3. Dùng giới hạn:
   - `f = 0`
   - `f -> ∞`
4. Suy ra loại lọc
5. Tính $f_c$ từ $\dfrac{1}{2\pi R C}$
6. Nếu cần vẽ Bode, đánh dấu:
   - vùng bằng phẳng
   - điểm `-3 dB`
   - độ dốc `20 dB/dec` mỗi cực

### Cách làm bài có pole và roll-off

1. Viết hàm truyền $H(s)$.
2. Tìm pole bằng cách giải mẫu số bằng 0.
3. Đếm số pole để xác định bậc lọc.
4. Suy ra `roll-off` gần đúng bằng:
   - `-20 dB/dec` cho mỗi pole bậc một
5. Nếu cần chi tiết hơn, thay $s = j\omega$ để tìm $|H(j\omega)|$ và pha.

# 10. Mạch lọc tích cực

## 10.1. Khái niệm

Mạch lọc tích cực dùng op-amp kết hợp `R`, `C` để:

- lọc tín hiệu
- có thể khuếch đại
- tránh dùng cuộn cảm trong nhiều trường hợp

![Mô hình hóa mạch lọc tích cực](figures/12_active_filter_block.png){ width=92% }

Hình này giúp nhìn mạch lọc tích cực đúng bản chất chức năng:

- mạng `RC` quyết định miền tần số được chọn
- op-amp nâng mức tín hiệu và cách ly tải
- nhánh hồi tiếp đặt ra dạng đáp ứng và độ lợi của cả hệ

## 10.2. Các dạng chính

- Thông thấp tích cực
- Thông cao tích cực
- Thông dải tích cực
- Triệt dải tích cực

## 10.3. Bộ lọc bậc một

### Thông thấp bậc một

- $f_c = \dfrac{1}{2\pi R C}$
- $A_v = 1 + \dfrac{R_f}{R_1}$ với cấu hình không đảo nếu có khuếch đại

### Thông cao bậc một

- $f_c = \dfrac{1}{2\pi R C}$
- `roll-off = 20 dB/dec`

## 10.4. Bộ lọc bậc hai

### Sallen-Key

- Rất phổ biến
- Độ dốc:
  - `40 dB/dec` cho bậc hai

Các đáp ứng:

- Butterworth: biên độ phẳng trong băng thông
- Có thể phải chọn tỉ số điện trở để đạt đáp ứng chuẩn

## 10.5. Dạng bài tập lọc tích cực

1. Xác định bậc lọc
2. Nhận dạng loại đáp ứng
3. Tính $f_c$ hoặc $f_0$
4. Nếu đề yêu cầu Butterworth, dùng điều kiện hệ số khuếch đại hay tỉ số điện trở tương ứng
5. Kiểm tra độ dốc:
   - bậc 1: `20 dB/dec`
   - bậc 2: `40 dB/dec`

# 11. Công thức trọng tâm cần học thuộc

## 11.1. Cơ sở

- `Q = I.t`
- `I = ΔQ/Δt`
- `U = I.R`
- `P = U.I`
- $X_C = \dfrac{1}{2\pi f C}$
- $X_L = 2\pi f L$

## 11.2. Diode

- $I \approx \dfrac{V_S - 0.7}{R}$
- $V_D = V_\gamma + I_D r_d$
- Bán kỳ: $V_{DC} \approx \dfrac{V_m}{\pi}$
- Toàn kỳ: $V_{DC} \approx \dfrac{2V_m}{\pi}$
- Gợn tụ lọc: $V_{r(pp)} \approx \dfrac{I_L}{f_r C}$
- Zener: $I_Z = I_R - I_L$

## 11.3. BJT

- $I_E = I_B + I_C$
- $\beta = \dfrac{I_C}{I_B}$
- $\alpha = \dfrac{I_C}{I_E}$
- $I_C = \beta I_B$
- $r'_e \approx \dfrac{25\,\mathrm{mV}}{I_E}$
- $r_\pi = \beta r'_e$
- $g_m = \dfrac{I_C}{V_T}$, với $V_T \approx 25\,\mathrm{mV}$
- $g_m \approx \dfrac{1}{r'_e}$
- CE bypass emitter:
  - $A_v \approx -\dfrac{R_C \parallel R_L}{r'_e}$
- CE nếu xét mô hình $g_m$:
  - $A_v \approx -g_m(R_C \parallel R_L \parallel r_o)$
- Trở vào nhìn từ base:
  - $R_{in(base)} \approx r_\pi = \beta r'_e$
- Nếu không bypass emitter:
  - $R_{in(base)} \approx \beta (r'_e + R_E)$
- Trở vào toàn mạch gần đúng:
  - $R_{in} \approx R_B \parallel R_{in(base)}$
- Trở ra CE gần đúng:
  - $R_{out} \approx R_C$
- CC / emitter follower:
  - $A_v \approx 1$
  - $R_{out} \approx r'_e$
- CB:
  - $R_{in} \approx r'_e$
- Đặc điểm CE:
  - khuếch đại áp lớn
  - khuếch đại dòng khá tốt
  - đảo pha $180^\circ$
  - trở vào trung bình, trở ra tương đối lớn
- Đặc điểm CC:
  - còn gọi là emitter follower
  - $A_v \approx 1$
  - không đảo pha
  - trở vào lớn
  - trở ra nhỏ
  - phù hợp làm tầng đệm
- Đặc điểm CB:
  - không đảo pha
  - trở vào rất nhỏ
  - trở ra lớn
  - khuếch đại áp tốt nhưng khuếch đại dòng kém
  - hay gặp trong bài cần nhớ về phối hợp trở kháng hoặc tần số cao

## 11.4. JFET/MOSFET

- $I_D = I_{DSS}\left(1 - \dfrac{V_{GS}}{V_P}\right)^2$
- Với JFET:
  - $V_{GS} = V_G - V_S$
  - thường $V_G \approx 0$ và $V_{GS} < 0$ trong self-bias kênh N
- Tại $V_{GS} = 0$:
  - $I_D = I_{DSS}$
- Tại cutoff:
  - $V_{GS} = V_P$
  - $I_D = 0$
- Độ dẫn truyền của JFET:
  - $g_m = \dfrac{\Delta I_D}{\Delta V_{GS}}$
  - $g_m = g_{m0}\left(1 - \dfrac{V_{GS}}{V_P}\right)$
- Với:
  - $g_{m0} = \dfrac{2I_{DSS}}{|V_P|}$

### Công thức AC của mạch khuếch đại JFET

Các công thức dưới đây dùng cho miền trung tần, tức là tụ ghép và tụ bypass được xem như ngắn mạch, nguồn DC được đưa về mass AC. Trước khi tính AC phải tìm điểm tĩnh $Q$ để có $I_{DQ}$, $V_{GSQ}$ và $V_{DSQ}$.

Quy tắc đổi sang mạch AC:

- $V_{DD}$ nối mass AC.
- Tụ ghép ngõ vào và ngõ ra xem như ngắn mạch.
- Nếu tụ bypass source $C_S$ đủ lớn, source xem như nối mass AC.
- Gate JFET gần như không hút dòng nên $i_g \approx 0$.
- JFET được thay bằng nguồn dòng phụ thuộc $g_mv_{gs}$ từ drain xuống source, song song với điện trở ra nhỏ tín hiệu $r_d$ nếu đề có cho.

Các điện trở hay dùng:

- Điện trở bias nhìn từ gate về mass AC:
  - Nếu dùng một điện trở gate: $R_G$.
  - Nếu dùng cầu chia áp: $R_G = R_1 \parallel R_2$.
- Điện trở tải AC ở drain khi có tải ngoài:

$$
R_D' = R_D \parallel R_L
$$

- Nếu không có tải ngoài thì lấy $R_D' = R_D$.
- Nếu đề không cho $r_d$, thường xem $r_d \to \infty$.

Tính $g_m$ tại điểm $Q$:

$$
g_m = g_{m0}\left(1 - \dfrac{V_{GSQ}}{V_P}\right)
$$

$$
g_{m0} = \dfrac{2I_{DSS}}{|V_P|}
$$

Có thể tính trực tiếp theo $I_{DQ}$:

$$
g_m = \dfrac{2}{|V_P|}\sqrt{I_{DSS}I_{DQ}}
$$

Hoặc nếu đã biết $g_{m0}$:

$$
g_m = g_{m0}\sqrt{\dfrac{I_{DQ}}{I_{DSS}}}
$$

#### Trường hợp 1: source được bypass hoàn toàn

Khi $C_S$ đủ lớn, $R_S$ bị nối tắt trong AC:

$$
v_s \approx 0,\qquad v_{gs} \approx v_i
$$

Trở vào:

$$
R_{in} \approx R_G
$$

Nếu có điện trở nguồn tín hiệu $R_{sig}$ thì điện áp thật vào gate là:

$$
v_g = v_{sig}\dfrac{R_{in}}{R_{sig}+R_{in}}
$$

Độ lợi áp từ gate ra drain, bỏ qua $r_d$:

$$
A_v = \dfrac{v_o}{v_g} \approx -g_mR_D'
$$

Nếu có xét $r_d$:

$$
A_v \approx -g_m(R_D' \parallel r_d)
$$

Nếu muốn tính từ nguồn tín hiệu đến ngõ ra:

$$
A_{vs} = \dfrac{v_o}{v_{sig}}
       \approx \left[-g_m(R_D' \parallel r_d)\right]
       \dfrac{R_{in}}{R_{sig}+R_{in}}
$$

Trở ra khi chưa gắn tải ngoài:

$$
R_{out} \approx R_D \parallel r_d
$$

Nếu bỏ qua $r_d$:

$$
R_{out} \approx R_D
$$

#### Trường hợp 2: source không được bypass

Khi không có tụ bypass, hoặc tụ bypass không đủ lớn ở tần số đang xét, $R_S$ xuất hiện trong mạch AC và tạo hồi tiếp âm. Khi bỏ qua $r_d$:

$$
A_v \approx -\dfrac{g_mR_D'}{1+g_mR_S}
$$

Dạng tương đương hay gặp:

$$
A_v \approx -\dfrac{R_D'}{R_S+\dfrac{1}{g_m}}
$$

Trở vào vẫn gần đúng là:

$$
R_{in} \approx R_G
$$

Nếu có xét $r_d$, công thức đầy đủ hơn cho common-source có $R_S$ không bypass là:

$$
A_v =
-\dfrac{g_m r_d R_D'}
{R_D' + r_d + R_S(1+g_mr_d)}
$$

Kiểm tra nhanh công thức này:

- Nếu $R_S = 0$ thì:

$$
A_v = -g_m(R_D' \parallel r_d)
$$

- Nếu $r_d \to \infty$ thì:

$$
A_v \approx -\dfrac{g_mR_D'}{1+g_mR_S}
$$

Trở ra khi gate nối mass AC và chưa gắn tải ngoài:

$$
R_{out} \approx R_D \parallel \left[r_d + R_S(1+g_mr_d)\right]
$$

Nếu bỏ qua $r_d$ thì dùng gần đúng:

$$
R_{out} \approx R_D
$$

#### Trường hợp 3: bypass source không hoàn toàn

Nếu cần xét theo tần số, thay $R_S$ trong công thức bằng tổng trở source AC:

$$
Z_S = R_S \parallel \dfrac{1}{j\omega C_S}
$$

Bỏ qua $r_d$:

$$
A_v(j\omega) \approx -\dfrac{g_mR_D'}{1+g_mZ_S}
$$

Ở tần số thấp, $C_S$ chưa ngắn mạch tốt nên $|Z_S|$ lớn, gain giảm. Ở trung tần, $C_S$ gần như ngắn mạch nên $Z_S \approx 0$ và gain tăng về:

$$
A_v \approx -g_mR_D'
$$

#### Ghi nhớ khi có $r_d$

- Nếu source là mass AC: đưa $r_d$ song song trực tiếp với tải drain:

$$
R_{AC} = R_D \parallel R_L \parallel r_d
$$

$$
A_v \approx -g_mR_{AC}
$$

- Nếu source còn $R_S$ trong AC: không được chỉ lấy $R_D'\parallel r_d$ rồi chia cho $1+g_mR_S$ một cách máy móc; công thức chính xác hơn là:

$$
A_v =
-\dfrac{g_m r_d R_D'}
{R_D' + r_d + R_S(1+g_mr_d)}
$$

- Trong phần lớn bài tập cơ bản, $r_d$ thường rất lớn so với $R_D$ và $R_L$, nên có thể bỏ qua để tính nhanh.
- E-MOSFET kênh N:
  - Điều kiện mở: $V_{GS} > V_{TH}$
  - Miền cutoff: $V_{GS} < V_{TH}$
  - Miền triode: $V_{DS} < V_{GS} - V_{TH}$
  - Miền saturation: $V_{DS} \ge V_{GS} - V_{TH}$
- Dòng bão hòa của E-MOSFET:
  - $I_D = K(V_{GS} - V_{TH})^2$
- Overdrive:
  - $V_{OV} = V_{GS} - V_{TH}$
- Khuếch đại common-source:
  - $A_v \approx -g_m(R_D \parallel R_L \parallel r_d)$
- Đặc điểm common-source (CS):
  - tương tự CE của BJT
  - khuếch đại áp tốt
  - đảo pha $180^\circ$
  - trở vào lớn
- Đặc điểm common-drain (CD):
  - còn gọi là source follower
  - $A_v \approx 1$
  - không đảo pha
  - trở vào lớn, trở ra nhỏ
  - phù hợp làm tầng đệm
- Đặc điểm common-gate (CG):
  - tương tự CB của BJT
  - không đảo pha
  - trở vào nhỏ
  - khuếch đại áp khá tốt
- Đặc điểm riêng của JFET:
  - gate phân cực nghịch
  - dòng gate gần như bằng 0
  - thường dùng phương trình Shockley để tìm điểm Q
- Đặc điểm riêng của E-MOSFET:
  - gate cách điện bởi oxide
  - trở vào rất lớn
  - phải có $V_{GS} > V_{TH}$ mới dẫn
  - thường gặp bài xác định cutoff, triode, saturation

## 11.5. Op-Amp

- $A_{CL} = \dfrac{A_{OL}}{1 + A_{OL}\beta}$
- Mạch đảo: $A_v = -\dfrac{R_f}{R_{in}}$
- Mạch không đảo: $A_v = 1 + \dfrac{R_f}{R_1}$
- Mạch theo áp: $A_v = 1$
- Mạch cộng đảo:
  - $V_{out} = -R_f\left(\dfrac{V_1}{R_1} + \dfrac{V_2}{R_2} + \cdots + \dfrac{V_n}{R_n}\right)$
- Nếu $R_1 = R_2 = \cdots = R_f$:
  - $V_{out} = -(V_1 + V_2 + \cdots + V_n)$
- Mạch cộng có trọng số:
  - $V_{out} = -\left(\dfrac{R_f}{R_1}V_1 + \dfrac{R_f}{R_2}V_2 + \cdots + \dfrac{R_f}{R_n}V_n\right)$
- Mạch trừ / khuếch đại sai biệt:
  - Điều kiện: $\dfrac{R_2}{R_1} = \dfrac{R_4}{R_3}$
  - $V_{out} = \left(\dfrac{R_2}{R_1}\right)(V_2 - V_1)$
- Nếu $R_1 = R_2 = R_3 = R_4$:
  - $V_{out} = V_2 - V_1$
- Dạng vi sai tổng quát:
  - $V_{out} = A_d (V_2 - V_1)$
  - $A_d = \dfrac{R_2}{R_1} = \dfrac{R_4}{R_3}$
- Tích phân: $V_{out} = -\dfrac{1}{RC}\int V_{in}\,dt$
- Vi phân: $V_{out} = -RC \dfrac{dV_{in}}{dt}$

## 11.6. Dao động

Nếu chỉ ôn gấp phần dao động, đây là nhóm công thức nên học thuộc trước:

1. Điều kiện pha:

$$
\angle A\beta = 0^\circ \text{ hoặc } 360^\circ
$$

2. Điều kiện biên độ ổn định:

$$
|A\beta| = 1
$$

3. Điều kiện khởi động:

$$
|A\beta| > 1
$$

4. Dạng viết gộp của Barkhausen:

$$
A\beta = 1\angle 0^\circ
$$

5. Tần số dao động cầu Wien đối xứng:

$$
f_0 = \dfrac{1}{2\pi RC}
$$

6. Tần số góc dao động:

$$
\omega_0 = \dfrac{1}{RC}
$$

7. Công thức tìm điện trở khi biết $f_0$ và $C$:

$$
R = \dfrac{1}{2\pi f_0 C}
$$

8. Công thức tìm tụ khi biết $f_0$ và $R$:

$$
C = \dfrac{1}{2\pi f_0 R}
$$

9. Hệ số hồi tiếp của cầu Wien tại tần số dao động:

$$
\beta = \dfrac{1}{3}
$$

10. Gain bộ khuếch đại cần có khi dao động ổn định:

$$
A = \dfrac{1}{\beta} = 3
$$

11. Nếu bộ khuếch đại dùng op-amp không đảo:

$$
A_v = 1 + \dfrac{R_f}{R_g}
$$

12. Điều kiện điện trở để mạch Wien ổn định:

$$
1 + \dfrac{R_f}{R_g} = 3
$$

$$
\dfrac{R_f}{R_g} = 2
$$

$$
R_f = 2R_g
$$

13. Ý nghĩa cần nhớ:

- $A < 3$ thì mạch khó hoặc không tự dao động
- $A > 3$ quá nhiều thì biên độ tăng mạnh và dễ méo
- $A \approx 3$ là trạng thái mong muốn khi dao động đã ổn định

## 11.7. Lọc

- $f_c = \dfrac{1}{2\pi R C}$
- $A_v(\mathrm{dB}) = 20\log_{10}\left(\dfrac{V_{out}}{V_{in}}\right)$
- $f_0 = \sqrt{f_L f_H}$
- $BW = f_H - f_L$
- $Q = \dfrac{f_0}{BW}$
- Tại tần số cắt bậc một:
  - $|H(j\omega_c)| = \dfrac{1}{\sqrt{2}}$
  - $A_v(\mathrm{dB}) \approx -3\,\mathrm{dB}$
- Mỗi pole bậc một:
  - `roll-off` $\approx -20\,\mathrm{dB/dec}$
- Hai pole:
  - `roll-off` $\approx -40\,\mathrm{dB/dec}$
- Ba pole:
  - `roll-off` $\approx -60\,\mathrm{dB/dec}$
- Thông thấp RC:
  - $H(s) = \dfrac{1}{1+sRC}$
- Thông cao RC:
  - $H(s) = \dfrac{sRC}{1+sRC}$
- Đáp ứng tần số:
  - thay $s = j\omega$
- Pole:
  - là nghiệm của mẫu số hàm truyền
- Thông dải:
  - $BW = f_H - f_L$
  - $f_0 = \sqrt{f_L f_H}$
  - $Q = \dfrac{f_0}{BW}$
- Sallen-Key bậc hai:
  - `roll-off` $\approx 40\,\mathrm{dB/dec}$
- Butterworth:
  - biên độ phẳng trong dải thông

# 12. Chiến lược học và làm bài thi

## 12.1. Khi gặp bài phân tích mạch

1. Xác định mạch DC hay AC
2. Xác định linh kiện đang làm việc ở chế độ nào
3. Chọn mô hình phù hợp:
   - diode lý tưởng hay thực
   - BJT active/cutoff/saturation
   - JFET với Shockley
   - op-amp lý tưởng có hồi tiếp âm
4. Viết công thức trước khi thay số
5. Kiểm tra kết quả có hợp lý vật lý hay không

Nên gắn cách giải với hình minh họa:

- diode: xác định ngay đang nằm ở vùng nào trên đặc tuyến
- BJT: đặt điểm `Q` lên đường tải trước khi phân tích khuếch đại
- JFET: dùng đồ thị truyền đạt để ước lượng $I_D$
- op-amp: nhìn chiều hồi tiếp để phân biệt tuyến tính hay so sánh
- bộ lọc: nhìn Bode để hiểu miền tần số qua và chặn trước khi thay số

## 12.2. Khi vẽ dạng sóng

1. Xác định dạng tín hiệu vào
2. Xác định mốc ngưỡng chuyển trạng thái
3. Xét theo từng khoảng thời gian
4. Đánh dấu mức bão hòa hoặc mức rơi áp diode

## 12.3. Sai lầm thường gặp

- Quên kiểm tra giả thiết diode dẫn/ngắt
- Dùng $I_C = \beta I_B$ ngay cả khi BJT đã bão hòa
- Quên $V_{BE} \approx 0.7\,\mathrm{V}$
- Quên đưa nguồn DC về mass khi phân tích tín hiệu nhỏ
- Áp dụng `V+ = V-` cho op-amp trong mạch không có hồi tiếp âm
- Nhầm thông thấp với thông cao do chọn sai điểm lấy $V_{out}$

# 13. Phụ lục mô hình hóa trực quan

## 13.1. Danh sách hình đã sinh bằng Python

- `figures/01_signal_chain.png`: sơ đồ khối hệ xử lý tín hiệu
- `figures/02_diode_vi_curve.png`: đặc tuyến dòng áp diode
- `figures/03_rectifier_waveforms.png`: dạng sóng chỉnh lưu bán kỳ và toàn kỳ
- `figures/04_bjt_load_line.png`: đường tải DC và điểm Q
- `figures/05_bjt_regions.png`: các vùng hoạt động của BJT
- `figures/06_jfet_transfer.png`: đặc tuyến truyền đạt của JFET
- `figures/13_bjt_input_characteristic.png`: đặc tuyến vào của BJT
- `figures/14_bjt_output_characteristic.png`: họ đặc tuyến ra của BJT
- `figures/15_jfet_output_characteristic.png`: họ đặc tuyến ra của JFET
- `figures/16_mosfet_characteristics.png`: đặc tuyến truyền đạt và đặc tuyến ra của E-MOSFET
- `figures/17_opamp_transfer_characteristic.png`: đặc tuyến truyền đạt vòng hở của Op-Amp
- `figures/07_opamp_inverting_model.png`: sơ đồ mô hình của mạch đảo op-amp
- `figures/08_opamp_comparator_waveform.png`: dạng sóng vào ra của comparator
- `figures/09_rc_filter_bode.png`: Bode thông thấp và thông cao
- `figures/10_bandpass_response.png`: đáp ứng thông dải
- `figures/11_wien_oscillator_waveform.png`: khởi động dao động cầu Wien
- `figures/12_active_filter_block.png`: mô hình chức năng của lọc tích cực

## 13.2. Tái tạo lại toàn bộ hình

Lệnh chạy:

`python3 scripts/generate_electronic_figures.py`

Toàn bộ hình sẽ được sinh lại trong thư mục `figures/`.

# 14. Kết luận ngắn gọn theo từng chương

- Chương diode: nắm bản chất P-N, đặc tuyến, mô hình và chỉnh lưu
- Chương BJT: nắm vùng hoạt động, phân cực, điểm Q và ba cấu hình khuếch đại
- Chương FET: nắm Shockley, bias và mạch CS
- Chương op-amp: nắm hai quy tắc vàng, mạch đảo/không đảo, cộng trừ tích phân vi phân
- Chương dao động: nắm điều kiện Barkhausen và cầu Wien
- Chương lọc: nắm $f_c$, đồ thị Bode, phân biệt các loại lọc và lọc tích cực

# 15. Nguồn tổng hợp

- Các slide trong `Slide/`
- Các slide trong `Slide_new/`
- File liên kết tham khảo: `Slide/ElectronicDevicesLink.txt`

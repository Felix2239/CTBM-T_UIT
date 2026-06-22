---
title: "Tổng Hợp Công Thức Theo Từng Chương - Thiết bị và Mạch điện tử"
author: "Biên soạn từ Slide và Slide_new"
lang: "vi"
geometry: margin=2cm
fontsize: 11pt
---

# Mục tiêu tài liệu

Tài liệu này chỉ tập trung vào:

- Công thức trọng tâm theo từng chương
- Giải thích chi tiết các thành phần trong công thức
- Cách tính từng bước khi làm bài tập

# Chương 1. Kiến thức nền tảng

## 1.1. Điện tích, dòng điện, điện áp, công suất

### Công thức 1

**Biểu thức:** $Q = I.t$

- `Q`: điện tích $(C)$
- `I`: dòng điện $(A)$
- `t`: thời gian $(s)$

Cách tính:

1. Đổi đơn vị về SI (A, s).
2. Nhân trực tiếp `I` với `t`.
3. Kết quả ra Coulomb.

### Công thức 2

**Biểu thức:** $I = ΔQ/Δt$

- `ΔQ`: lượng điện tích thay đổi $(C)$
- `Δt`: khoảng thời gian thay đổi $(s)$

Cách tính:

1. Lấy điện tích cuối trừ điện tích đầu.
2. Chia cho thời gian tương ứng.

### Công thức 3

**Biểu thức:** $U = I.R$

- `U`: điện áp $(V)$
- `I`: dòng điện $(A)$
- `R`: điện trở $(Ω)$

Cách tính:

1. Biết 2 đại lượng thì suy ra đại lượng còn lại.
2. Dùng các biến đổi: $I = U/R$, $R = U/I$.

### Công thức 4

**Biểu thức:** $P = U I$

- `P`: công suất $(W)$
- `U`: điện áp $(V)$
- `I`: dòng điện $(A)$

Cách tính:

1. Tính điện áp và dòng qua phần tử.
2. Nhân `U` với `I`.
3. Nếu cần công suất tiêu tán điện trở: $P = I^2R = U^2/R$.

## 1.2. Tụ điện và cuộn cảm

### Công thức 5

**Biểu thức:** $i_C = C.dv/dt$

- $i_C$: dòng qua tụ $(A)$
- `C`: điện dung $(F)$
- $dv/dt$: tốc độ biến thiên điện áp $(V/s)$

Cách tính:

1. Xác định độ dốc điện áp trên tụ theo thời gian.
2. Nhân với `C` để ra dòng.

### Công thức 6

**Biểu thức:** $X_C = 1/(2\pi f C)$

- $X_C$: dung kháng $(Ω)$
- `f`: tần số $(Hz)$
- `C`: điện dung $(F)$

Cách tính:

1. Tính mẫu số `2\pifC`.
2. Lấy nghịch đảo.

### Công thức 7

**Biểu thức:** $v_L = L.di/dt$

- $v_L$: điện áp cuộn cảm $(V)$
- `L`: độ tự cảm $(H)$
- $di/dt$: tốc độ biến thiên dòng $(A/s)$

### Công thức 8

**Biểu thức:** $X_L = 2\pi f L$

- $X_L$: cảm kháng $(Ω)$
- `f`: tần số $(Hz)$
- `L`: độ tự cảm $(H)$

Cách tính: thay trực tiếp `f`, `L` rồi nhân.

# Chương 2. Diode

## 2.1. Mô hình thực diode

### Công thức 9

**Biểu thức:** $V_D = V_\gamma + I_D.r_d$

- $V_D$: điện áp hai đầu diode
- $V_\gamma$: điện áp ngưỡng (Si khoảng `0.7V`, Ge khoảng `0.3V`)
- $I_D$: dòng diode
- $r_d$: điện trở vi sai

Cách tính:

1. Chọn đúng loại diode để lấy $V_\gamma$.
2. Tính dòng $I_D$ trong mạch.
3. Thay vào để suy ra $V_D$.

### Công thức 10

**Biểu thức:** $I \approx (V_S - 0.7)/R$ (diode Si thuận)

- $V_S$: nguồn cấp
- `0.7`: sụt áp thuận xấp xỉ diode Si
- `R`: điện trở hạn dòng

Cách tính:

1. Kiểm tra diode đang phân cực thuận.
2. Lấy nguồn trừ sụt áp diode.
3. Chia cho điện trở nối tiếp.

## 2.2. Ổn áp Zener

### Công thức 11

**Biểu thức:** $I_R = (V_S - V_Z)/R$
### Công thức 12

**Biểu thức:** $I_L = V_Z/R_L$
### Công thức 13

**Biểu thức:** $I_Z = I_R - I_L$

- $V_Z$: điện áp Zener
- $I_Z$: dòng qua Zener
- Điều kiện đúng vùng ổn áp: $I_ZK \le  I_Z \le  I_ZM$

Cách tính:

1. Tính $I_R$ qua điện trở hạn dòng.
2. Tính $I_L$ của tải.
3. Lấy hiệu để ra $I_Z$.
4. So sánh với dải dòng cho phép của Zener.

# Chương 3. Transistor BJT

## 3.1. Quan hệ dòng và hệ số khuếch đại

### Công thức 14

**Biểu thức:** $I_E = I_B + I_C$
### Công thức 15

**Biểu thức:** $\beta = I_C/I_B$
### Công thức 16

**Biểu thức:** $\alpha = I_C/I_E$
### Công thức 17

**Biểu thức:** $I_C = \beta I_B$

Cách tính:

1. Từ mạch phân cực suy ra $I_B$.
2. Nhân $\beta$ để có $I_C$.
3. Tính $I_E = I_B + I_C$.
4. Kiểm tra vùng làm việc qua $V_{CE}$.

## 3.2. Điểm làm việc Q và đường tải

### Công thức 18

**Biểu thức:** $V_{CC} = I_C R_C + V_{CE} + I_E R_E$

- Dùng để tìm $V_{CE}$ hoặc $I_C$ ở chế độ DC.

Cách tính:

1. Tính $I_C$, $I_E$ từ phân cực.
2. Thay vào phương trình vòng ra.
3. Suy ra $V_{CE}$ và xác nhận active/saturation/cutoff.

## 3.3. Phân cực cầu chia áp

### Công thức 19

**Biểu thức:** $V_B \approx V_{CC} R_2/(R_1+R_2)$
### Công thức 20

**Biểu thức:** $V_E = V_B - 0.7$
### Công thức 21

**Biểu thức:** $I_E = V_E/R_E$, $I_C \approx I_E$

Cách tính:

1. Tính $V_B$ từ cầu chia áp.
2. Trừ `0.7V` để có $V_E$.
3. Chia cho $R_E$ để ra $I_E$.
4. Lấy gần đúng $I_C \approx I_E$.

## 3.4. Mô hình tín hiệu nhỏ

### Công thức 22

**Biểu thức:** $r_e' \approx 25mV/I_E$
### Công thức 23

**Biểu thức:** $r_\pi = \beta.r_e'$
### Công thức 24

**Biểu thức:** $g_m = I_C/V_T$ với $V_T \approx 25mV$

### Công thức 25 (CE)

**Biểu thức:** $A_v \approx -(R_C \parallel R_L)/r_e'$

Cách tính:

1. Từ điểm Q lấy $I_E$, $I_C$.
2. Tính $r_e'$, $g_m$.
3. Quy đổi song song tải rồi tính độ lợi áp.

# Chương 4. FET (JFET, MOSFET)

## 4.1. JFET

### Công thức 26 (Shockley)

**Biểu thức:** $I_D = I_{DSS}(1 - V_{GS}/V_P)^2$

- $I_{DSS}$: dòng cực máng khi $V_{GS} = 0$
- $V_P$ (hay $V_{GS}(off)$): điện áp khóa kênh
- $V_{GS}$: điện áp cổng-nguồn

Cách tính:

1. Viết biểu thức $V_{GS}$ theo mạch phân cực.
2. Thay vào Shockley.
3. Giải ra $I_D$ (thường là phương trình bậc hai).

### Công thức 27 (tự phân cực)

**Biểu thức:** $V_{GS} = -I_D R_S$

- Kết hợp trực tiếp với Shockley để tìm điểm Q.

## 4.2. MOSFET tăng cường kênh N

### Công thức 28 (miền bão hòa)

**Biểu thức:** $I_D = K(V_{GS} - V_{TH})^2$

- `K`: hằng số công nghệ/linh kiện
- $V_{TH}$: điện áp ngưỡng mở kênh

Cách tính:

1. Kiểm tra điều kiện $V_{GS} > V_{TH}$.
2. Thay số để tính $I_D$.

### Công thức 28a (điều kiện mở/tắt)

**Biểu thức:** 

- Nếu $V_{GS} \le V_{TH}$ thì $I_D \approx 0$
- Nếu $V_{GS} > V_{TH}$ thì MOSFET bắt đầu dẫn

- $V_{TH}$: điện áp ngưỡng
- $V_{GS}$: điện áp cổng-nguồn

Cách tính:

1. Tính $V_{GS}$ từ mạch phân cực.
2. So sánh với $V_{TH}$.
3. Nếu chưa vượt ngưỡng thì coi như ngắt.

### Công thức 28b (điều kiện miền bão hòa)

**Biểu thức:** $V_{DS} \ge V_{GS} - V_{TH}$

- Điều kiện này phải đúng thì công thức $I_D = K(V_{GS} - V_{TH})^2$ mới dùng trực tiếp được.

Cách tính:

1. Tính $V_{GS}$ và $V_{DS}$.
2. Tính vế phải $V_{GS} - V_{TH}$.
3. So sánh để xác nhận MOSFET đang ở miền bão hòa.

### Công thức 28c (quan hệ điện áp DC trong mạch phân cực)

**Biểu thức:** 

- $V_{GS} = V_G - V_S$
- $V_{DS} = V_D - V_S$
- $V_D = V_{DD} - I_D R_D$
- $V_S = I_D R_S$

- Dùng để nối bài toán mạch điện trở phân cực với công thức dòng của MOSFET.

Cách tính:

1. Tính $V_G$ từ cầu chia áp hoặc từ nguồn bias đã cho.
2. Tính $V_S = I_D R_S$ nếu có điện trở source.
3. Suy ra $V_{GS}$, rồi thế vào công thức dòng.
4. Sau khi có $I_D$, tính $V_D$ và $V_{DS}$ để kiểm tra miền làm việc.

### Công thức 28d (độ dẫn truyền nhỏ tín hiệu của MOSFET)

**Biểu thức:** 

- $g_m = \Delta I_D / \Delta V_{GS}$
- Với $I_D = K(V_{GS} - V_{TH})^2$ thì $g_m = 2K(V_{GS} - V_{TH})$
- Tương đương: $g_m = 2I_D/(V_{GS} - V_{TH})$

- $g_m$: hỗ dẫn nhỏ tín hiệu, đơn vị Siemens

Cách tính:

1. Tìm điểm Q để biết $I_D$ và $V_{GS}$.
2. Tính độ vượt ngưỡng $(V_{GS} - V_{TH})$.
3. Dùng một trong hai biểu thức trên để suy ra $g_m$.

## 4.3. Khuếch đại CS

### Công thức 29

**Biểu thức:** $A_v \approx -g_m(R_D \parallel R_L \parallel r_d)$

Cách tính:

1. Tính $g_m$ tại điểm Q.
2. Tính điện trở tương đương ở cực Drain.
3. Nhân với $-g_m$.

# Chương 5. Op-Amp cơ bản

## 5.1. Quy tắc vàng (op-amp lý tưởng, có hồi tiếp âm)

- $I_+ = I_- = 0$
- $V_+ \approx V_-$

## 5.2. Độ lợi vòng kín

### Công thức 30

**Biểu thức:** $A_{CL} = A_{OL}/(1 + A_{OL}\beta)$

- $A_{OL}$: độ lợi vòng hở
- $\beta$: hệ số hồi tiếp

Cách tính: thay trực tiếp $A_{OL}$, $\beta$; khi $A_{OL}\beta >> 1$, độ lợi chủ yếu do mạng hồi tiếp quyết định.

## 5.3. Mạch đảo và không đảo

### Công thức 31

**Biểu thức:** $A_v = -R_f/R_{in}$ (mạch đảo)
### Công thức 32

**Biểu thức:** $A_v = 1 + R_f/R_1$ (mạch không đảo)

Cách tính:

1. Nhận dạng cấu trúc mạch.
2. Áp dụng đúng công thức theo cấu hình.
3. Tính $V_{out} = A_v V_{in}$.

## 5.4. CMRR

### Công thức 33

**Biểu thức:** $CMRR = A_DM/A_CM$
### Công thức 34

**Biểu thức:** $CMRR_dB = 20\log_{10}(CMRR)$

# Chương 6. Ứng dụng Op-Amp

## 6.1. Mạch cộng đảo

### Công thức 35

**Biểu thức:** $V_{out} = -R_f(V_1/R_1 + V_2/R_2 + ... + V_n/R_n)$

Cách tính:

1. Tính từng thành phần $V_k/R_k$.
2. Cộng lại.
3. Nhân với $-R_f$.

## 6.2. Mạch trừ

### Công thức 36

**Biểu thức:** $V_{out} = (R_2/R_1)(V_2 - V_1)$

- Áp dụng khi tỉ số điện trở hai nhánh thỏa điều kiện mạch khuếch đại vi sai chuẩn.

## 6.3. Mạch tích phân

### Công thức 37

**Biểu thức:** $V_{out} = -(1/RC)\int V_{in}\,dt$

Cách tính:

1. Chia tín hiệu vào thành các đoạn thời gian.
2. Tính diện tích dưới đường $V_{in}(t)$ cho từng đoạn.
3. Nhân hệ số $-1/(RC)$.

## 6.4. Mạch vi phân

### Công thức 38

**Biểu thức:** $V_{out} = -RC\,\dfrac{dV_{in}}{dt}$

Cách tính:

1. Tính độ dốc của $V_{in}(t)$ theo thời gian.
2. Nhân với `-RC`.

# Chương 7. Mạch dao động

## 7.1. Điều kiện Barkhausen

### Công thức 39

**Biểu thức:** $|A\beta| = 1$ (dao động duy trì)

- Điều kiện khởi động thực tế: $|A\beta| > 1$
- Điều kiện pha: tổng lệch pha vòng kín bằng `0°` hoặc `360°`

## 7.2. Dao động cầu Wien

### Công thức 40

**Biểu thức:** $f_0 = 1/(2\pi R C)$

Cách tính:

1. Dùng giá trị cặp `R, C` của mạng cầu Wien.
2. Thay vào công thức để ra tần số dao động trung tâm.

# Chương 8. Mạch lọc thụ động và tích cực

## 8.1. Tần số cắt RC bậc một

### Công thức 41

**Biểu thức:** $f_c = 1/(2\pi R C)$

- Dùng cho lọc thông thấp/thông cao bậc một.

Cách tính:

1. Đổi `R` về Ohm, `C` về Farad.
2. Tính mẫu số `2\piRC`.
3. Lấy nghịch đảo.

## 8.2. Độ lợi theo decibel

### Công thức 42

**Biểu thức:** $A_v(dB) = 20\log_{10}(V_{out}/V_{in})$

Cách tính:

1. Tính tỉ số biên độ $V_{out}/V_{in}$.
2. Lấy log cơ số 10.
3. Nhân 20.

## 8.3. Lọc thông dải

### Công thức 43

**Biểu thức:** $f_0 = \sqrt{f_L f_H}$
### Công thức 44

**Biểu thức:** $BW = f_H - f_L$

- $f_L$: tần số cắt dưới
- $f_H$: tần số cắt trên
- `BW`: băng thông

Cách tính:

1. Xác định $f_L$, $f_H$ trên đồ thị/đề bài.
2. Tính $f_0$ bằng trung bình nhân.
3. Lấy hiệu để có `BW`.

# Quy trình làm bài nhanh (áp dụng cho mọi chương)

1. Xác định chế độ làm việc DC hay AC.
2. Chọn mô hình đúng của linh kiện.
3. Viết công thức tổng quát trước, chưa thay số.
4. Đổi đơn vị về SI.
5. Thay số, bấm máy, ghi rõ đơn vị.
6. Kiểm tra tính hợp lý vật lý của kết quả (dấu, cỡ lớn/nhỏ, vùng hoạt động).

# Danh sách công thức trọng tâm (rút gọn)

- $Q = I.t$
- $I = ΔQ/Δt$
- $U = I.R$
- $P = U I$
- $i_C = C.dv/dt$
- $X_C = 1/(2\pi f C)$
- $X_L = 2\pi f L$
- $I \approx (V_S - 0.7)/R$
- $V_D = V_\gamma + I_D.r_d$
- $I_E = I_B + I_C$
- $I_C = \beta I_B$
- $r_e' \approx 25mV/I_E$
- $I_D = I_{DSS}(1 - V_{GS}/V_P)^2$
- $I_D = K(V_{GS} - V_{TH})^2$
- $A_v(CE) \approx -(R_C \parallel R_L)/r_e'$
- $A_v(CS) \approx -g_m(R_D \parallel R_L \parallel r_d)$
- $A_{CL} = A_{OL}/(1 + A_{OL}\beta)$
- $A_v = -R_f/R_{in}$
- $A_v = 1 + R_f/R_1$
- $V_{out} = -(1/RC)\int V_{in}\,dt$
- $V_{out} = -RC\,\dfrac{dV_{in}}{dt}$
- $|A\beta| = 1$
- $f_0 = 1/(2\pi R C)$
- $A_v(dB) = 20\log_{10}(V_{out}/V_{in})$
- $f_0 = \sqrt{f_L f_H}$
- $BW = f_H - f_L$

# Ví dụ cụ thể kèm ảnh

## Ví dụ 1 (Chương 1): Định luật Ohm và công suất

Đề bài: Cho $R = 220Ω$, $U = 11\,\mathrm{V}$. Tính `I` và `P`.

Tính:

- $I = U/R = 11/220 = 0.05A = 50\,\mathrm{mA}$
- $P = U I = 11 x 0.05 = 0.55\,\mathrm{W}$

Kết quả: Dòng qua điện trở là `50mA`, công suất tiêu tán `0.55W`.

## Ví dụ 2 (Chương 2): Diode chỉnh lưu nửa chu kỳ

Đề bài: Nguồn sin có đỉnh $V_p = 10\,\mathrm{V}$, diode Si và tải $R = 1kΩ$. Tính dòng đỉnh qua tải khi diode dẫn.

Tính:

- $I_p \approx (V_p - 0.7)/R = (10 - 0.7)/1000 = 9.3\,\mathrm{mA}$

Kết quả: Dòng đỉnh xấp xỉ `9.3mA`.

![Dạng sóng chỉnh lưu](figures/03_rectifier_waveforms.png){ width=86% }

## Ví dụ 3 (Chương 3): BJT phân cực cầu chia áp

Đề bài: $V_{CC} = 12\,\mathrm{V}$, $R_1 = 47kΩ$, $R_2 = 10kΩ$, $R_E = 1kΩ$, $R_C = 2.2kΩ$. Tính gần đúng $V_E$, $I_C$, $V_{CE}$.

Tính:

- $V_B \approx 12 x 10/(47+10) = 2.105\,\mathrm{V}$
- $V_E = V_B - 0.7 = 1.405\,\mathrm{V}$
- $I_E = V_E/R_E = 1.405\,\mathrm{mA}$, suy ra $I_C \approx 1.405mA$
- $V_C = V_{CC} - I_C R_C = 12 - 1.405mA x 2.2kΩ = 8.909\,\mathrm{V}$
- $V_{CE} = V_C - V_E = 7.504\,\mathrm{V}$

Kết quả: Q-point ở vùng active, phù hợp khuếch đại tuyến tính.

![Đường tải và điểm Q BJT](figures/04_bjt_load_line.png){ width=80% }

## Ví dụ 4 (Chương 4): JFET tự phân cực

Đề bài: $I_{DSS} = 10\,\mathrm{mA}$, $V_P = -4V$, $R_S = 330Ω$. Tính gần đúng $I_D$.

Tính nhanh lặp:

- $V_{GS} = -I_D R_S$
- Thử $I_D = 4\,\mathrm{mA}$ thì $V_{GS} = -1.32V$
- Shockley: $I_D = 10(1 - (-1.32)/(-4))^2 = 10(0.67)^2 \approx 4.49mA$

Kết quả gần đúng hội tụ: $I_D \approx 4.4mA$.

![Đặc tuyến truyền đạt JFET](figures/06_jfet_transfer.png){ width=76% }

## Ví dụ 5 (Chương 5): Op-amp mạch đảo

Đề bài: $R_{in} = 10kΩ$, $R_f = 47kΩ$, $V_{in} = 0.2\,\mathrm{V}$. Tính $V_{out}$.

Tính:

- $A_v = -R_f/R_{in} = -47/10 = -4.7$
- $V_{out} = A_v V_{in} = -4.7 x 0.2 = -0.94V$

Kết quả: $V_{out} = -0.94V$, tín hiệu đảo pha 180 độ.

![Mạch op-amp đảo](figures/07_opamp_inverting_model.png){ width=88% }

## Ví dụ 6 (Chương 6): Op-amp mạch cộng đảo

Đề bài: $R_f = 20kΩ$, $R_1 = 10kΩ$, $R_2 = 20kΩ$, $V_1 = 0.5\,\mathrm{V}$, $V_2 = 1.2\,\mathrm{V}$.

Tính:

- $V_{out} = -R_f(V_1/R_1 + V_2/R_2)$
- $V_{out} = -20k(0.5/10k + 1.2/20k) = -(1 + 1.2) = -2.2V$

Kết quả: $V_{out} = -2.2V$.

## Ví dụ 7 (Chương 7): Dao động cầu Wien

Đề bài: $R = 10kΩ$, $C = 10nF$. Tính tần số dao động.

Tính:

- $f_0 = 1/(2\pi R C) = 1/(2\pi x 10^4 x 10^-8) \approx 1591.5Hz$

Kết quả: $f_0 \approx 1.59kHz$.

![Khởi động dao động cầu Wien](figures/11_wien_oscillator_waveform.png){ width=84% }

## Ví dụ 8 (Chương 8): Lọc RC thông thấp

Đề bài: $R = 3.3kΩ$, $C = 10nF$. Tính $f_c$.

Tính:

- $f_c = 1/(2\pi R C) = 1/(2\pi x 3300 x 10^-8) \approx 4822Hz$

Kết quả: $f_c \approx 4.82kHz$.

![Đáp ứng Bode lọc RC](figures/09_rc_filter_bode.png){ width=86% }

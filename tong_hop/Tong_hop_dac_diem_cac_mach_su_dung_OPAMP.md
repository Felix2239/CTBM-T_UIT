---
title: "Tổng Hợp Đặc Điểm Các Mạch Sử Dụng Op-Amp Khi Giải Bài"
author: "Codex tổng hợp theo hướng tra nhanh"
lang: "vi"
mainfont: DejaVu Sans
monofont: Noto Sans Mono
geometry: margin=1.7cm
fontsize: 10.5pt
header-includes:
  - \usepackage{amsmath}
  - \usepackage{amssymb}
---

# Tổng hợp đặc điểm các mạch sử dụng Op-Amp khi giải bài

Tài liệu này dùng để **tra nhanh khi làm bài op-amp**. Trọng tâm là:

- mạch đang làm việc ở vùng nào
- được dùng tính chất nào của op-amp
- đầu ra so với đầu vào cùng pha hay ngược pha
- công thức cần dùng

## 1. Op-amp lý tưởng: các tính chất gốc

### 1.1. Các giả thiết cơ bản

- Độ lợi vòng hở rất lớn:

$$
A_{OL}\to\infty
$$

- Trở kháng vào rất lớn:

$$
i_+=i_-=0
$$

- Trở kháng ra rất nhỏ.

### 1.2. Hai quy tắc vàng khi có hồi tiếp âm

Nếu mạch có **hồi tiếp âm** và op-amp đang làm việc tuyến tính:

$$
v_+\approx v_-
$$

và:

$$
i_+=i_-=0
$$

Đây là hai ý quan trọng nhất khi giải phần lớn bài op-amp.

### 1.3. Giới hạn đầu ra

Đầu ra không thể tăng vô hạn mà bị chặn bởi nguồn nuôi:

$$
v_o\approx +V_{sat}\quad \text{hoặc}\quad v_o\approx -V_{sat}
$$

Nếu kết quả tính tuyến tính vượt quá rail nguồn, phải kết luận mạch đã vào bão hòa.

## 2. Các vùng hoạt động của op-amp

### 2.1. Vùng tuyến tính

- Có hồi tiếp âm.
- Đầu ra chưa chạm rail nguồn.
- Dùng được:

$$
v_+\approx v_-
$$

### 2.2. Vùng bão hòa dương

- Đầu ra bị kéo lên gần rail dương:

$$
v_o\approx +V_{sat}
$$

- Hay gặp ở comparator khi:

$$
v_+>v_-
$$

### 2.3. Vùng bão hòa âm

- Đầu ra bị kéo xuống gần rail âm:

$$
v_o\approx -V_{sat}
$$

- Hay gặp ở comparator khi:

$$
v_+<v_-
$$

### 2.4. Khi nào không được dùng mass ảo

Không được dùng:

$$
v_+\approx v_-
$$

nếu:

- mạch không có hồi tiếp âm
- mạch là comparator hoặc Schmitt trigger
- đầu ra đã bão hòa

## 3. Cách nhận dạng mạch op-amp khi giải bài

| Dạng mạch | Dấu hiệu nhận biết | Vùng hoạt động thường dùng | Đầu ra so với đầu vào |
|---|---|---|---|
| Khuếch đại đảo | tín hiệu vào qua điện trở vào chân `-`, chân `+` nối chuẩn | tuyến tính | đảo pha 180 độ |
| Khuếch đại không đảo | tín hiệu vào chân `+`, hồi tiếp về chân `-` | tuyến tính | cùng pha |
| Mạch theo áp | đầu ra nối trực tiếp về chân `-` | tuyến tính | cùng pha, gain 1 |
| Mạch cộng đảo | nhiều ngõ vào qua điện trở cùng vào chân `-` | tuyến tính | đảo dấu tổng có trọng số |
| Mạch trừ / vi sai | cả hai chân đều nhận tín hiệu qua mạng điện trở | tuyến tính | khuếch đại hiệu hai đầu vào |
| Comparator | không có hồi tiếp âm tuyến tính | bão hòa | ra mức cao hoặc thấp |
| Schmitt trigger | có hồi tiếp dương | bão hòa có ngưỡng | đầu ra nhảy mức theo ngưỡng |
| Tích phân | tụ ở nhánh hồi tiếp | tuyến tính | đầu ra tỉ lệ tích phân và đảo dấu |
| Vi phân | tụ ở nhánh vào | tuyến tính | đầu ra tỉ lệ đạo hàm và đảo dấu |
| Lọc tích cực | có mạng `R`, `C` và op-amp | tuyến tính theo tần số | phụ thuộc loại lọc |

## 4. Mạch khuếch đại đảo

### 4.1. Tính chất

- Chân `+` thường nối mass.
- Chân `-` là **mass ảo**:

$$
v_-\approx 0
$$

- Dòng vào op-amp bằng 0 nên dòng qua điện trở vào bằng dòng qua điện trở hồi tiếp.

### 4.2. Đầu ra so với đầu vào

- Ngược pha 180 độ.
- Nếu $v_{in}$ dương thì $v_o$ có xu hướng âm.

### 4.3. Công thức

$$
A_v=\frac{v_o}{v_{in}}=-\frac{R_f}{R_i}
$$

$$
v_o=-\frac{R_f}{R_i}v_{in}
$$

### 4.4. Khi nào mạch còn tuyến tính

Sau khi tính:

$$
v_o=-\frac{R_f}{R_i}v_{in}
$$

phải kiểm tra:

$$
-V_{sat}<v_o<+V_{sat}
$$

Nếu không thỏa, đầu ra bị bão hòa.

## 5. Mạch khuếch đại không đảo

### 5.1. Tính chất

- Tín hiệu vào đi vào chân `+`.
- Hồi tiếp âm qua bộ chia điện áp về chân `-`.

### 5.2. Đầu ra so với đầu vào

- Cùng pha.
- Đầu ra lớn hơn hoặc bằng đầu vào theo hệ số khuếch đại.

### 5.3. Công thức

$$
A_v=\frac{v_o}{v_{in}}=1+\frac{R_f}{R_i}
$$

$$
v_o=\left(1+\frac{R_f}{R_i}\right)v_{in}
$$

### 5.4. Điều kiện tuyến tính

Phải có:

$$
-V_{sat}<v_o<+V_{sat}
$$

## 6. Mạch theo áp

### 6.1. Tính chất

- Là trường hợp riêng của mạch không đảo.
- Đầu ra nối trực tiếp về chân `-`.
- Dùng để đệm, cách ly tầng trước với tải.

### 6.2. Đầu ra so với đầu vào

- Cùng pha.
- Biên độ bằng nhau.

### 6.3. Công thức

$$
v_o=v_{in}
$$

$$
A_v=1
$$

## 7. Mạch cộng đảo

### 7.1. Tính chất

- Nhiều nguồn vào đi qua các điện trở riêng rồi cùng gặp tại chân `-`.
- Chân `-` là mass ảo nếu mạch đang tuyến tính.

### 7.2. Đầu ra so với đầu vào

- Là tổng có trọng số của các ngõ vào.
- Có dấu âm nên bị đảo.

### 7.3. Công thức tổng quát

$$
v_o=-R_f\left(\frac{v_1}{R_1}+\frac{v_2}{R_2}+\cdots+\frac{v_n}{R_n}\right)
$$

Nếu:

$$
R_1=R_2=\cdots=R_n=R
$$

thì:

$$
v_o=-\frac{R_f}{R}(v_1+v_2+\cdots+v_n)
$$

## 8. Mạch trừ và khuếch đại vi sai

### 8.1. Tính chất

- Dùng để khuếch đại hiệu điện áp giữa hai ngõ vào.
- Hay gặp trong bài yêu cầu:
  - loại bỏ thành phần chung
  - đo chênh lệch giữa hai tín hiệu

### 8.2. Đầu ra so với đầu vào

- Đầu ra tỉ lệ với:

$$
v_2-v_1
$$

theo cách gán cực của mạch.

### 8.3. Công thức cân bằng điện trở

Nếu:

$$
\frac{R_2}{R_1}=\frac{R_4}{R_3}
$$

thì:

$$
v_o=\frac{R_2}{R_1}(v_2-v_1)
$$

Đây là công thức vi sai cơ bản hay dùng nhất.

## 9. Comparator

### 9.1. Vùng hoạt động

- Làm việc ở **vùng bão hòa**, không phải vùng tuyến tính.
- Không dùng mass ảo.

### 9.2. Tính chất

- Chỉ cần so sánh điện áp hai đầu vào.
- Do $A_{OL}$ rất lớn, chỉ cần hiệu rất nhỏ cũng đẩy đầu ra lên một rail.

### 9.3. Đầu ra so với đầu vào

$$
v_o=
\begin{cases}
+V_{sat}, & v_+>v_- \\
-V_{sat}, & v_+<v_-
\end{cases}
$$

Nếu:

$$
v_+=v_-
$$

thì lý tưởng ở ngưỡng chuyển trạng thái.

## 10. Schmitt trigger

### 10.1. Vùng hoạt động

- Là comparator có **hồi tiếp dương**.
- Đầu ra nhảy giữa hai mức bão hòa.

### 10.2. Tính chất

- Có hai ngưỡng khác nhau:
  - ngưỡng lên
  - ngưỡng xuống
- Dùng để chống nhiễu và tạo hysteresis.

### 10.3. Đầu ra so với đầu vào

- Đầu ra không đổi liên tục theo đầu vào.
- Nó chỉ nhảy mức khi đầu vào vượt ngưỡng.

### 10.4. Công thức ngưỡng điển hình

Với mạch hồi tiếp dương chia áp từ đầu ra:

$$
V_{UT}=+\beta V_{sat}
$$

$$
V_{LT}=-\beta V_{sat}
$$

với:

$$
\beta=\frac{R_1}{R_1+R_2}
$$

Tùy sơ đồ, biểu thức $\beta$ có thể đổi theo cách đặt điện trở, nhưng bản chất vẫn là ngưỡng lấy từ một phần của đầu ra bão hòa.

## 11. Mạch tích phân

### 11.1. Tính chất

- Điện trở ở ngõ vào.
- Tụ điện ở nhánh hồi tiếp.
- Là mạch đảo.

### 11.2. Đầu ra so với đầu vào

- Đầu ra là tích phân của đầu vào và mang dấu âm.
- Nếu đầu vào là xung vuông thì đầu ra thường là tam giác.

### 11.3. Công thức

$$
v_o(t)=-\frac{1}{RC}\int v_{in}(t)\,dt + v_o(t_0)
$$

Nếu bỏ qua điều kiện đầu:

$$
v_o(t)=-\frac{1}{RC}\int v_{in}(t)\,dt
$$

## 12. Mạch vi phân

### 12.1. Tính chất

- Tụ điện ở ngõ vào.
- Điện trở ở nhánh hồi tiếp.
- Là mạch đảo.

### 12.2. Đầu ra so với đầu vào

- Đầu ra tỉ lệ với đạo hàm của đầu vào và mang dấu âm.
- Nếu đầu vào biến thiên nhanh thì đầu ra lớn.

### 12.3. Công thức

$$
v_o(t)=-RC\frac{dv_{in}(t)}{dt}
$$

## 13. Lọc tích cực dùng op-amp

### 13.1. Tính chất chung

- Op-amp được dùng để vừa khuếch đại vừa tạo đặc tính lọc.
- Mạch vẫn làm việc tuyến tính nếu chưa bão hòa.

### 13.2. Thông thấp bậc một

Đầu ra cho thành phần tần số thấp đi qua tốt hơn tần số cao.

Tần số cắt:

$$
f_c=\frac{1}{2\pi RC}
$$

### 13.3. Thông cao bậc một

Đầu ra cho thành phần tần số cao đi qua tốt hơn tần số thấp.

Tần số cắt:

$$
f_c=\frac{1}{2\pi RC}
$$

### 13.4. Sallen-Key bậc hai đối xứng

Với lọc thông thấp hoặc thông cao đối xứng:

$$
f_c=\frac{1}{2\pi RC}
$$

Nếu muốn đáp ứng Butterworth bậc hai:

$$
A_v\approx1.586
$$

Nếu tầng op-amp mắc không đảo:

$$
A_v=1+\frac{R_f}{R_i}
$$

## 14. Các công thức cực hay dùng khi giải bài

### 14.1. Khuếch đại đảo

$$
v_o=-\frac{R_f}{R_i}v_{in}
$$

### 14.2. Khuếch đại không đảo

$$
v_o=\left(1+\frac{R_f}{R_i}\right)v_{in}
$$

### 14.3. Mạch theo áp

$$
v_o=v_{in}
$$

### 14.4. Mạch cộng đảo

$$
v_o=-R_f\sum\frac{v_k}{R_k}
$$

### 14.5. Mạch vi sai

$$
v_o=\frac{R_2}{R_1}(v_2-v_1)
$$

### 14.6. Comparator

$$
v_o=
\begin{cases}
+V_{sat}, & v_+>v_- \\
-V_{sat}, & v_+<v_-
\end{cases}
$$

### 14.7. Tích phân

$$
v_o(t)=-\frac{1}{RC}\int v_{in}(t)\,dt
$$

### 14.8. Vi phân

$$
v_o(t)=-RC\frac{dv_{in}(t)}{dt}
$$

## 15. Checklist tra nhanh trước khi bấm máy

1. Mạch có hồi tiếp âm hay không.
2. Có được dùng:

$$
v_+\approx v_-
$$

không.

3. Đầu ra đang ở vùng tuyến tính hay đã chạm:

$$
\pm V_{sat}
$$

4. Mạch đảo hay không đảo.
5. Có phải mạch cộng, trừ, tích phân, vi phân, comparator hay Schmitt không.
6. Sau khi tính xong, có cần kiểm tra bão hòa đầu ra không.

## 16. Các lỗi rất hay gặp

- Dùng mass ảo cho comparator là sai.
- Quên kiểm tra đầu ra có vượt nguồn nuôi hay không.
- Nhầm mạch đảo với mạch không đảo.
- Quên dấu âm trong mạch đảo, cộng đảo, tích phân, vi phân.
- Với Schmitt trigger, chỉ dùng một ngưỡng thay vì hai ngưỡng.
- Với mạch vi sai, dùng sai tỉ lệ điện trở nên áp nhầm công thức.

## 17. Tóm tắt nhớ trong 30 giây

- Có hồi tiếp âm và chưa bão hòa thì dùng:

$$
v_+\approx v_-,\qquad i_+=i_-=0
$$

- Mạch đảo:

$$
v_o=-\frac{R_f}{R_i}v_{in}
$$

- Mạch không đảo:

$$
v_o=\left(1+\frac{R_f}{R_i}\right)v_{in}
$$

- Comparator:

$$
v_+>v_- \Rightarrow v_o\approx +V_{sat}
$$

$$
v_+<v_- \Rightarrow v_o\approx -V_{sat}
$$

- Tích phân:

$$
v_o=-\frac{1}{RC}\int v_{in}\,dt
$$

- Vi phân:

$$
v_o=-RC\frac{dv_{in}}{dt}
$$


---
title: "Bài Tập Đáp Ứng Tần Số, Bode, Pole, Roll-Off"
author: "Tổng hợp và tự biên soạn"
lang: "vi"
mainfont: DejaVu Sans
monofont: Noto Sans Mono
geometry: margin=1.7cm
fontsize: 10.5pt
header-includes:
  - \usepackage{amsmath}
  - \usepackage{amssymb}
---

# Bài tập đáp ứng tần số, Bode, pole, roll-off

Tài liệu này tập trung vào phần **đáp ứng tần số thuần**:

- viết $H(j\omega)$
- tính biên độ và pha
- đổi sang dB
- tìm pole
- đọc và ước lượng `roll-off`

Mỗi bài đều có:

- yêu cầu
- đáp số ngắn
- cơ sở công thức
- lời giải chi tiết

Khi làm dạng này, nên đi theo thứ tự:

1. Viết hàm truyền $H(s)$.
2. Thay:

$$
s=j\omega
$$

3. Tách:

$$
|H(j\omega)|,\qquad \angle H(j\omega)
$$

4. Nếu cần Bode, đổi sang:

$$
A_v(\mathrm{dB})=20\log_{10}|H(j\omega)|
$$

5. Tìm pole và suy ra `roll-off`.

## Bài 1. RC thông thấp bậc một

![Đáp ứng tần số của lọc RC bậc một](figures/09_rc_filter_bode.png){ width=88% }

**Yêu cầu**

Cho mạch RC thông thấp bậc một có đầu ra lấy trên tụ.

1. Viết hàm truyền $H(j\omega)$.
2. Tìm $|H(j\omega)|$ và $\angle H(j\omega)$.
3. Tìm tần số cắt $f_c$.
4. Cho biết pole và `roll-off`.

**Đáp số ngắn**

$$
H(j\omega)=\frac{1}{1+j\omega RC}
$$

$$
|H(j\omega)|=\frac{1}{\sqrt{1+(\omega RC)^2}}
$$

$$
\angle H(j\omega)=-\tan^{-1}(\omega RC)
$$

$$
f_c=\frac{1}{2\pi RC}
$$

Pole:

$$
s_p=-\frac{1}{RC}
$$

Roll-off sau tần số cắt:

$$
-20\,\mathrm{dB/dec}
$$

**Cơ sở và công thức**

Với mạch chia áp theo trở kháng:

$$
H(j\omega)=\frac{Z_C}{R+Z_C}
$$

với:

$$
Z_C=\frac{1}{j\omega C}
$$

**Lời giải chi tiết**

Vì đầu ra lấy trên tụ, ta dùng chia áp:

$$
H(j\omega)=\frac{Z_C}{R+Z_C}
=\frac{\frac{1}{j\omega C}}{R+\frac{1}{j\omega C}}
=\frac{1}{1+j\omega RC}
$$

Từ đó:

$$
|H(j\omega)|=\frac{1}{\sqrt{1+(\omega RC)^2}}
$$

và:

$$
\angle H(j\omega)=-\tan^{-1}(\omega RC)
$$

Tại tần số cắt:

$$
\omega_cRC=1
\Rightarrow
\omega_c=\frac{1}{RC}
\Rightarrow
f_c=\frac{1}{2\pi RC}
$$

Hàm truyền có mẫu:

$$
1+sRC
$$

nên pole nằm tại:

$$
s_p=-\frac{1}{RC}
$$

Vì chỉ có **một pole**, độ dốc sau $f_c$ là:

$$
-20\,\mathrm{dB/dec}
$$

Đây là bài mẫu cơ bản nhất của chương đáp ứng tần số.

---

## Bài 2. RC thông cao bậc một

![Đáp ứng tần số của lọc RC bậc một](figures/09_rc_filter_bode.png){ width=88% }

**Yêu cầu**

Cho mạch RC thông cao bậc một có đầu ra lấy trên điện trở.

1. Viết $H(j\omega)$.
2. Tính biên độ và pha.
3. Xác định tần số cắt và `roll-off`.

**Đáp số ngắn**

$$
H(j\omega)=\frac{j\omega RC}{1+j\omega RC}
$$

$$
|H(j\omega)|=\frac{\omega RC}{\sqrt{1+(\omega RC)^2}}
$$

$$
\angle H(j\omega)=90^\circ-\tan^{-1}(\omega RC)
$$

$$
f_c=\frac{1}{2\pi RC}
$$

Ở miền thấp tần, đường Bode tăng với độ dốc:

$$
20\,\mathrm{dB/dec}
$$

**Cơ sở và công thức**

Chia áp theo trở kháng:

$$
H(j\omega)=\frac{R}{R+Z_C}
$$

**Lời giải chi tiết**

Ta có:

$$
H(j\omega)=\frac{R}{R+\frac{1}{j\omega C}}
=\frac{j\omega RC}{1+j\omega RC}
$$

Biên độ:

$$
|H(j\omega)|=\frac{\omega RC}{\sqrt{1+(\omega RC)^2}}
$$

Pha:

$$
\angle H(j\omega)=\angle(j\omega RC)-\angle(1+j\omega RC)
$$

$$
\angle H(j\omega)=90^\circ-\tan^{-1}(\omega RC)
$$

Khi $\omega$ rất nhỏ, tử số rất nhỏ nên tín hiệu thấp tần bị chặn mạnh. Khi $\omega$ lớn, biên độ tiến tới `1`, nên mạch cho qua tốt thành phần cao tần.

Tần số cắt vẫn là:

$$
f_c=\frac{1}{2\pi RC}
$$

Về Bode:

- dưới $f_c$, đường biên độ tăng với `+20 dB/dec`
- trên $f_c$, nó tiến dần về miền gần `0 dB`

---

## Bài 3. Đổi biên độ sang dB và xác định điểm -3 dB

**Yêu cầu**

Với mạch thông thấp bậc một:

$$
|H(j\omega)|=\frac{1}{\sqrt{1+(\omega RC)^2}}
$$

1. Viết biểu thức độ lợi theo dB.
2. Chứng minh tại tần số cắt thì độ lợi bằng `-3 dB`.

**Đáp số ngắn**

$$
A_v(\mathrm{dB})=20\log_{10}\left(\frac{1}{\sqrt{1+(\omega RC)^2}}\right)
$$

Tại $\omega=\omega_c=\frac{1}{RC}$:

$$
|H(j\omega_c)|=\frac{1}{\sqrt{2}}
$$

$$
A_v(\mathrm{dB})=20\log_{10}\left(\frac{1}{\sqrt{2}}\right)\approx -3.01\,\mathrm{dB}
$$

**Cơ sở và công thức**

Đổi sang dB:

$$
A_v(\mathrm{dB})=20\log_{10}|H(j\omega)|
$$

**Lời giải chi tiết**

Độ lợi theo biên độ là:

$$
|H(j\omega)|=\frac{1}{\sqrt{1+(\omega RC)^2}}
$$

Nên đổi sang dB:

$$
A_v(\mathrm{dB})=20\log_{10}\left(\frac{1}{\sqrt{1+(\omega RC)^2}}\right)
$$

Tại tần số cắt:

$$
\omega_cRC=1
$$

Suy ra:

$$
|H(j\omega_c)|=\frac{1}{\sqrt{1+1}}=\frac{1}{\sqrt{2}}
$$

Và:

$$
A_v(\mathrm{dB})=20\log_{10}\left(\frac{1}{\sqrt{2}}\right)\approx-3.01\,\mathrm{dB}
$$

Đây là lý do trong mọi đồ thị Bode, tần số cắt của lọc bậc một thường được đánh dấu tại mức `-3 dB`.

---

## Bài 4. Pole và ý nghĩa của pole

**Yêu cầu**

Cho hàm truyền:

$$
H(s)=\frac{10}{(1+s/100)(1+s/1000)}
$$

1. Tìm các pole.
2. Cho biết bậc của mạch.
3. Suy ra độ dốc biên độ ở tần số cao.

**Đáp số ngắn**

Các pole:

$$
s_{p1}=-100,\qquad s_{p2}=-1000
$$

Bậc mạch: `2`

Roll-off ở cao tần:

$$
-40\,\mathrm{dB/dec}
$$

**Cơ sở và công thức**

Pole là nghiệm của mẫu số:

$$
D(s)=0
$$

Mỗi pole bậc một đóng góp gần đúng:

$$
-20\,\mathrm{dB/dec}
$$

**Lời giải chi tiết**

Từ mẫu số:

$$
(1+s/100)(1+s/1000)=0
$$

ta có:

$$
1+\frac{s}{100}=0 \Rightarrow s=-100
$$

$$
1+\frac{s}{1000}=0 \Rightarrow s=-1000
$$

Vậy hệ có hai pole thực âm. Điều này cho biết:

- mạch là **bậc hai**
- năng lượng tích trữ tương đương hai phần tử phản ứng
- biên độ sẽ suy giảm mạnh hơn mạch bậc một

Vì mỗi pole thêm khoảng `-20 dB/dec`, nên khi đi xa lên miền cao tần, tổng độ dốc là:

$$
-40\,\mathrm{dB/dec}
$$

Đây chính là ý nghĩa thực dụng nhất của pole trong bài tập: giúp đọc nhanh độ dốc Bode mà không cần thay số quá nhiều.

---

## Bài 5. Roll-off từ số pole

**Yêu cầu**

Hãy cho biết `roll-off` xấp xỉ của các bộ lọc sau:

1. bậc một
2. bậc hai
3. bậc ba

và giải thích ý nghĩa vật lý của nó.

**Đáp số ngắn**

- bậc một:

$$
-20\,\mathrm{dB/dec}
$$

- bậc hai:

$$
-40\,\mathrm{dB/dec}
$$

- bậc ba:

$$
-60\,\mathrm{dB/dec}
$$

**Cơ sở và công thức**

Mỗi pole bậc một đóng góp gần đúng:

$$
-20\,\mathrm{dB/dec}
$$

Nên:

$$
\text{roll-off} \approx -20n\,\mathrm{dB/dec}
$$

với `n` là số pole bậc một.

**Lời giải chi tiết**

`Roll-off` là tốc độ suy giảm biên độ khi tần số đi ra khỏi dải thông.

Nếu có:

- `1 pole` thì biên độ rơi khoảng `20 dB` khi tần số tăng `10 lần`
- `2 pole` thì rơi khoảng `40 dB/dec`
- `3 pole` thì rơi khoảng `60 dB/dec`

Ý nghĩa vật lý:

- `roll-off` càng dốc thì bộ lọc càng chặn mạnh tần số không mong muốn
- nhưng mạch thường phức tạp hơn vì cần nhiều phần tử tích trữ năng lượng hơn

Đây là cách nối trực tiếp giữa số pole và chất lượng chọn lọc của mạch.

---

## Bài 6. Đọc đồ thị thông dải

![Đáp ứng của mạch lọc thông dải](figures/10_bandpass_response.png){ width=84% }

**Yêu cầu**

1. Xác định ý nghĩa của $f_L$, $f_H$, $f_0$.
2. Viết công thức tính $BW$ và $f_0$.
3. Giải thích khi nào bộ lọc “sắc” hơn.

**Đáp số ngắn**

$$
BW=f_H-f_L
$$

$$
f_0=\sqrt{f_Lf_H}
$$

Bộ lọc sắc hơn khi `BW` nhỏ hoặc `Q` lớn.

**Cơ sở và công thức**

Với thông dải:

- $f_L$: cắt dưới
- $f_H$: cắt trên
- $f_0$: tần số trung tâm

Hệ số chọn lọc:

$$
Q=\frac{f_0}{BW}
$$

**Lời giải chi tiết**

Thông dải cho qua tốt chỉ một miền quanh tần số trung tâm.

Hai mép của miền đó là:

$$
f_L,\qquad f_H
$$

Từ đó:

$$
BW=f_H-f_L
$$

Tần số trung tâm được lấy theo trung bình nhân:

$$
f_0=\sqrt{f_Lf_H}
$$

Nếu `BW` nhỏ, dải thông hẹp hơn, nghĩa là mạch chọn lọc mạnh hơn. Điều đó tương ứng với:

$$
Q=\frac{f_0}{BW}
$$

cao hơn.

Đây là dạng bài thường đi kèm đồ thị đáp ứng thay vì sơ đồ mạch.


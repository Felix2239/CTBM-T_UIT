---
title: "Giải chi tiết 3 đề thi Các Thiết Bị và Mạch Điện Tử"
lang: vi
mainfont: DejaVu Sans
monofont: Noto Sans Mono
geometry: margin=1.6cm
fontsize: 10pt
header-includes:
  - \usepackage{amsmath}
  - \usepackage{amssymb}
---

# Giải chi tiết 3 đề thi

Tài liệu này giải 3 đề trong thư mục `Đề thi`. Các câu có hình mạch được đọc trực tiếp từ ảnh trang PDF. Một vài câu tự luận cần giả thiết mô hình chuẩn của môn học; các giả thiết đó được ghi rõ ngay trong lời giải.

# Đề 1: Cuối kỳ HKI 2020-2021

Nguồn: `de-thi-cuoi-ki-hki-2020-2021-mon-cac-thiet-bi-mach-dien-tu.pdf`.

## I. Trắc nghiệm

| Câu | Đáp án | Giải thích |
|---:|:---:|---|
| 1 | A | Mạch đa hài hai transistor hoạt động luân phiên: khi $Q_1$ tắt thì $Q_2$ bão hòa, và ngược lại. |
| 2 | C | Muốn tăng roll-off phải tăng bậc lọc, thường bằng cách mắc các tầng lọc nối tiếp/cascade. Thay $R,C$ chỉ đổi $f_c$, không đổi bậc. |
| 3 | C | Băng thông của mạch thông dải là khoảng giữa hai tần số cắt: $BW=f_{c2}-f_{c1}$. |
| 4 | B | Mạch gồm các ngõ vào số $D_0,D_1,D_2,D_3$ qua các điện trở có trọng số vào Op-Amp cộng đảo, nên là DAC 4 bit. |
| 5 | B | Hồi tiếp âm đưa Op-Amp về vùng tuyến tính và làm độ lợi kín phụ thuộc vào linh kiện ngoài. |
| 6 | B | Đồ thị có biên độ phẳng ở tần số thấp và suy giảm $-20\,\mathrm{dB/dec}$ sau $f_c$, nên là lọc thông thấp bậc 1. |
| 7 | D | Mạch có hai tụ ở ngõ vào kiểu active high-pass bậc 2, roll-off $-40\,\mathrm{dB/dec}$. |
| 8 | B | Trong ngữ cảnh mạch lọc, số pole gắn với bậc lọc/số cặp RC độc lập; mỗi pole đóng góp khoảng $20\,\mathrm{dB/dec}$. |

## II. Tự luận

## Bài 1: Mạch Op-Amp hai tầng

Dữ kiện đọc từ hình:

- $v_{in}=0.5\sin \omega t\;\mathrm{V}$.
- Tầng 1 là khuếch đại không đảo: $R_f=10\,\mathrm{k}\Omega$, $R_g=2\,\mathrm{k}\Omega$, nguồn nuôi $\pm 15\,\mathrm{V}$.
- Tầng 2 là khuếch đại đảo: $R_{in}=4.7\,\mathrm{k}\Omega$, $R_f=47\,\mathrm{k}\Omega$, nguồn nuôi $\pm 15\,\mathrm{V}$.

### a. Độ lợi từng tầng và toàn mạch

**Cơ sở dùng**

- Tầng không đảo: $A_v=1+\dfrac{R_f}{R_g}$
- Tầng đảo: $A_v=-\dfrac{R_f}{R_{in}}$
- Hai tầng nối tiếp: $A_v=A_{v1}A_{v2}$

**Thay số**

Vì tầng 1 là mạch khuếch đại **không đảo** nên dùng công thức độ lợi vòng kín của op-amp lý tưởng có hồi tiếp âm:

$$
A_{v1}=1+\frac{R_f}{R_g}=1+\frac{10\,\mathrm{k}\Omega}{2\,\mathrm{k}\Omega}=6
$$

Vì tầng 2 là mạch khuếch đại **đảo** nên dùng công thức:

$$
A_{v2}=-\frac{R_f}{R_{in}}=-\frac{47\,\mathrm{k}\Omega}{4.7\,\mathrm{k}\Omega}=-10
$$

Hai tầng mắc nối tiếp nên độ lợi toàn mạch bằng tích độ lợi từng tầng. Đây là quy tắc cascade:

$$
A_v=A_{v1}A_{v2}=6(-10)=-60
$$

**Kết luận**

$$
A_{v1}=6,\quad A_{v2}=-10,\quad A_v=-60
$$

### b. Phương trình $v_{o1}$ và $v_{o2}$

**Cơ sở dùng**

- Trong miền tuyến tính: $v_o=A_vv_i$
- Op-amp thực không thể cho điện áp ra vượt quá nguồn nuôi

**Thay số**

Ở miền tuyến tính của op-amp, điện áp ra bằng độ lợi nhân điện áp vào của từng tầng.

Tầng 1:

$$
 v_{o1}=A_{v1}v_{in}=6\cdot 0.5\sin\omega t=3\sin\omega t\;\mathrm{V}
$$

Biên độ đầu ra tầng 1 là $3\,\mathrm{V}$. Vì $|v_{o1}|_{max}=3\,\mathrm{V}<15\,\mathrm{V}$, đầu ra vẫn nằm trong giới hạn nguồn nuôi $\pm15\,\mathrm{V}$ nên tầng 1 chưa bão hòa.

Tầng 2 theo mô hình tuyến tính:

$$
 v_{o2}=A_{v2}v_{o1}=-10\cdot 3\sin\omega t=-30\sin\omega t\;\mathrm{V}
$$

Kết quả lý tưởng có biên độ $30\,\mathrm{V}$, nhưng định luật vận hành thực tế của op-amp là đầu ra không thể vượt quá rail nguồn. Vì nguồn nuôi chỉ là $\pm15\,\mathrm{V}$ nên đầu ra thực bị clipping:

$$
 v_{o2}\approx
 \begin{cases}
 +15\,\mathrm{V}, & -30\sin\omega t>15\\
 -30\sin\omega t, & -15\le -30\sin\omega t\le 15\\
 -15\,\mathrm{V}, & -30\sin\omega t<-15
 \end{cases}
$$

Kết luận dạng sóng:

- $v_{o1}$ là sin cùng pha với $v_{in}$, biên độ $3\,\mathrm{V}$.
- $v_{o2}$ đảo pha so với $v_{o1}$, biên độ lý tưởng $30\,\mathrm{V}$ nhưng thực tế bị cắt đỉnh ở $\pm15\,\mathrm{V}$.

## Bài 2: Khuếch đại D-MOSFET

Dữ kiện:

$$
R_1=110\,\mathrm{M}\Omega,\quad R_2=10\,\mathrm{M}\Omega,\quad V_{DD}=18\,\mathrm{V}
$$

$$
R_D=1.8\,\mathrm{k}\Omega,\quad R_S=750\,\Omega,
\quad I_{DSS}=6\,\mathrm{mA},\quad V_{GS(off)}=-3\,\mathrm{V},\quad r_{ds}=20\,\mathrm{k}\Omega
$$

Trình tự giải nên dùng cho các mạch khuếch đại FET/BJT là:

1. Phân tích DC để tìm các điện áp, dòng phân cực.
2. Suy ra điểm tĩnh $Q$.
3. Từ điểm $Q$ mới lập mạch tương đương AC và tính độ lợi, trở kháng.

### a. Phân tích DC

**Cơ sở dùng**

- Gate MOSFET gần như không hút dòng
- Chia áp: $V_G=V_{DD}\dfrac{R_2}{R_1+R_2}$
- Định luật Ohm: $V_S=I_DR_S$
- Định nghĩa: $V_{GS}=V_G-V_S$
- Shockley: $I_D=I_{DSS}\left(1-\dfrac{V_{GS}}{V_P}\right)^2$

**Thay số**

Cơ sở 1: gate của MOSFET có dòng vào xấp xỉ bằng 0, nên mạch chia áp $R_1,R_2$ hầu như không bị tải. Vì vậy điện áp gate tính bằng công thức chia áp:

$$
V_G=V_{DD}\frac{R_2}{R_1+R_2}=18\frac{10}{110+10}=1.5\,\mathrm{V}
$$

Cơ sở 2: theo định luật Ohm, điện áp trên $R_S$ là:

$$
V_S=I_D R_S=0.75I_D\;\mathrm{V}
$$

Cơ sở 3: theo định nghĩa điện áp điều khiển của FET:

$$
V_{GS}=V_G-V_S=1.5-0.75I_D
$$

Cơ sở 4: với D-MOSFET/JFET được cho bởi bộ tham số $I_{DSS},V_P$, ta dùng phương trình truyền đạt Shockley:

$$
I_D=I_{DSS}\left(1-\frac{V_{GS}}{V_P}\right)^2,
\quad V_P=-3\,\mathrm{V}
$$

Thay biểu thức $V_{GS}=1.5-0.75I_D$ vào phương trình trên để nhận được phương trình chỉ còn ẩn $I_D$:

$$
I_D=6\left(1-\frac{1.5-0.75I_D}{-3}\right)^2
$$

Giải phương trình và chọn nghiệm vật lý phù hợp với miền làm việc của transistor:

$$
I_{DQ}\approx 3.12\,\mathrm{mA}
$$

Từ dòng phân cực vừa tìm được, quay lại các công thức DC để suy ra điện áp tại điểm làm việc:

$$
V_{GSQ}=1.5-0.75(3.12)\approx -0.84\,\mathrm{V}
$$

$$
V_{DSQ}=V_{DD}-I_D(R_D+R_S)
=18-3.12\,\mathrm{mA}(1.8\,\mathrm{k}\Omega+0.75\,\mathrm{k}\Omega)
\approx 10.05\,\mathrm{V}
$$

**Kết luận**

$$
I_{DQ}\approx3.12\,\mathrm{mA},\quad V_{GSQ}\approx-0.84\,\mathrm{V},\quad V_{DSQ}\approx10.05\,\mathrm{V}
$$

### b. Điểm tĩnh Q

Vậy:

$$
Q: \quad I_D\approx3.12\,\mathrm{mA},\quad V_{GS}\approx -0.84\,\mathrm{V},\quad V_{DS}\approx10.05\,\mathrm{V}
$$

### c. Mạch tương đương tín hiệu nhỏ AC

**Cơ sở dùng**

- Ở trung tần: tụ ghép và tụ bypass xem như ngắn mạch
- Nguồn DC trở thành mass AC
- MOSFET được thay bằng mô hình tín hiệu nhỏ

Ở miền trung tần, cơ sở biến đổi mạch là:

- $C_1,C_2,C_S$ xem như ngắn mạch.
- $V_{DD}$ là mass AC.
- Gate hở dòng, nhưng có $R_1\parallel R_2$ về mass AC.
- Source được bypass bởi $C_S$, nên source là mass AC.
- MOSFET thay bằng nguồn dòng phụ thuộc $g_mv_{gs}$ từ drain xuống source, song song với $r_{ds}$.

### d. Độ lợi $A_V$ và điện áp ra khi $v_i=20\,\mathrm{mV}$

**Cơ sở dùng**

- $g_{m0}=\dfrac{2I_{DSS}}{|V_P|}$
- $g_m=g_{m0}\left(1-\dfrac{V_{GS}}{V_P}\right)$
- Tải AC tại drain là song song điện trở
- Tầng CS bypass source: $A_V\approx-g_mR_D'$
- Định nghĩa: $v_o=A_Vv_i$

**Thay số**

Cơ sở 1: độ dẫn truyền tại điểm Q của phần tử kiểu Shockley được tính bằng:

$$
g_{m0}=\frac{2I_{DSS}}{|V_P|}=\frac{2\cdot6\,\mathrm{mA}}{3\,\mathrm{V}}=4\,\mathrm{mS}
$$

$$
g_m=g_{m0}\left(1-\frac{V_{GS}}{V_P}\right)
=4\left(1-\frac{-0.84}{-3}\right)\approx2.88\,\mathrm{mS}
$$

Cơ sở 2: ở mạch AC, điện trở nhìn từ drain xuống mass là song song của $R_D$ và $r_{ds}$:

$$
R_D'=R_D\parallel r_{ds}=1.8\,\mathrm{k}\Omega\parallel20\,\mathrm{k}\Omega\approx1.65\,\mathrm{k}\Omega
$$

Vì source đã được bypass về mass AC nên đây là tầng common-source chuẩn, dùng công thức xấp xỉ:

$$
A_V\approx -g_mR_D'=-2.88\,\mathrm{mS}\cdot1.65\,\mathrm{k}\Omega\approx -4.76
$$

Cơ sở 3: định nghĩa độ lợi điện áp là $A_V=v_o/v_i$, do đó:

$$
v_o=A_Vv_i=-4.76\cdot20\,\mathrm{mV}\approx -95\,\mathrm{mV}
$$

Dấu âm nghĩa là tín hiệu ra đảo pha so với tín hiệu vào.

**Kết luận**

$$
g_m\approx2.88\,\mathrm{mS},\quad A_V\approx-4.76,\quad v_o\approx-95\,\mathrm{mV}
$$

### e. Tổng trở ngõ ra khi mắc thêm $R_L=2.7\,\mathrm{k}\Omega$

Do tải được nối qua tụ ghép nên nó không ảnh hưởng phân cực DC, nhưng trong AC tụ coi như ngắn mạch. Vì vậy $R_L$ song song với mạng thoát hiện có:

$$
Z_{out,loaded}=R_D\parallel r_{ds}\parallel R_L
$$

$$
Z_{out,loaded}=1.8\,\mathrm{k}\Omega\parallel20\,\mathrm{k}\Omega\parallel2.7\,\mathrm{k}\Omega\approx1.02\,\mathrm{k}\Omega
$$

# Đề 2: Cuối kỳ HKI 2022-2023

Nguồn: `de-thi-cuoi-ky-hki-2022-2023-mon-cac-thiet-bi-mach-dien-tu.pdf`.

## I. Trắc nghiệm

| Câu | Đáp án | Giải thích |
|---:|:---:|---|
| 1 | A | Bán dẫn loại n có hạt tải đa số là electron. |
| 2 | C | Tăng roll-off bằng tăng bậc lọc và mắc các tầng nối tiếp. |
| 3 | A | $I_B=I_C/\beta=1.52\,\mathrm{mA}/60=25.33\,\mu\mathrm{A}$, gần đáp án $25.36\,\mu\mathrm{A}$. |
| 4 | B | Mạch cộng đảo với điện trở trọng số $200\,\mathrm{k}\Omega,100\,\mathrm{k}\Omega,50\,\mathrm{k}\Omega,25\,\mathrm{k}\Omega$ là DAC 4 bit. |
| 5 | B | Điểm Q tối ưu nằm gần giữa đường tải để tín hiệu có biên độ dao động đối xứng nhất trước khi méo. |
| 6 | B | Đồ thị là thông thấp bậc 1: phẳng ở tần số thấp, suy giảm $-20\,\mathrm{dB/dec}$ sau $f_c$. |
| 7 | A | Zener còn ổn áp: $I_R=(30-20)/20=0.5\,\mathrm{A}$, $I_L=20/200=0.1\,\mathrm{A}$, $I_Z=0.4\,\mathrm{A}$, $P_Z=8\,\mathrm{W}<10\,\mathrm{W}$. Do đó $V_1=V_0=20\,\mathrm{V}$. |
| 8 | B | Pole thể hiện số cặp RC/bậc lọc. |
| 9 | C | Vùng nghèo lý tưởng không còn hạt tải tự do; chỉ còn ion cố định. |
| 10 | A | Op-Amp thực tế có trở vào lớn, trở ra nhỏ nhưng không lý tưởng vô hạn/zero tuyệt đối. |
| 11 | B | JFET điều khiển kênh bằng phân cực nghịch mối nối gate-channel. |
| 12 | D | Mạch có tụ nối tiếp ngõ vào và điện trở xuống mass nên là lọc thông cao; $f_c$ phụ thuộc $R,C$. |
| 13 | B | Op-Amp so sánh hai điện áp từ cầu Wheatstone; transistor $Q_1$ chỉ là tầng kích relay. |
| 14 | C | Độ lợi toàn mạch được định nghĩa là $A_V=V_{o2}/V_{in}$. |

## II. Tự luận

## Bài 1: Mạch lọc tích cực thông cao bậc hai

Dữ kiện đọc từ hình:

$$
R_A=R_B=1.0\,\mathrm{k}\Omega,\quad C_A=C_B=0.022\,\mu\mathrm{F}=22\,\mathrm{nF},\quad R_2=10\,\mathrm{k}\Omega
$$

### a. Tần số cắt

**Cơ sở dùng**

- Mạch Sallen-Key thông cao bậc hai đối xứng: $f_c=\dfrac{1}{2\pi RC}$

**Thay số**

Cơ sở: với mạch lọc Sallen-Key thông cao bậc hai đối xứng ($R_A=R_B=R$, $C_A=C_B=C$), tần số cắt được cho bởi:

$$
f_c=\frac{1}{2\pi RC}
$$

Thay số:

$$
f_c=\frac{1}{2\pi(1.0\times10^3)(22\times10^{-9})}
\approx 7234\,\mathrm{Hz}=7.23\,\mathrm{kHz}
$$

**Kết luận**

$$
f_c\approx7.23\,\mathrm{kHz}
$$

### b. Chọn $R_1$ để đáp ứng Butterworth

**Cơ sở dùng**

- Tra bảng Butterworth bậc 2: $\dfrac{R_1}{R_2}=0.586$

**Thay số**

Cơ sở thiết kế: đáp ứng Butterworth bậc 2 có hệ số suy giảm chuẩn, và với cấu hình đề bài thì tra bảng thiết kế được tỉ số:

$$
\frac{R_1}{R_2}=0.586
$$

Vì $R_2=10\,\mathrm{k}\Omega$:

$$
R_1=0.586R_2=0.586\cdot10\,\mathrm{k}\Omega=5.86\,\mathrm{k}\Omega
$$

Kết luận:

$$
f_c\approx7.23\,\mathrm{kHz},\quad R_1\approx5.86\,\mathrm{k}\Omega
$$

## Bài 2: BJT phân cực cầu chia áp

Dữ kiện:

$$
V_{CC}=18\,\mathrm{V},\quad R_1=33\,\mathrm{k}\Omega,
\quad R_2=10\,\mathrm{k}\Omega,
\quad R_C=2.2\,\mathrm{k}\Omega,
\quad R_E=1\,\mathrm{k}\Omega
$$

$$
V_{BE}=0.7\,\mathrm{V},\quad \beta_{DC}=\beta_{AC}=50
$$

Trình tự giải phù hợp cho BJT là:

1. Giải mạch DC trước để có $I_B$, $I_C$, $I_E$, $V_{CE}$.
2. Chốt điểm tĩnh $Q$ và kiểm tra vị trí trên đường tải DC.
3. Dùng dòng tại điểm $Q$ để tính tham số tín hiệu nhỏ rồi phân tích AC.

### a. Phân tích DC

**Cơ sở dùng**

- Quy đổi cầu chia áp sang nguồn Thevenin
- KVL vòng base-emitter
- Quan hệ dòng BJT: $I_C=\beta I_B$, $I_E=(\beta+1)I_B$
- KVL nhánh collector

**Thay số**

Cơ sở 1: mạch phân cực base bằng cầu chia áp được đổi sang nguồn tương đương Thevenin để tính dòng base dễ hơn:

$$
V_{TH}=V_{CC}\frac{R_2}{R_1+R_2}=18\frac{10}{33+10}=4.186\,\mathrm{V}
$$

$$
R_{TH}=R_1\parallel R_2=33\,\mathrm{k}\Omega\parallel10\,\mathrm{k}\Omega=7.674\,\mathrm{k}\Omega
$$

Cơ sở 2: áp dụng KVL trên vòng base-emitter:

$$
I_B=\frac{V_{TH}-V_{BE}}{R_{TH}+(\beta+1)R_E}
=\frac{4.186-0.7}{7.674\,\mathrm{k}\Omega+51\cdot1\,\mathrm{k}\Omega}
\approx59.4\,\mu\mathrm{A}
$$

Cơ sở 3: quan hệ dòng của BJT trong miền tích cực:

$$
I_C=\beta I_B=50\cdot59.4\,\mu\mathrm{A}=2.97\,\mathrm{mA}
$$

$$
I_E=(\beta+1)I_B=3.03\,\mathrm{mA}
$$

$$
V_E=I_ER_E=3.03\,\mathrm{V}
$$

Cơ sở 4: áp dụng định luật Ohm và KVL cho mạch collector:

$$
V_C=V_{CC}-I_CR_C=18-2.97\,\mathrm{mA}\cdot2.2\,\mathrm{k}\Omega=11.47\,\mathrm{V}
$$

$$
V_{CE}=V_C-V_E=11.47-3.03=8.44\,\mathrm{V}
$$

**Kết luận**

$$
I_B\approx59.4\,\mu\mathrm{A},\quad I_C\approx2.97\,\mathrm{mA},\quad I_E\approx3.03\,\mathrm{mA},\quad V_{CE}\approx8.44\,\mathrm{V}
$$

### b. Điểm tĩnh Q và đường tải DC

**Cơ sở dùng**

- Điểm Q là cặp $(I_C,V_{CE})$ ở chế độ không tín hiệu
- Đường tải DC lấy từ KVL mạch collector-emitter

**Thay số**

Điểm tĩnh được xác định bởi cặp $(I_C,V_{CE})$ tại chế độ không tín hiệu:

$$
Q:\quad I_C\approx2.97\,\mathrm{mA},\quad V_{CE}\approx8.44\,\mathrm{V}
$$

Cơ sở của đường tải DC là phương trình KVL vòng collector-emitter:

$$
V_{CE}=V_{CC}-I_CR_C-I_ER_E\approx18-I_C(R_C+R_E)
$$

Hai giao điểm xấp xỉ:

- Khi $I_C=0$: $V_{CE}=18\,\mathrm{V}$.
- Khi $V_{CE}=0$: $I_C\approx\dfrac{18}{2.2\,\mathrm{k}\Omega+1\,\mathrm{k}\Omega}=5.63\,\mathrm{mA}$.

**Kết luận**

$$
Q\approx(2.97\,\mathrm{mA},\,8.44\,\mathrm{V})
$$

### c. Hệ số ổn định nhiệt

**Cơ sở dùng**

- Công thức gần đúng đề cho: $S=1+\dfrac{R_B}{R_E}$

**Thay số**

Đề cho trực tiếp công thức gần đúng của hệ số ổn định nhiệt:

$$
S=1+\frac{R_B}{R_E}
$$

với $R_B$ là điện trở nhìn tại cực base, bỏ qua $R_{in(base)}$:

$$
R_B=R_1\parallel R_2=7.674\,\mathrm{k}\Omega
$$

$$
S=1+\frac{7.674\,\mathrm{k}\Omega}{1\,\mathrm{k}\Omega}=8.674
$$

**Kết luận**

$$
S\approx8.67
$$

### d. Phân tích AC, tính $A_V$, $A_i$ và $Z_0$

Giả thiết mạch tín hiệu bé miền trung tần, bỏ qua $r_o$ của transistor và không có tụ bypass emitter trong hình.

**Cơ sở dùng**

- $r_e\approx\dfrac{26\,\mathrm{mV}}{I_E}$
- $r_\pi=\beta r_e$
- Điện trở vào tổng là song song
- CE không bypass emitter: $A_V\approx-\dfrac{\beta R_C}{r_\pi+(\beta+1)R_E}$
- $A_i\approx A_V\dfrac{R_{in}}{R_C}$
- Bỏ qua $r_o$: $Z_0\approx R_C$

**Thay số**

Cơ sở 1: điện trở emitter nội tại của BJT được lấy theo mô hình tín hiệu nhỏ:

$$
r_e\approx\frac{26\,\mathrm{mV}}{I_E}=\frac{26\,\mathrm{mV}}{3.03\,\mathrm{mA}}=8.58\,\Omega
$$

Cơ sở 2: vì emitter không bypass nên điện trở emitter xuất hiện phản hồi âm trong AC, điện trở nhìn vào base xấp xỉ:

$$
R_{in(base)}\approx \beta(r_e+R_E)=50(8.58+1000)\approx50.43\,\mathrm{k}\Omega
$$

Cơ sở 3: điện trở vào toàn mạch là song song của bộ chia bias và điện trở nhìn vào base:

$$
R_{in}=R_1\parallel R_2\parallel R_{in(base)}
=33\,\mathrm{k}\Omega\parallel10\,\mathrm{k}\Omega\parallel50.43\,\mathrm{k}\Omega
\approx6.66\,\mathrm{k}\Omega
$$

Cơ sở 4: với mạch CE có $R_E$ không bypass, dùng công thức độ lợi gần đúng:

$$
A_V\approx-\frac{\beta R_C}{R_{in(base)}+(R_E\;\text{đã quy đổi trong }R_{in(base)})}
$$

Dạng viết rõ theo mô hình $\pi$ chính xác hơn là:

$$
A_V\approx -\frac{\beta R_C}{r_\pi+(\beta+1)R_E},
\quad r_\pi=\beta r_e
$$

$$
r_\pi=50\cdot8.58=429\,\Omega
$$

$$
A_V\approx-\frac{50\cdot2.2\,\mathrm{k}\Omega}{429\,\Omega+51\cdot1\,\mathrm{k}\Omega}
\approx-2.14
$$

Cơ sở 5: từ định nghĩa $A_i=i_o/i_i$ và $v_o=A_Vv_i$, có thể suy ra gần đúng:

$$
A_i=\frac{i_o}{i_i}\approx A_V\frac{R_{in}}{R_C}
=-2.14\frac{6.66\,\mathrm{k}\Omega}{2.2\,\mathrm{k}\Omega}
\approx-6.48
$$

Cơ sở 6: bỏ qua $r_o$ thì nhìn từ collector ra chỉ còn chủ yếu là $R_C$:

$$
Z_0\approx R_C=2.2\,\mathrm{k}\Omega
$$

**Kết luận**

$$
A_V\approx-2.14,\quad A_i\approx-6.48,\quad Z_0\approx2.2\,\mathrm{k}\Omega
$$

### e. Mắc thêm $R_L=2.7\,\mathrm{k}\Omega$

Tải mắc qua tụ ghép nên không làm đổi mạch DC. Trong AC, tụ là ngắn mạch nên tải song song với $R_C$:

$$
Z_{out,loaded}=R_C\parallel R_L
=2.2\,\mathrm{k}\Omega\parallel2.7\,\mathrm{k}\Omega
\approx1.21\,\mathrm{k}\Omega
$$

# Đề 3: Cuối kỳ HKII 2021-2022

Nguồn: `de-thi-cuoi-ky-hkii-2021-2022-cac-thiet-bi-va-mach-dien-tu-ck-ii.pdf`.

## I. Trắc nghiệm

| Câu | Đáp án | Giải thích |
|---:|:---:|---|
| 1 | A | Mạch có tụ nối tiếp ngõ vào và điện trở xuống mass ở chân không đảo, nên là lọc tích cực thông cao. Với cấu hình gain không đảo $A_v=1+R_1/R_2$, damping factor $DF=3-A_v=2-R_1/R_2$. |
| 2 | C | Vùng nghèo không có hạt tải tự do; về vật lý còn ion cố định nhưng không phải hạt tải di động. |
| 3 | A | $\beta=I_C/I_B$. Nếu $I_B=40I_C$ thì $\beta=1/40$. |
| 4 | B | Tăng roll-off bằng tăng bậc và mắc nhiều tầng lọc nối tiếp. |
| 5 | C | Op-Amp lý tưởng có trở kháng ngõ vào vô cùng lớn, trở kháng ngõ ra bằng 0, độ lợi vòng hở vô cùng lớn. |
| 6 | D | Phân cực thuận diode: anode/p-type nối cực dương, cathode/n-type nối cực âm. A và B cùng đúng. |
| 7 | A | Mạch chia áp lấy $V_{ref}$ tại nút giữa $R_1,R_2$: $V_{ref}=15\,R_2/(R_1+R_2)$. |
| 8 | C | Độ lợi kín Op-Amp phụ thuộc mạng hồi tiếp, nên thay đổi điện trở hồi tiếp sẽ thay đổi độ lợi. |
| 9 | D | Tầng đầu là khuếch đại đảo: $v_1=-(3\,\mathrm{k}\Omega/1\,\mathrm{k}\Omega)(-0.6)=1.8\,\mathrm{V}$. |
| 10 | A | Lọc thông cao RC bậc 1 có $f_c=1/(2\pi RC)$. |
| 11 | D | Đồ thị suy giảm lần lượt $-20,-40,-60\,\mathrm{dB/dec}$ khi qua 3 tần số cắt, nên là thông thấp bậc 1 mắc 3 tầng. |
| 12 | A | Bảng Butterworth bậc 2 cho $R_1/R_2=0.586$. Với $R_2=2.7\,\mathrm{k}\Omega$, $R_1=0.586\cdot2.7=1.58\,\mathrm{k}\Omega$. |

## II. Tự luận

## Bài 1: Thiết kế ổn áp Zener

Dữ kiện:

$$
V_{in}=24\,\mathrm{V},\quad V_Z=10\,\mathrm{V},\quad P_{Zmax}=240\,\mathrm{mW}
$$

$$
R_L: 100\,\Omega \rightarrow 500\,\Omega
$$

Cơ sở 1: công suất cực đại của Zener thỏa $P_Z=V_ZI_Z$, nên dòng cực đại là:

$$
I_{Zmax}=\frac{P_{Zmax}}{V_Z}=\frac{240\,\mathrm{mW}}{10\,\mathrm{V}}=24\,\mathrm{mA}
$$

Cơ sở 2: dòng tải lấy theo định luật Ohm $I_L=V_Z/R_L$. Tải nhỏ nhất về điện trở sẽ hút dòng lớn nhất:

$$
I_{Lmax}=\frac{V_Z}{100\,\Omega}=100\,\mathrm{mA}
$$

Ngược lại, với tải lớn hơn thì dòng tải nhỏ hơn:

$$
I_{Lmin}=\frac{V_Z}{500\,\Omega}=20\,\mathrm{mA}
$$

Cơ sở 3: áp dụng định luật Ohm cho điện trở nối tiếp:

$$
I_S=\frac{V_{in}-V_Z}{R_S}=\frac{14}{R_S}
$$

### a. Điều kiện chọn $R_S$

**Cơ sở dùng**

- Điều kiện còn ổn áp ở tải nặng nhất: $I_S\ge I_{Lmax}$
- Điều kiện không quá công suất ở tải nhẹ nhất: $I_Z\le I_{Zmax}$

**Thay số**

Cơ sở điều kiện 1: muốn còn ổn áp ở tải nặng nhất thì Zener phải còn ít nhất vừa dẫn, tức là dòng qua $R_S$ phải không nhỏ hơn dòng tải lớn nhất:

$$
I_S\ge I_{Lmax}
\Rightarrow \frac{14}{R_S}\ge100\,\mathrm{mA}
\Rightarrow R_S\le140\,\Omega
$$

Cơ sở điều kiện 2: ở tải nhẹ nhất, phần dòng dư chảy qua Zener là lớn nhất nên phải kiểm tra giới hạn công suất:

$$
I_Z=I_S-I_{Lmin}\le I_{Zmax}
$$

$$
\frac{14}{R_S}-20\,\mathrm{mA}\le24\,\mathrm{mA}
\Rightarrow \frac{14}{R_S}\le44\,\mathrm{mA}
\Rightarrow R_S\ge318\,\Omega
$$

Ghép hai điều kiện biên lại:

$$
R_S\le140\,\Omega \quad \text{và} \quad R_S\ge318\,\Omega
$$

Vì vậy **không tồn tại một giá trị $R_S$ nào vừa đảm bảo ổn áp từ $100\,\Omega$ đến $500\,\Omega$, vừa không làm Zener vượt công suất**. Đây là kết luận vật lý quan trọng hơn bản thân phép tính.

Nếu làm theo ghi chú của đề “lấy giá trị trung bình” giữa hai biên tính được:

$$
R_{S,avg}=\frac{140+318}{2}\approx229\,\Omega
$$

Nhưng giá trị này chỉ là lựa chọn trung gian hình thức, không thỏa điều kiện “luôn hoạt động ổn áp” ở toàn bộ dải tải.

**Kết luận**

Không tồn tại một giá trị $R_S$ thỏa đồng thời cả hai điều kiện làm việc an toàn và ổn áp cho toàn dải tải đã cho.

### b. Khi hở tải với $R_S\approx229\,\Omega$

**Cơ sở dùng**

- Hở tải: $I_L=0$
- Khi đó toàn bộ dòng qua $R_S$ đi qua Zener
- Công suất Zener: $P_Z=V_ZI_Z$

**Thay số**

Khi hở tải thì $I_L=0$, nên theo định luật nút toàn bộ dòng qua $R_S$ đều chảy qua diode Zener:

$$
I_Z=\frac{24-10}{229}\approx61.1\,\mathrm{mA}
$$

Sau đó dùng lại công thức công suất:

$$
P_Z=V_ZI_Z=10\cdot61.1\,\mathrm{mA}=611\,\mathrm{mW}
$$

So sánh:

$$
611\,\mathrm{mW}>240\,\mathrm{mW}
$$

Kết luận: khi hở tải, Zener **không hoạt động an toàn**, bị quá công suất. Muốn an toàn ở hở tải thì phải ép dòng Zener không vượt $24\,\mathrm{mA}$, tức là:

$$
R_S\ge\frac{24-10}{24\,\mathrm{mA}}\approx583\,\Omega
$$

nhưng khi đó mạch lại không đủ dòng cho tải $100\,\Omega$.

**Kết luận**

Với $R_S\approx229\,\Omega$, mạch không an toàn khi hở tải.

## Bài 2: Khuếch đại DMOSFET

Dữ kiện đọc từ đề và hình:

$$
V_{DD}=18\,\mathrm{V},\quad R_1=110\,\mathrm{M}\Omega,
\quad R_2=10\,\mathrm{M}\Omega,
\quad R_D=1.8\,\mathrm{k}\Omega,
\quad R_S=0.3\,\mathrm{k}\Omega
$$

$$
I_{DSS}=6\,\mathrm{mA},\quad V_{GS(off)}=-3\,\mathrm{V},
\quad r_d=20\,\mathrm{k}\Omega
$$

Các tụ rất lớn nên trong phân tích AC được xem là ngắn mạch.

Trình tự giải nên là:

1. Viết quan hệ DC để tìm $V_G$, $V_S$, $V_{GS}$ và $I_D$.
2. Kết luận điểm tĩnh $Q$.
3. Chuyển sang mạch AC, tính $g_m$, độ lợi và trở kháng.

### a. Phân tích DC

**Cơ sở dùng**

- Gate gần như không hút dòng
- Chia áp ở gate
- Định luật Ohm trên $R_S$
- $V_{GS}=V_G-V_S$
- Shockley cho đặc tuyến truyền đạt

**Thay số**

Cơ sở 1: gate của MOSFET gần như không hút dòng, nên điện áp gate vẫn lấy theo công thức chia áp:

$$
V_G=18\frac{10}{110+10}=1.5\,\mathrm{V}
$$

Cơ sở 2: điện áp source do dòng qua $R_S$ tạo nên theo định luật Ohm:

$$
V_S=I_DR_S=0.3I_D\;\mathrm{V}
$$

$$
V_{GS}=V_G-V_S=1.5-0.3I_D
$$

Cơ sở 3: dùng phương trình Shockley cho đặc tuyến truyền đạt:

$$
I_D=6\left(1-\frac{V_{GS}}{-3}\right)^2
$$

Thay quan hệ DC giữa $V_{GS}$ và $I_D$ vào để được phương trình một ẩn:

$$
I_D=6\left(1-\frac{1.5-0.3I_D}{-3}\right)^2
$$

Giải phương trình và chọn nghiệm vật lý:

$$
I_{DQ}\approx5.46\,\mathrm{mA}
$$

$$
V_{GSQ}=1.5-0.3(5.46)\approx-0.14\,\mathrm{V}
$$

$$
V_{DSQ}=18-I_D(R_D+R_S)
=18-5.46\,\mathrm{mA}(1.8\,\mathrm{k}\Omega+0.3\,\mathrm{k}\Omega)
\approx6.53\,\mathrm{V}
$$

**Kết luận**

$$
I_{DQ}\approx5.46\,\mathrm{mA},\quad V_{GSQ}\approx-0.14\,\mathrm{V},\quad V_{DSQ}\approx6.53\,\mathrm{V}
$$

### b. Điểm tĩnh Q

Vậy:

$$
Q:\quad I_D\approx5.46\,\mathrm{mA},\quad V_{GS}\approx-0.14\,\mathrm{V},\quad V_{DS}\approx6.53\,\mathrm{V}
$$

Nếu dùng trực tiếp dòng đề cho $I_S\approx5.5\,\mathrm{mA}$ thì kết quả gần tương tự: $V_{GS}\approx-0.15\,\mathrm{V}$, $V_{DS}\approx6.45\,\mathrm{V}$.

### c. Mạch tương đương tín hiệu nhỏ AC

Ở miền AC, dùng các quy tắc chuẩn của phân tích trung tần:

- $C_i,C_o,C_S$ xem như ngắn mạch.
- $V_{DD}$ là mass AC.
- Source được nối mass AC do $C_S$ bypass $R_S$.
- Gate có điện trở vào $R_1\parallel R_2$.
- MOSFET thay bằng nguồn dòng phụ thuộc $g_mv_{gs}$ song song với $r_d$.
- Drain có $R_D$ về mass AC.

### d. Tính $A_V$, $Z_O$, $Z_i$

**Cơ sở dùng**

- $g_{m0}=\dfrac{2I_{DSS}}{|V_P|}$
- $g_m=g_{m0}\left(1-\dfrac{V_{GS}}{V_P}\right)$
- $R_D'=R_D\parallel r_d$
- $A_V\approx-g_mR_D'$
- $Z_i\approx R_1\parallel R_2$
- $Z_O\approx R_D\parallel r_d$

**Thay số**

Cơ sở 1: độ dẫn truyền tại điểm Q được suy ra từ hệ số cực đại của đặc tuyến Shockley:

$$
g_{m0}=\frac{2I_{DSS}}{|V_P|}=\frac{2\cdot6\,\mathrm{mA}}{3\,\mathrm{V}}=4\,\mathrm{mS}
$$

$$
g_m=4\left(1-\frac{-0.14}{-3}\right)\approx3.82\,\mathrm{mS}
$$

Cơ sở 2: điện trở tải hiệu dụng tại drain là song song:

$$
R_D'=R_D\parallel r_d=1.8\,\mathrm{k}\Omega\parallel20\,\mathrm{k}\Omega\approx1.65\,\mathrm{k}\Omega
$$

Vì source được bypass về mass AC, mạch trở thành common-source chuẩn nên dùng:

$$
A_V\approx-g_mR_D'=-3.82\,\mathrm{mS}\cdot1.65\,\mathrm{k}\Omega\approx-6.30
$$

Cơ sở 3: gate không hút dòng nên tổng trở vào chủ yếu là song song của mạng phân cực:

$$
Z_i\approx R_1\parallel R_2=110\,\mathrm{M}\Omega\parallel10\,\mathrm{M}\Omega\approx9.17\,\mathrm{M}\Omega
$$

Cơ sở 4: nhìn từ drain ra khi chưa mắc tải ngoài là song song của $R_D$ và điện trở nội $r_d$:

$$
Z_O\approx R_D\parallel r_d\approx1.65\,\mathrm{k}\Omega
$$

**Kết luận**

$$
g_m\approx3.82\,\mathrm{mS},\quad A_V\approx-6.30,\quad Z_i\approx9.17\,\mathrm{M}\Omega,\quad Z_O\approx1.65\,\mathrm{k}\Omega
$$

### e. Nếu mắc thêm $R_L=2.7\,\mathrm{k}\Omega$

Tải phải mắc ở ngõ ra qua tụ ghép $C_o$, tức là một đầu $R_L$ nối tại nút $v_o$ sau tụ, đầu còn lại nối mass. Cơ sở là tụ ghép chặn DC nên không làm thay đổi điểm tĩnh của MOSFET, nhưng trong AC lại cho tín hiệu đi qua.

Khi có tải:

$$
R_{AC}=R_D\parallel r_d\parallel R_L
=1.8\,\mathrm{k}\Omega\parallel20\,\mathrm{k}\Omega\parallel2.7\,\mathrm{k}\Omega
\approx1.02\,\mathrm{k}\Omega
$$

Độ lợi mới nếu cần tính thêm:

$$
A_{V,loaded}\approx-g_mR_{AC}=-3.82\,\mathrm{mS}\cdot1.02\,\mathrm{k}\Omega\approx-3.9
$$

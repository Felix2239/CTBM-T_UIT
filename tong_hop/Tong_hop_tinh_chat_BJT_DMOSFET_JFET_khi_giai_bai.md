---
title: "Tổng Hợp Tính Chất BJT, JFET, MOSFET, Zener, Op-Amp, Đáp Ứng Tần Số, Dao Động Khi Giải Bài"
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

# Tổng hợp tính chất BJT, JFET, MOSFET, Zener, Op-Amp, đáp ứng tần số, dao động khi giải bài

Tài liệu này dùng để **tra nhanh lúc giải bài mạch điện tử**. Mục tiêu là nhớ:

- linh kiện dẫn hay tắt khi nào
- điện áp, dòng điện hay lấy gần đúng bao nhiêu
- công thức nào cần dùng
- điều kiện vùng hoạt động
- cách kiểm tra linh kiện có đang làm việc an toàn hay có thể bị cháy không
- quy tắc giải nhanh với op-amp
- các công thức nền của đáp ứng tần số, mạch lọc và cầu dao động

## 1. Bảng nhận diện siêu nhanh

| Linh kiện | Điều khiển bởi | Dòng vào cực điều khiển | Trạng thái tại điện áp điều khiển bằng 0 | Công thức dòng hay gặp |
|---|---|---:|---|---|
| `BJT` | dòng base hoặc $V_{BE}$ | không bằng 0 | thường chưa kết luận ngay | $I_C=\beta I_B$ |
| `JFET` | $V_{GS}$ | $I_G \approx 0$ | với kênh N: đã dẫn tại $V_{GS}=0$ | $I_D=I_{DSS}\left(1-\frac{V_{GS}}{V_{GS(off)}}\right)^2$ |
| `D-MOSFET` | $V_{GS}$ | $I_G \approx 0$ | đã dẫn tại $V_{GS}=0$ | thường dùng cùng dạng với JFET trong bài cơ bản |
| `E-MOSFET` | $V_{GS}$ | $I_G \approx 0$ | thường tắt tại $V_{GS}=0$ | $I_D=K(V_{GS}-V_{TH})^2$ |
| `Zener` | phân cực nghịch và điện áp đủ lớn | không áp dụng như transistor | chưa ổn áp nếu chưa vào vùng đánh thủng | $I_Z=I_R-I_L$, $P_Z=V_ZI_Z$ |

## 2. BJT khi giải bài

### 2.1. Các đại lượng cần nhớ

- Dòng:
  - $I_E = I_C + I_B$
  - $I_C = \beta I_B$
  - $I_C = \alpha I_E$
- Hệ số:
  - $\beta = \dfrac{I_C}{I_B}$
  - $\alpha = \dfrac{I_C}{I_E} = \dfrac{\beta}{\beta+1}$
- Với transistor silic:
  - $V_{BE} \approx 0.7\,V$ khi dẫn
  - $V_{CE(sat)} \approx 0.2\,V$

### 2.2. Điều kiện vùng hoạt động

**NPN**

- Ngắt:
  - $V_{BE} < 0.7\,V$ gần đúng
  - $I_B \approx 0$, $I_C \approx 0$
- Active:
  - tiếp giáp `BE` phân cực thuận
  - tiếp giáp `BC` phân cực ngược
  - dùng được $I_C=\beta I_B$
- Bão hòa:
  - transistor dẫn mạnh
  - thường lấy $V_{CE} \approx 0.2\,V$
  - không còn dùng chính xác $I_C=\beta I_B$ để tăng mãi

**PNP**

- Giống ý nghĩa vật lý như NPN nhưng đảo cực tính điện áp và chiều dòng.
- Nếu bài cơ bản, chỉ cần cẩn thận dấu điện áp.

### 2.3. Giá trị gần đúng hay dùng

| Đại lượng | Giá trị gần đúng hay dùng |
|---|---|
| $V_{BE}$ khi dẫn | $0.7\,V$ |
| $V_{CE(sat)}$ | $0.2\,V$ |
| $V_{BC}$ tại active với NPN | âm hoặc nhỏ hơn 0 theo cách viết $V_B - V_C$ |
| $\beta$ | đề bài thường cho, nếu không thì không tự ý đoán |

### 2.4. Cách giải nhanh mạch BJT DC

1. Giả sử transistor đang `active`.
2. Tính $I_B$ bằng KVL vòng base.
3. Suy ra $I_C=\beta I_B$.
4. Tính $V_{CE}$.
5. So với điều kiện bão hòa:
   - nếu $V_{CE} > 0.2\,V$ thì giả sử active hợp lý
   - nếu $V_{CE}$ ra quá nhỏ hoặc âm thì phải xét lại ở vùng bão hòa

### 2.5. Công thức hay dùng

$$
I_B=\frac{V_{nguon\_base}-V_{BE}}{R_B}
$$

$$
I_C=\beta I_B
$$

$$
I_E=I_B+I_C
$$

$$
V_{CE}=V_C-V_E
$$

## 3. JFET khi giải bài

### 3.1. Bản chất cần nhớ

- Gate là tiếp giáp `PN`.
- Dòng gate rất nhỏ:

$$
I_G \approx 0
$$

- Với `JFET kênh N`, transistor đã dẫn khi:

$$
V_{GS}=0
$$

- Muốn giảm dòng phải làm:

$$
V_{GS}<0
$$

### 3.2. Giá trị và dấu cần nhớ

**JFET kênh N**

- $V_{GS(off)} < 0$
- $V_P < 0$
- thường chỉ xét:

$$
V_{GS} \le 0
$$

- tại $V_{GS}=0$:

$$
I_D=I_{DSS}
$$

- tại $V_{GS}=V_{GS(off)}$:

$$
I_D=0
$$

**JFET kênh P**

- Dấu điện áp đảo lại so với kênh N.

### 3.3. Công thức dòng quan trọng nhất

Phương trình Shockley:

$$
I_D=I_{DSS}\left(1-\frac{V_{GS}}{V_{GS(off)}}\right)^2
$$

Hoặc viết bằng $V_P$:

$$
I_D=I_{DSS}\left(1-\frac{V_{GS}}{V_P}\right)^2
$$

### 3.4. Độ dẫn truyền

$$
g_{m0}=\frac{2I_{DSS}}{|V_P|}
$$

$$
g_m=g_{m0}\left(1-\frac{V_{GS}}{V_P}\right)
$$

### 3.5. Điều kiện cần nhớ khi giải bài

- Nếu là `JFET kênh N`, thấy $V_{GS}$ dương thì phải kiểm tra lại vì trong bài cơ bản điều này thường không hợp lệ.
- Vì $I_G \approx 0$, điện áp gate thường tìm bằng cầu chia áp hoặc bằng điện áp DC đang nối trực tiếp vào gate.
- Sau khi có $V_G$, $V_S$, luôn tính:

$$
V_{GS}=V_G-V_S
$$

### 3.6. Cách giải nhanh JFET DC

1. Tìm $V_G$.
2. Tìm $V_S=I_D R_S$ nếu source có điện trở.
3. Lập:

$$
V_{GS}=V_G-I_D R_S
$$

4. Thế vào phương trình Shockley để tìm $I_D$.
5. Tính tiếp $V_D$, $V_{DS}$.

## 4. D-MOSFET khi giải bài

### 4.1. Bản chất cần nhớ

- Gate cách ly bởi lớp oxide.
- Vì vậy:

$$
I_G \approx 0
$$

- `D-MOSFET` là loại **depletion**, nên tại:

$$
V_{GS}=0
$$

vẫn có dòng dẫn.

### 4.2. Điểm khác JFET quan trọng nhất

**D-MOSFET kênh N**

- Khi $V_{GS}=0$:

$$
I_D=I_{DSS}
$$

- Khi $V_{GS}<0$: dòng giảm.
- Khi $V_{GS}>0$: dòng tăng lên, có thể:

$$
I_D > I_{DSS}
$$

Đây là điểm khác rất quan trọng so với `JFET`.

### 4.3. Công thức thường dùng trong bài cơ bản

Rất nhiều bài cơ bản dùng cùng dạng bình phương như JFET:

$$
I_D=I_{DSS}\left(1-\frac{V_{GS}}{V_{GS(off)}}\right)^2
$$

với `kênh N` thì:

- $V_{GS(off)}<0$
- nếu $V_{GS}=0$ thì $I_D=I_{DSS}$
- nếu $V_{GS}>0$ thì dòng tăng cao hơn $I_{DSS}$

### 4.4. Khi nào cần cẩn thận

- Nếu đề cho dạng dữ kiện `ngưỡng`, `K`, `I_D(on)`, `V_{GS}(on)` thì đề có thể đang dùng mô hình kiểu MOSFET bình phương theo ngưỡng.
- Nếu đề chỉ cho `I_{DSS}` và `V_{GS(off)}` thì đa số có thể giải như JFET, nhưng phải nhớ `D-MOSFET` cho phép xét cả $V_{GS}$ dương.

### 4.5. Cách giải nhanh D-MOSFET DC

1. Tìm $V_G$ từ cầu chia áp hoặc nguồn phân cực.
2. Tìm $V_S=I_D R_S$ nếu có điện trở source.
3. Suy ra:

$$
V_{GS}=V_G-V_S
$$

4. Dùng công thức phù hợp theo dữ kiện đề bài.
5. Tính $V_D$, rồi:

$$
V_{DS}=V_D-V_S
$$

## 5. E-MOSFET khi giải bài

### 5.1. Bản chất cần nhớ

- Gate cách ly bởi lớp oxide nên:

$$
I_G \approx 0
$$

- `E-MOSFET` là loại **enhancement**, nên với `kênh N`:

$$
V_{GS}=0 \Rightarrow \text{thường chưa dẫn}
$$

- Muốn dẫn phải có:

$$
V_{GS}>V_{TH}
$$

### 5.2. Các giá trị và điều kiện cần nhớ

**E-MOSFET kênh N**

- Nếu:

$$
V_{GS}\le V_{TH}
$$

thì gần đúng:

$$
I_D\approx 0
$$

- Nếu:

$$
V_{GS}>V_{TH}
$$

thì transistor bắt đầu dẫn.

- Điện áp ngưỡng:

$$
V_{TH}
$$

là dữ kiện rất quan trọng, không được nhầm với $V_{GS(off)}$ của JFET hay D-MOSFET.

### 5.3. Công thức hay dùng

Trong miền bão hòa:

$$
I_D=K(V_{GS}-V_{TH})^2
$$

với:

$$
K=\frac{I_D(\mathrm{on})}{\left(V_{GS}(\mathrm{on})-V_{TH}\right)^2}
$$

Trong miền ohmic hay triode:

$$
I_D=K\left[2(V_{GS}-V_{TH})V_{DS}-V_{DS}^2\right]
$$

Nhiều bài cơ bản chỉ dùng miền bão hòa, nên thường chỉ cần công thức bình phương đầu tiên.

### 5.4. Kiểm tra vùng hoạt động

Nếu đã tính dòng bằng công thức miền bão hòa, phải kiểm tra lại:

$$
V_{DS}\ge V_{GS}-V_{TH}
$$

- Nếu đúng: cách tính theo miền bão hòa là hợp lệ.
- Nếu sai: transistor đang ở miền ohmic, cần đổi công thức.

### 5.5. Cách giải nhanh E-MOSFET DC

1. Tìm $V_G$, $V_S$, rồi suy ra:

$$
V_{GS}=V_G-V_S
$$

2. So sánh $V_{GS}$ với $V_{TH}$.
3. Nếu $V_{GS}\le V_{TH}$ thì thường lấy:

$$
I_D\approx 0
$$

4. Nếu $V_{GS}>V_{TH}$ thì tính $I_D$ theo công thức bình phương.
5. Tính $V_D$, $V_{DS}$.
6. Kiểm tra điều kiện:

$$
V_{DS}\ge V_{GS}-V_{TH}
$$

### 5.6. Điểm dễ nhầm với D-MOSFET

- `D-MOSFET`: tại $V_{GS}=0$ đã dẫn.
- `E-MOSFET`: tại $V_{GS}=0$ thường tắt.
- `D-MOSFET` hay gặp $I_{DSS}, V_{GS(off)}$.
- `E-MOSFET` hay gặp $V_{TH}, K, I_D(\mathrm{on}), V_{GS}(\mathrm{on})$.

## 6. Zener khi giải bài

### 6.1. Bản chất cần nhớ

- Zener thường được dùng ở **phân cực nghịch** để giữ điện áp gần như không đổi.
- Khi vào đúng vùng ổn áp:

$$
V_{OUT}\approx V_Z
$$

- Nếu bị phân cực thuận thì Zener cư xử gần giống diode thường:

$$
V_D\approx 0.7\,V
$$

### 6.2. Mô hình giải bài cơ bản

Với mạch ổn áp Zener điển hình gồm nguồn $V_{IN}$, điện trở hạn dòng $R$, diode Zener song song với tải $R_L$:

$$
I_R=\frac{V_{IN}-V_Z}{R}
$$

$$
I_L=\frac{V_Z}{R_L}
$$

$$
I_Z=I_R-I_L
$$

Nếu Zener đang ổn áp thì:

$$
V_{OUT}\approx V_Z
$$

### 6.3. Điều kiện để Zener ổn áp

Muốn Zener ổn áp đúng nghĩa thì phải có:

$$
I_Z(\min)\le I_Z \le I_Z(\max)
$$

Trong đó:

- $I_Z(\min)$ là dòng tối thiểu để Zener bắt đầu giữ áp ổn định.
- $I_Z(\max)$ là dòng lớn nhất cho phép theo datasheet hoặc theo công suất định mức.

Điện áp vào tối thiểu để bắt đầu ổn áp:

$$
V_{IN}(\min)=V_Z+R\big(I_L+I_Z(\min)\big)
$$

Nếu:

$$
V_{IN}<V_{IN}(\min)
$$

thì Zener chưa vào đúng vùng ổn áp.

### 6.4. Cách nhận biết Zener có đang ổn áp hay không

Làm theo thứ tự:

1. Giả sử Zener đang ổn áp, lấy:

$$
V_{OUT}\approx V_Z
$$

2. Tính:

$$
I_R=\frac{V_{IN}-V_Z}{R},\qquad I_L=\frac{V_Z}{R_L},\qquad I_Z=I_R-I_L
$$

3. Kiểm tra:

$$
I_Z(\min)\le I_Z \le I_Z(\max)
$$

- Nếu đúng: giả sử ổn áp là hợp lệ.
- Nếu $I_Z<I_Z(\min)$: Zener không đủ dòng để ổn áp.
- Nếu $I_Z<0$: tải đang hút nhiều hơn dòng qua điện trở, nên Zener chắc chắn không ổn áp.
- Nếu $I_Z>I_Z(\max)$: Zener bị quá dòng, rất dễ hỏng.

### 6.5. Kiểm tra Zener có cháy không

Cách kiểm tra trực tiếp nhất là kiểm tra **công suất trên Zener**:

$$
P_Z=V_ZI_Z
$$

So sánh với công suất định mức:

$$
P_Z \le P_{Z(\max)}
$$

- Nếu đúng: về công suất thì Zener chưa bị quá tải.
- Nếu:

$$
P_Z>P_{Z(\max)}
$$

thì có nguy cơ cháy hoặc hỏng.

Từ đó cũng suy ra dòng Zener lớn nhất theo công suất:

$$
I_Z(\max)=\frac{P_{Z(\max)}}{V_Z}
$$

Trong nhiều bài cơ bản, nếu đề không cho $I_Z(\max)$ mà cho công suất định mức, bạn phải tự suy ra bằng công thức này.

### 6.6. Trường hợp xấu nhất để kiểm tra cháy

Muốn kiểm tra an toàn, không chỉ tính ở một điểm mà phải xét **trường hợp xấu nhất**:

- $V_{IN}$ lớn nhất
- tải nhẹ nhất, tức $I_L$ nhỏ nhất
- trường hợp không tải thì $I_L=0$

Khi đó dòng Zener lớn nhất thường là:

$$
I_{Z(worst)}=\frac{V_{IN(\max)}-V_Z}{R}
$$

với giả sử không tải.

Rồi tính:

$$
P_{Z(worst)}=V_ZI_{Z(worst)}
$$

Nếu:

$$
P_{Z(worst)}\le P_{Z(\max)}
$$

thì thiết kế an toàn hơn nhiều.

### 6.7. Khi Zener không ổn áp thì làm gì

Nếu tính ra:

$$
I_Z<I_Z(\min)
$$

thì không được tiếp tục lấy:

$$
V_{OUT}\approx V_Z
$$

nữa.

Lúc đó, với mạch cơ bản gồm $R$ nối tiếp nguồn và tải $R_L$ song song Zener, có thể coi Zener gần như **hở mạch** rồi tính lại điện áp ra theo mạch còn lại. Trong dạng đơn giản nhất:

$$
V_{OUT}\approx V_{IN}\frac{R_L}{R+R_L}
$$

### 6.8. Đừng quên kiểm tra điện trở hạn dòng

Nhiều bài chỉ hỏi Zener có cháy không, nhưng về mặt mạch thực tế cũng nên kiểm tra điện trở:

$$
P_R=I_R^2R
$$

hoặc:

$$
P_R=(V_{IN}-V_Z)I_R
$$

Nếu điện trở quá công suất thì mạch vẫn hỏng dù Zener còn chịu được.

## 7. So sánh JFET, D-MOSFET và E-MOSFET khi giải bài

| Ý cần nhớ | `JFET` | `D-MOSFET` | `E-MOSFET` |
|---|---|---|---|
| Dòng gate | $I_G \approx 0$ | $I_G \approx 0$ | $I_G \approx 0$ |
| Tại $V_{GS}=0$ | đã dẫn, $I_D=I_{DSS}$ | đã dẫn, $I_D=I_{DSS}$ | thường tắt |
| Với kênh N, $V_{GS}<0$ | dòng giảm | dòng giảm | càng tắt hơn |
| Với kênh N, $V_{GS}>0$ | thường không dùng trong bài cơ bản | dòng tăng, vẫn dùng được | nếu vượt ngưỡng thì dẫn |
| Công thức cơ bản | Shockley | thường giống Shockley trong bài nhập môn | $I_D=K(V_{GS}-V_{TH})^2$ |

## 8. So sánh BJT và FET khi giải bài

| Ý cần nhớ | `BJT` | `JFET / D-MOSFET / E-MOSFET` |
|---|---|---|
| Đại lượng điều khiển chính | dòng base | điện áp $V_{GS}$ |
| Dòng vào cực điều khiển | có, không bỏ qua | gần như bằng 0 |
| Điện áp hay nhớ | $V_{BE}\approx0.7\,V$ | không có sụt áp gate cố định như BJT |
| Cách bắt đầu giải | tìm $I_B$ trước | tìm $V_G$, $V_S$, rồi $V_{GS}$ |

## 9. Checklist tra nhanh trước khi bấm máy

### 9.1. Nếu là BJT

- Có phải transistor silic không
- Có thể lấy $V_{BE}=0.7\,V$ không
- Đang giả sử `active` hay `bão hòa`
- Đã kiểm tra lại $V_{CE}$ chưa

### 9.2. Nếu là JFET

- Có đúng là `kênh N` hay `kênh P`
- Dấu của $V_{GS(off)}$ đã đúng chưa
- Đã dùng đúng:

$$
V_{GS}=V_G-V_S
$$

- Có lỡ dùng $V_{GS}$ dương cho `JFET kênh N` không

### 9.3. Nếu là D-MOSFET

- Tại $V_{GS}=0$ có nhớ là vẫn dẫn không
- Nếu $V_{GS}>0$, có nhớ rằng $I_D$ có thể lớn hơn $I_{DSS}$ không
- Đề cho mô hình theo `I_{DSS}, V_{GS(off)}` hay theo `V_{th}, K`

### 9.4. Nếu là E-MOSFET

- Có đang dùng đúng `V_{TH}` không
- Nếu $V_{GS}\le V_{TH}$, có nhớ rằng thường lấy $I_D\approx 0$ không
- Sau khi dùng công thức bình phương, đã kiểm tra:

$$
V_{DS}\ge V_{GS}-V_{TH}
$$

chưa

### 9.5. Nếu là Zener

- Zener có đang phân cực nghịch không
- Đã giả sử $V_{OUT}\approx V_Z$ rồi kiểm tra lại dòng chưa
- Đã tính:

$$
I_Z=I_R-I_L
$$

chưa

- Có kiểm tra:

$$
I_Z(\min)\le I_Z\le I_Z(\max)
$$

chưa

- Có kiểm tra công suất:

$$
P_Z=V_ZI_Z
$$

và so với công suất định mức chưa

## 10. Các lỗi rất hay gặp

- Nhầm `BJT` với `FET`: lấy $V_{BE}=0.7\,V$ cho gate là sai.
- Quên rằng `JFET` và `D-MOSFET` có:

$$
I_G \approx 0
$$

nên cầu chia áp ở gate thường không bị tải.

- Dùng công thức `JFET` cho `E-MOSFET` là sai.
- Với `D-MOSFET`, quên rằng khi $V_{GS}>0$ thì dòng có thể tăng hơn $I_{DSS}$.
- Với `E-MOSFET`, quên kiểm tra điều kiện:

$$
V_{DS}\ge V_{GS}-V_{TH}
$$

sau khi tính theo miền bão hòa là sai.
- Với `BJT`, tính ra $V_{CE}$ âm mà vẫn kết luận active là sai, phải chuyển sang xét bão hòa.
- Với `Zener`, thấy đề cho $V_Z$ là nhảy ngay tới $V_{OUT}=V_Z$ mà không kiểm tra $I_Z$ là sai.
- Với `Zener`, chỉ kiểm tra dòng mà quên kiểm tra công suất là sai.

## 11. Tóm tắt nhớ trong 30 giây

- `BJT`: nhớ $V_{BE}\approx0.7\,V$, $I_C=\beta I_B$, kiểm tra $V_{CE(sat)}\approx0.2\,V$.
- `JFET`: nhớ $I_G\approx0$, $V_{GS}=0$ thì đã dẫn, kênh N thường chỉ xét $V_{GS}\le0$, dùng Shockley.
- `D-MOSFET`: gần giống `JFET` trong bài cơ bản nhưng cho phép $V_{GS}$ dương, nên $I_D$ có thể lớn hơn $I_{DSS}$.
- `E-MOSFET`: tại $V_{GS}=0$ thường tắt, phải có $V_{GS}>V_{TH}$ mới dẫn, hay dùng $I_D=K(V_{GS}-V_{TH})^2$.
- `Zener`: muốn ổn áp phải có $I_Z(\min)\le I_Z\le I_Z(\max)$; muốn biết có cháy không thì kiểm tra $P_Z=V_ZI_Z\le P_{Z(\max)}$.

## 12. Op-Amp khi giải bài

### 12.1. Các tính chất lý tưởng cần nhớ

- Độ lợi vòng hở rất lớn:

$$
A_{OL}\to \infty
$$

- Dòng vào hai đầu vào rất nhỏ:

$$
i_+=i_-=0
$$

- Nếu có hồi tiếp âm và mạch đang tuyến tính thì:

$$
v_+\approx v_-
$$

Đây là điều kiện `mass ảo`.

### 12.2. Vùng hoạt động của op-amp

- Vùng tuyến tính:
  - có hồi tiếp âm
  - đầu ra chưa chạm nguồn
  - dùng được:

$$
v_+\approx v_-
$$

- Bão hòa dương:

$$
v_o\approx +V_{sat}
$$

- Bão hòa âm:

$$
v_o\approx -V_{sat}
$$

Không được dùng `mass ảo` nếu:

- mạch không có hồi tiếp âm
- mạch là comparator hoặc Schmitt trigger
- đầu ra đã bão hòa

### 12.3. Mạch đảo

- Đầu vào đi qua điện trở vào chân `-`.
- Chân `+` thường nối mass.
- Đầu ra **ngược pha** với đầu vào.

$$
A_v=\frac{v_o}{v_{in}}=-\frac{R_f}{R_i}
$$

$$
v_o=-\frac{R_f}{R_i}v_{in}
$$

### 12.4. Mạch không đảo

- Đầu vào đi vào chân `+`.
- Đầu ra **cùng pha** với đầu vào.

$$
A_v=\frac{v_o}{v_{in}}=1+\frac{R_f}{R_i}
$$

$$
v_o=\left(1+\frac{R_f}{R_i}\right)v_{in}
$$

### 12.5. Mạch theo áp

- Là trường hợp riêng của mạch không đảo.
- Đầu ra hồi tiếp trực tiếp về chân `-`.
- Đầu ra cùng pha và gần bằng đầu vào.

$$
v_o=v_{in}
$$

$$
A_v=1
$$

### 12.6. Mạch cộng đảo

- Nhiều đầu vào đi qua các điện trở riêng vào chân `-`.
- Đầu ra là tổng có trọng số và **đảo dấu**.

$$
v_o=-R_f\left(\frac{v_1}{R_1}+\frac{v_2}{R_2}+\cdots+\frac{v_n}{R_n}\right)
$$

Nếu các điện trở vào bằng nhau:

$$
v_o=-\frac{R_f}{R}(v_1+v_2+\cdots+v_n)
$$

### 12.7. Mạch vi sai

Nếu mạch cân bằng điện trở:

$$
\frac{R_2}{R_1}=\frac{R_4}{R_3}
$$

thì:

$$
v_o=\frac{R_2}{R_1}(v_2-v_1)
$$

Mạch này khuếch đại **hiệu** giữa hai tín hiệu.

### 12.8. Comparator và Schmitt trigger

**Comparator**

- Làm việc ở vùng bão hòa, không phải tuyến tính.
- Chỉ so sánh hai điện áp vào:

$$
v_o=
\begin{cases}
+V_{sat}, & v_+>v_- \\
-V_{sat}, & v_+<v_-
\end{cases}
$$

**Schmitt trigger**

- Là comparator có hồi tiếp dương.
- Có hai ngưỡng:
  - ngưỡng lên $V_{UT}$
  - ngưỡng xuống $V_{LT}$

Với mạch chia áp hồi tiếp đơn giản:

$$
V_{UT}=+\beta V_{sat},\qquad V_{LT}=-\beta V_{sat}
$$

$$
\beta=\frac{R_1}{R_1+R_2}
$$

### 12.9. Mạch tích phân và vi phân

**Tích phân**

- Tụ ở nhánh hồi tiếp.
- Đầu ra là tích phân của đầu vào và bị đảo dấu.

$$
v_o(t)=-\frac{1}{RC}\int v_{in}(t)\,dt
$$

**Vi phân**

- Tụ ở ngõ vào.
- Đầu ra tỉ lệ với đạo hàm của đầu vào và bị đảo dấu.

$$
v_o(t)=-RC\frac{dv_{in}(t)}{dt}
$$

### 12.10. Cách giải nhanh mạch op-amp

1. Xác định mạch có hồi tiếp âm hay không.
2. Nếu có hồi tiếp âm và chưa bão hòa, dùng:

$$
v_+\approx v_-,\qquad i_+=i_-=0
$$

3. Nhận dạng mạch đảo, không đảo, cộng, trừ, tích phân, vi phân hay comparator.
4. Viết công thức điện áp ra.
5. Kiểm tra đầu ra có vượt quá $\pm V_{sat}$ hay không.

## 13. Đáp ứng tần số và mạch lọc

### 13.1. Các khái niệm nền

- Tần số cắt `bậc một` thường lấy tại mức:

$$
|A|=\frac{1}{\sqrt{2}}A_{\max}
$$

tức là điểm `-3 dB`.

- Độ dốc biên độ:
  - bậc một: `20 dB/dec`
  - bậc hai: `40 dB/dec`
  - bậc $n$: `20n dB/dec`

### 13.2. Lọc thông thấp RC bậc một

- Cho tần số thấp đi qua tốt hơn tần số cao.
- Tần số cắt:

$$
f_c=\frac{1}{2\pi RC}
$$

- Khi:
  - $f\ll f_c$: biên độ ra gần giữ nguyên
  - $f\gg f_c$: biên độ ra giảm mạnh

### 13.3. Lọc thông cao RC bậc một

- Cho tần số cao đi qua tốt hơn tần số thấp.
- Tần số cắt:

$$
f_c=\frac{1}{2\pi RC}
$$

- Khi:
  - $f\ll f_c$: đầu ra rất nhỏ
  - $f\gg f_c$: đầu ra tiến gần giá trị trong dải thông

Nếu bài có tải, cần cẩn thận điện trở tương đương mà tụ nhìn thấy.

### 13.4. Lọc bậc hai: các đại lượng phải nhớ

- Tần số trung tâm:

$$
f_0
$$

- Băng thông:

$$
BW=f_H-f_L
$$

- Hệ số phẩm chất:

$$
Q=\frac{f_0}{BW}
$$

`Q` càng lớn thì đỉnh càng nhọn, dải càng hẹp.

### 13.5. Sallen-Key bậc hai đối xứng

Với thông thấp hoặc thông cao đối xứng:

$$
f_c=\frac{1}{2\pi RC}
$$

Nếu muốn đáp ứng Butterworth bậc hai:

$$
A_v\approx 1.586
$$

Nếu tầng op-amp là không đảo:

$$
A_v=1+\frac{R_2}{R_1}
$$

### 13.6. Hệ số hãm, Q và Butterworth

Trong nhiều slide:

$$
Q=\frac{1}{D}
$$

với `D` là hệ số hãm.

Với Sallen-Key đối xứng:

$$
D=3-A_v
$$

Nếu op-amp là không đảo:

$$
A_v=1+\frac{R_2}{R_1}
$$

nên:

$$
D=2-\frac{R_2}{R_1}
$$

Nếu tài liệu khác định nghĩa trực tiếp gain theo tỉ số điện trở khác, biểu thức có thể viết thành dạng khác, nhưng bản chất vẫn quay về:

$$
D=3-A_v
$$

Với Butterworth bậc hai:

$$
Q=\frac{1}{\sqrt{2}}\approx 0.707,\qquad D=\sqrt{2}\approx1.414
$$

### 13.7. Cách giải nhanh bài đáp ứng tần số

1. Nhận dạng loại lọc:
  - thông thấp
  - thông cao
  - thông dải
  - chắn dải
2. Xác định bậc mạch.
3. Tính $f_c$ hoặc $f_0$.
4. Nếu là bậc hai, tính thêm:

$$
BW,\qquad Q=\frac{f_0}{BW}
$$

5. Nếu là Sallen-Key Butterworth, tách riêng:
  - phần `RC` quyết định $f_c$
  - phần gain quyết định dạng đáp ứng

## 14. Mạch dao động và cầu Wien

### 14.1. Điều kiện Barkhausen

Muốn mạch tự dao động:

$$
A\beta=1\angle 0^\circ
$$

Tách ra:

- điều kiện pha:

$$
\angle A\beta=0^\circ \text{ hoặc }360^\circ
$$

- điều kiện biên độ ổn định:

$$
|A\beta|=1
$$

- điều kiện khởi động:

$$
|A\beta|>1
$$

### 14.2. Cầu Wien

Với cầu Wien đối xứng:

$$
f_0=\frac{1}{2\pi RC}
$$

Tại tần số dao động, mạng hồi tiếp có:

$$
\beta=\frac{1}{3}
$$

Do đó:

$$
A=\frac{1}{\beta}=3
$$

để dao động duy trì ổn định.

### 14.3. Gain của tầng khuếch đại trong cầu Wien

Nếu bộ khuếch đại là mạch op-amp không đảo:

$$
A_v=1+\frac{R_f}{R_i}
$$

Muốn dao động ổn định:

$$
1+\frac{R_f}{R_i}=3
$$

suy ra:

$$
\frac{R_f}{R_i}=2
$$

### 14.4. Điều kiện khởi động và ổn định

- Lúc khởi động thường cần:

$$
A>3
$$

để dao động lớn dần.

- Khi biên độ đã đủ lớn, cơ chế ổn định biên độ phải làm mạch quay về:

$$
A=3
$$

Nếu:

- $A<3$: dao động tắt dần
- $A=3$: dao động duy trì
- $A>3$ quá nhiều: dao động méo hoặc tăng đến bão hòa

### 14.5. Cách giải nhanh bài cầu Wien

1. Viết điều kiện pha và biên độ.
2. Dùng:

$$
f_0=\frac{1}{2\pi RC}
$$

3. Nhớ rằng tại cộng hưởng:

$$
\beta=\frac{1}{3}
$$

4. Suy ra gain yêu cầu:

$$
A=3
$$

5. Nếu tầng là không đảo, dùng:

$$
A_v=1+\frac{R_f}{R_i}
$$

để tìm điện trở.

## 15. Tóm tắt bổ sung trong 30 giây

- `Op-amp` có hồi tiếp âm và chưa bão hòa thì dùng:

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

- `Comparator` không dùng mass ảo; chỉ xét:

$$
v_+>v_- \Rightarrow v_o\approx +V_{sat}
$$

- Lọc bậc một có:

$$
f_c=\frac{1}{2\pi RC}
$$

- Lọc bậc hai nhớ:

$$
Q=\frac{f_0}{BW}
$$

- Cầu Wien nhớ:

$$
f_0=\frac{1}{2\pi RC},\qquad \beta=\frac{1}{3},\qquad A=3
$$

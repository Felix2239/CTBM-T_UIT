---
title: "Cheat Sheet 1 Trang: BJT, JFET, D-MOSFET, E-MOSFET, Zener"
author: "Codex"
lang: "vi"
mainfont: DejaVu Sans
monofont: Noto Sans Mono
geometry: margin=0.55cm,landscape
fontsize: 6pt
header-includes:
  - \usepackage{amsmath}
  - \usepackage{amssymb}
  - \usepackage{multicol}
  - \setlength{\parindent}{0pt}
  - \setlength{\parskip}{1pt}
  - \pagestyle{empty}
---

# Cheat sheet 1 trang: BJT, JFET, D-MOSFET, E-MOSFET, Zener

\begin{multicols}{3}

**Nhận diện nhanh**

| Loại | Điều khiển | Dòng vào cực điều khiển | Khi điện áp điều khiển bằng 0 |
|---|---|---:|---|
| `BJT` | $I_B$, $V_{BE}$ | có | chưa kết luận |
| `JFET` | $V_{GS}$ | $I_G\approx0$ | kênh N: đã dẫn |
| `D-MOSFET` | $V_{GS}$ | $I_G\approx0$ | đã dẫn |
| `E-MOSFET` | $V_{GS}$ | $I_G\approx0$ | thường tắt |
| `Zener` | phân cực nghịch | không áp dụng | chỉ ổn áp khi vào đánh thủng |

**BJT**

- Nhớ nhanh: $V_{BE}\approx0.7V$, $V_{CE(sat)}\approx0.2V$
- Quan hệ dòng: $I_C=\beta I_B$, $I_E=I_C+I_B$, $\alpha=\beta/(\beta+1)$
- Ngắt: $V_{BE}<0.7V$, gần đúng $I_B\approx0$, $I_C\approx0$
- Active: dùng $I_C=\beta I_B$
- Bão hòa: lấy $V_{CE}\approx0.2V$
- Công thức: $I_B=(V_{nguon\_base}-V_{BE})/R_B$
- Công thức: $V_{CE}=V_C-V_E$
- Trình tự: giả sử active -> tính $I_B$ -> tính $I_C$ -> tính $V_{CE}$ -> nếu $V_{CE}$ quá nhỏ hoặc âm thì xét bão hòa

**JFET kênh N**

- Nhớ nhanh: $I_G\approx0$, $V_{GS}=0 \Rightarrow I_D=I_{DSS}$
- Dấu: $V_{GS(off)}<0$, $V_P<0$, thường chỉ xét $V_{GS}\le0$
- Tắt khi $V_{GS}=V_{GS(off)}$
- Shockley: $I_D=I_{DSS}(1-V_{GS}/V_{GS(off)})^2$
- Độ dẫn truyền: $g_{m0}=2I_{DSS}/|V_P|$
- Tại điểm Q: $g_m=g_{m0}(1-V_{GS}/V_P)$
- Trình tự: tìm $V_G$, $V_S=I_D R_S$, suy ra $V_{GS}=V_G-V_S$, thế Shockley để tìm $I_D$, rồi tính $V_D$, $V_{DS}$

**D-MOSFET kênh N**

- Nhớ nhanh: $I_G\approx0$, $V_{GS}=0 \Rightarrow I_D=I_{DSS}$
- Nếu $V_{GS}<0$: $I_D$ giảm
- Nếu $V_{GS}>0$: $I_D$ tăng, có thể lớn hơn $I_{DSS}$
- Bài cơ bản thường dùng cùng dạng: $I_D=I_{DSS}(1-V_{GS}/V_{GS(off)})^2$
- Khác `JFET`: `D-MOSFET` cho phép dùng cả $V_{GS}<0$ và $V_{GS}>0$
- Trình tự: tìm $V_G$, $V_S$, rồi $V_{GS}=V_G-V_S$; chọn công thức theo dữ kiện đề

**E-MOSFET kênh N**

- Nhớ nhanh: $I_G\approx0$, $V_{GS}=0 \Rightarrow$ thường tắt
- Dẫn khi $V_{GS}>V_{TH}$
- Công thức chính: $I_D=K(V_{GS}-V_{TH})^2$
- Kiểm tra sau cùng: $V_{DS}\ge V_{GS}-V_{TH}$

**Zener**

- Khi ổn áp: $V_{OUT}\approx V_Z$
- Dòng: $I_R=(V_{IN}-V_Z)/R$, $I_L=V_Z/R_L$, $I_Z=I_R-I_L$
- Điều kiện: $I_Z(\min)\le I_Z\le I_Z(\max)$
- Kiểm tra cháy: $P_Z=V_ZI_Z\le P_{Z(\max)}$
- Trường hợp xấu nhất: $V_{IN}$ lớn nhất, tải nhỏ nhất, thường $I_L=0$

**Phân biệt nhanh**

- Thấy $V_{BE}\approx0.7V$, $\beta$ -> `BJT`
- Thấy $I_{DSS}$, $V_{GS(off)}$, Shockley -> `JFET` hoặc `D-MOSFET`
- Nếu $V_{GS}>0$ mà vẫn được phép tính bình thường -> nghiêng về `D-MOSFET`
- Thấy $V_{TH}$, $K$, $I_D(on)$ -> `E-MOSFET`
- Thấy $V_Z$, $I_Z$, công suất định mức -> `Zener`
- `BJT`: bắt đầu từ $I_B$
- `FET`: bắt đầu từ $V_G$, $V_S$, rồi tính $V_{GS}$

**Lỗi hay gặp**

- Dùng $V_{BE}=0.7V$ cho gate của FET
- Quên gate của `JFET`, `D-MOSFET` gần như không hút dòng
- Dùng $V_{GS}>0$ cho `JFET` kênh N trong bài cơ bản
- Tính ra $V_{CE}$ âm mà vẫn kết luận `BJT` active
- Với `E-MOSFET`, quên kiểm tra $V_{DS}\ge V_{GS}-V_{TH}$
- Với `Zener`, lấy ngay $V_{OUT}=V_Z$ mà không kiểm tra $I_Z$
- Với `Zener`, quên kiểm tra công suất $P_Z$

\end{multicols}

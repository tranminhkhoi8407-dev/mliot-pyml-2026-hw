# Bài tập về nhà: Singular Value Decomposition (SVD)

Bài tập gồm 2 câu:

1. Phân rã một ma trận có rank thấp bằng SVD.
2. Chọn số thành phần k cho Truncated SVD dựa trên tỷ lệ năng lượng.

---

# Câu 1. Phân rã ma trận

Cho ma trận:

$$
A=
\begin{bmatrix}
1 & 0 & 1\\
0 & 1 & 1\\
1 & 0 & 1\\
0 & 1 & 1
\end{bmatrix}
\in\mathbb{R}^{4\times3}
$$

## Yêu cầu

1. Chứng minh các cột của $A$ phụ thuộc tuyến tính và xác định $\operatorname{rank}(A)$.
2. Tính $A^\top A$.
3. Tìm các eigenvalues và eigenvectors trực chuẩn của $A^\top A$.
4. Sắp xếp $\lambda_1\geq\lambda_2\geq\lambda_3$.
5. Tính các singular values $\sigma_i=\sqrt{\lambda_i}$.
6. Xác định các right singular vectors $v_1,v_2,v_3$.
7. Với mỗi $\sigma_i>0$, tính $u_i=Av_i/\sigma_i$.
8. Bổ sung các vector trực chuẩn còn thiếu để viết Full SVD:

$$
A=U\Sigma V^\top
$$

với:

$$
U\in\mathbb{R}^{4\times4},\qquad
\Sigma\in\mathbb{R}^{4\times3},\qquad
V^\top\in\mathbb{R}^{3\times3}
$$

9. Viết Reduced SVD:

$$
A=U_r\Sigma_rV_r^\top
$$

10. Ghi rõ kích thước của $U_r,\Sigma_r,V_r^\top$.
11. Kiểm tra $U^\top U=I$, $V^\top V=I$ và $U\Sigma V^\top=A$.
12. Giải thích:
   - Vì sao có một singular value bằng 0?
   - Singular vector tương ứng với singular value bằng 0 liên hệ thế nào với null space của $A$?
   - Vì sao Reduced SVD vẫn tái tạo chính xác $A$?

> Phải trình bày các bước tính toán. Có thể dùng Python để kiểm tra kết quả cuối cùng.

---

# Câu 2. Chọn k cho Truncated SVD bằng tỷ lệ năng lượng

Một ma trận dữ liệu $X$ có các singular values:

$$
\sigma_1=12,\qquad
\sigma_2=5,\qquad
\sigma_3=3,\qquad
\sigma_4=1
$$

Ma trận xấp xỉ hạng $k$:

$$
X_k=\sum_{i=1}^{k}\sigma_i u_i v_i^\top
$$

## Yêu cầu

1. Xác định rank của $X$.
2. Tính tổng năng lượng:

$$
E_{\text{total}}=\sum_{i=1}^{4}\sigma_i^2
$$

3. Với $k=1,2,3,4$, tính:

$$
R(k)=
\frac{\sum_{i=1}^{k}\sigma_i^2}
{\sum_{i=1}^{4}\sigma_i^2}
$$

4. Hoàn thành bảng:

| $k$ | Năng lượng giữ lại | Tỷ lệ $R(k)$ |
|---:|---:|---:|
| 1 |  |  |
| 2 |  |  |
| 3 |  |  |
| 4 |  |  |

5. Tìm $k$ nhỏ nhất để giữ ít nhất:
   - 80% năng lượng.
   - 90% năng lượng.
   - 95% năng lượng.
   - 99% năng lượng.

6. Với $k=1,2,3$, tính:

$$
\|X-X_k\|_F=
\sqrt{\sum_{i=k+1}^{4}\sigma_i^2}
$$

7. Hoàn thành bảng:

| $k$ | $R(k)$ | $\|X-X_k\|_F$ |
|---:|---:|---:|
| 1 |  |  |
| 2 |  |  |
| 3 |  |  |

8. Giả sử $\sigma_4$ chủ yếu biểu diễn nhiễu. Chọn $k$ phù hợp và giải thích.
9. Trả lời:
   - Vì sao singular values phải được sắp xếp giảm dần?
   - Giữ càng nhiều singular values có phải lúc nào cũng tốt hơn không?
   - Sự đánh đổi giữa tỷ lệ năng lượng và mức độ nén dữ liệu là gì?

---

# Yêu cầu nộp bài

Nộp một trong hai file:

```text
svd_homework.ipynb
```

hoặc:

```text
svd_homework.pdf
```

## Quy định

- Câu 1 phải trình bày đầy đủ các bước phân rã.
- Câu 2 phải ghi rõ phép tính năng lượng và cách chọn $k$.
- Không chỉ ghi đáp án cuối cùng.
- Có thể dùng Python để kiểm tra nhưng phải giải thích kết quả.

---
**Công Nghệ Sử Dụng**<br>
_matplotlib: Vẽ đồ thị trong python<br>
_numpy: Dùng để xử lý mảng (số học, ma trận, thống kê)<br>
_imageio: Dùng để đọc hoặc ghi ảnh, video, GIF và hỗ trợ nhiều định dạng<br>
_Scipy là thư viện Python mạnh mẽ chuyên dùng cho khoa học và kỹ thuật, xây dựng trên nền NumPy. Nó mở rộng khả năng của NumPy để xử lý các bài toán nâng cao: tích phân, đạo hàm, tối ưu hóa, xử lý ảnh và tín hiệu...<br>
**Giải Thích Code**
```python
img = iio.imread('baby.jpeg')
gray = np.dot(img[..., :3], [0.299, 0.587, 0.114])
k = np.ones((5, 5)) / 25
b = sn.convolve(gray, k).astype(np.uint8)
```
Ta chuyển ảnh baby sang dạng mảng numpy thông qua imread<br>
np.dot là tích vô hướng **(sử dụng tích vô hướng do cách biểu diễn giống và tự động giảm chiều của list khi giá trị tại phần tử đó chỉ còn 1 và không cần lưu dưới dạng list nữa nên ta xài nó dù nó không liên quan gì đến tích vô hướng)**. VD: ta cớ list như sau:
```python
[
[ [100, 150, 200], [50, 100, 150] ],
[ [25, 75, 125], [200, 100, 50] ]
]
#ta lấy tại vị trí [0][0] là có giá trị là [100, 150, 200] và tích vô hướng với với [0.299, 0.587, 0.114] -> 100*0.299+150*0.587+200*0.114 ra giá trị tại vị trí [0][0] như list ở dưới và tương tự tại vị trí khác và ra list 2 chiều do chỉ có 1 giá trị, không còn là 3 giá trị RGB để cần lưu dưới dạng list nữa.
[[140.75  90.75]
 [ 65.25 130.4 ]]
```
_Từ đó ta có ảnh xám 2 chiều.<br>
_np.ones để tạo ra list 2 chiều có 5 phần tử chiều 0 và 5 phần tử chiều 1 với giá trị 1 <=> 5 hàng 5 cột và sn.convole để tích chập các phần tử trong khoảng 5x5 lại. Chia 25 vì 1 cột 5 phần tử thì 5 cột là 5 lần 5 là 5x5=25, chia tổng số rồi nhân vô các phần tử rồi cộng lại là ra trung bình cộng thôi, x1*(1/25)+x2*(1/25)+...+x25*(1/25)=(x1+x2+...+x25)/25.
_Từ Trung bình cộng đó để trải đều điểm ảnh để lọc nhiễu và uint8 là giá trị trong khoảng [0,255].
```python
iio.imwrite('baby_mean_filter.png', b)
plt.imshow(b, cmap='gray')
plt.axis('off')
plt.show()
```
_imwrite để lưu file mới tên là baby_mean_filter với b là mảng numpy chứa giá trị đã trung bình cộng tại khu vực 5x5 tại gốc đã chọn đó.
_imshow là vẽ đồ thị với vị trí tọa độ là các điểm chứa giá trị điểm ảnh từ mảng numpy b.
_show() để hiển thị ra màn hình.

Công Nghệ Sử Dụng\\
_matplotlib: Vẽ đồ thị trong python\\
_skimage: Thư viện xử lý ảnh của python dựa trên numpy\\
Giải thích cách hoạt động\\
```python
dt=skimage.io.imread("bird.png", as_gray=True)
```
*imread của thư viện skimage chuyển ảnh bird.png sang mảng số numpy, as_gray=True chuyển sang giá trị đen trắng
```python
plt.imshow(dt,cmap='gray')
plt.show()
```
imshow thuộc thư viện matplotlib để vẽ đồ thị mảng số từ imread của bird.png để thể hiện các điểm ảnh lên đồ thị tạo ra ảnh, show() để hiển thị ra màn hình.

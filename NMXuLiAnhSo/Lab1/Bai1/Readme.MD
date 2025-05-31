Công Nghệ Sử Dụng<br> 
_matplotlib: Vẽ đồ thị trong python.<br>
_skimage: Thư viện xử lý ảnh của python dựa trên numpy.<br>
Giải thích cách hoạt động<br>
```python
dt=skimage.io.imread("bird.png", as_gray=True)
```
imread của thư viện skimage chuyển ảnh bird.png sang mảng số numpy, as_gray=True chuyển sang giá trị đen trắng
```python
plt.imshow(dt,cmap='gray')
plt.show()
```
imshow thuộc thư viện matplotlib để vẽ đồ thị mảng số từ imread của bird.png để thể hiện các điểm ảnh lên đồ thị tạo ra ảnh, show() để hiển thị ra màn hình.

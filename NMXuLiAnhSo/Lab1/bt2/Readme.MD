**Công Nghệ Sử Dụng**<br>
_skimage: Thư viện xử lý ảnh của python dựa trên numpy.<br>
**Giải thích code**<br>
```python
image = io.imread('bird.png')
swapped_image = image.copy()
```
imread để biến ảnh thành mảng numpy là list 3 chiều và biến swapped_image là mảng numpy được copy từ biến image
```python
swapped_image[:, :, 0] = image[:, :, 2]
swapped_image[:, :, 2] = image[:, :, 0]
io.imsave('swapped_colors.png', swapped_image)
```
Đổi giá trị của R sang B và B sang R và lưu sang file mới có tên là swapped_colors.png với mảng numpy của swapped_image.

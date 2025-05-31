**Công Nghệ Sử Dụng**<br>
_numpy: Dùng để xử lý mảng (số học, ma trận, thống kê)<br>
_skimage: Thư viện xử lý ảnh của python dựa trên numpy<br>
**Giải thích code**<br>
```python
image = io.imread('bird.png')
red = image[:, :, 0]
green = image[:, :, 1]
blue = image[:, :, 2]
```
imread để biến ảnh thành mảng numpy và các biến red, green, blue sẽ thành mảng numpy 2 chiều do thay vì giảm đi 1 chiều list gồm 3 đơn vị màu RGB
```python
io.imsave('red_channel.png', red)
io.imsave('green_channel.png', green)
io.imsave('blue_channel.png', blue)
```
imsave để tạo ra các file tương ứng.

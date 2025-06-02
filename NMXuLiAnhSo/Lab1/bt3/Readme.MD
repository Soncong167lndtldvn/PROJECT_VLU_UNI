**Công Nghệ Sử Dụng**<br>
_skimage: Thư viện xử lý ảnh của python dựa trên numpy<br>
_numpy: Dùng để xử lý mảng (số học, ma trận, thống kê)<br>
**Giải thích code<br>
```python
image = io.imread('bird.png')
hsv_image = color.rgb2hsv(image)
```
y chang mấy file trước, chuyển đổi từ ảnh thành mảng numpy và chuyển sang từ RGB - HSV
```python
hue = (hsv_image[:, :, 0] * 255).astype(np.uint8) 
saturation = (hsv_image[:, :, 1] * 255).astype(np.uint8)
value = (hsv_image[:, :, 2] * 255).astype(np.uint8)
```
chuẩn hóa từ [0,360] về [0,1] và nhân 255 để đưa về [0,255] cho kiểu uint8
```python
io.imsave('hue.png', hue)
io.imsave('saturation.png', saturation)
io.imsave('value.png', value)
```
Lưu lại 3 file khác nhau với 3 màu riêng được tách từ RGB và chuyển sang HSV

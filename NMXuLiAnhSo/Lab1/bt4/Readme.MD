**Công Nghệ Sử Dụng**
_numpy: Dùng để xử lý mảng (số học, ma trận, thống kê)<br>
_skimage: Thư viện xử lý ảnh của python dựa trên numpy<br>
**Giải thích code**<br>
```python
image = io.imread('bird.png')
hsv_image = color.rgb2hsv(image)
```
Đưa ảnh về dạng mảng numpy và chuyển từ RGB sang HSV
```python
hsv_image[:, :, 0] = hsv_image[:, :, 0] * (1/3)
hsv_image[:, :, 2] = np.clip(hsv_image[:, :, 2] * 34, 0, 1)
```
Thay đổi giá trị bằng phép nhân, clip giúp từ nhân 34 lần chuẩn hóa về [0,1]
```python
new_rgb = color.hsv2rgb(hsv_image)
io.imsave('transformed_hsv.png', (new_rgb * 255).astype(np.uint8))
```
Lưu ảnh về lại dạng RGB sau khi thay đổi giá trị và nhân 255 để chuyển từ [0,1] thành [0,255] dưới dạng uint8

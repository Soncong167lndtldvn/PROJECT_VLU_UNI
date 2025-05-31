Công Nghệ Sử Dụng<br>
_matplotlib: Vẽ đồ thị trong python<br>
_skimage: Thư viện xử lý ảnh của python dựa trên numpy<br>
_PIL: Là thư viện để mở, chỉnh sửa, lưu ảnh trong python<br>
_imageio: Dùng để đọc hoặc ghi ảnh, video, GIF và hỗ trợ nhiều định dạng hơn PIL<br>
_numpy: Dùng để xử lý mảng (số học, ma trận, thống kê)<br>
Giải thích code<br>
```python
data = skimage.io.imread('bird.png')
```
Tạo biến chứa giá trị là mảng numpy 3 chiều được biến ra từ ảnh bird.png
```python
gray = skimage.color.rgb2gray(data) 
```
Chuyển sang dạng mảng 2 numpy 2 chiều, kết quả là ảnh float trong khoảng [0, 1]
```python
gray_uint8 = (gray * 255).astype(np.uint8)
cl = gray_uint8 & 0xF0
```
Nhân 255 vô vì gray đang ở dạng [0-1] để biến thành [0-255] (Kiểu uint8)<br>
cl để lấy 4 bit cao nhất 11110000
```python
skimage.io.imsave('birdf0.png', cl)
tmp = skimage.io.imread('birdf0.png')
plt.imshow(tmp, cmap='gray')
plt.show()
```
Lần lượt lưu file mới birdf0.png bằng imsave dưới dạng 4 bit cao rồi chuyển sang mảng numpy 2 chiều bằng imread và dùng imshow để vẽ đồ thị các điểm ảnh và show() để hiện ra màn hình.

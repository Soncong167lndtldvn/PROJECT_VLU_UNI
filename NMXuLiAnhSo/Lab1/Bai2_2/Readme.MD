Công Nghệ Sử Dụng<br>
_matplotlib: Vẽ đồ thị trong python<br>
_imageio: Dùng để đọc hoặc ghi ảnh, video, GIF và hỗ trợ nhiều định dạng hơn PIL<br>
Giải thích code hoạt động<br>
```python
dt=imageio.imread('bird.png')
```
Xử lí ảnh bằng imread để biến ảnh thành mảng numpy<br>
```python
mpl.imshow(dt)
mpl.show()
```
Đưa mảng dt vào imshow của matplotlib để vẽ các điểm của mảng lên các điểm tương tự đồ thị để tạo ra ảnh và show() để hiển thị lên màn hình.

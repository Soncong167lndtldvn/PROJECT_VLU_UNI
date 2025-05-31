Công Nghệ Sử Dụng<br>
_matplotlib: Vẽ đồ thị trong python<br>
_imageio: Dùng để đọc hoặc ghi ảnh, video, GIF và hỗ trợ nhiều định dạng hơn PIL<br>
_numpy: Dùng để xử lý mảng (số học, ma trận, thống kê)<br>
Giải thích code/thuật toán<br>
```python
dt=img.imread('bird.png')
dt_2=(dt[ :, :, 1]+dt[ :, :, 2]).astype('int32')
```
imread chuyển về dạng mảng numpy và dt_2 để cộng giá trị của 2 kênh màu 1 là green và 2 là blue, do chuyển từ hệ 3 màu RGB sang 1 màu nên mảng numpy từ 3 chiều gồm chiều x,y và chiều cuối cùng là list chứa giá trị của 3 màu thành còn 2 chiều x,y và tại x,y đó chỉ còn 1 màu nên không cần lưu thành dạng list nữa mà thành phần tử đơn nên chỉ còn 2 chiều<br>
astype('int32') là do ảnh đang ở dạng uint8 giá trị từ 0-255 nên để không bị tràn số thì ta phải đổi thành dạng int32 (4 byte)<br>
```python
mpl.imshow(dt_2)
mpl.show()
```
imshow của thư viện matplotlib để vẽ điểm của mảng num lên đồ thị tạo thành ảnh từ mảng numpy dt_2 và show() để hiển thị ra màn hình.

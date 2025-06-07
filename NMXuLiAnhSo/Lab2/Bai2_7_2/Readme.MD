**Công Nghệ Sử Dụng**<br>
Như hệt bài 2_7<br>
**Giải Thích Code**<br>
```python
img = iio.imread('baby.jpeg')
gray = np.dot(img[..., :3], [0.299, 0.587, 0.114])
```
_Này như hệt ở bài 2_7 đã có giải thích.<br>
```python
b = sn.median_filter(gray, size=5).astype(np.uint8)
```
_Sử dụng trung vị thay vì trung bình cộng quanh khu vực đó.<br>
```python
iio.imwrite('baby_median_filter.jpeg', b)
plt.imshow(b, cmap='gray')
plt.axis('off')
plt.show()
```
_Như hệt bài 2_7.

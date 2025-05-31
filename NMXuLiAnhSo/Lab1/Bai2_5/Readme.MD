**Công Nghệ Sử Dụng**<br>
_colorsys: Dùng để chuyển đổi giữa các hệ màu.<br>
Giải thích thuật toán<br>
```python
a=colorsys.rgb_to_hsv(255,0,0)
b=colorsys.rgb_to_hsv(1,0,0)
c=colorsys.rgb_to_hsv(0,255,0)
```
Khi print ra a,b,c sẽ in ra tuple với giá trị theo thứ tự là (H,S,V):<br>
_H: Nếu max là R thì sẽ tính (((G-B)/(max-min))%6)/6; nếu max là G (2+(B-R)/(max-min))/6, nếu max là B (4+(r-g)/(max-min))/6.<br>
_S: Nếu max=0 thì S=0; nếu max khác 0 thì S=(max-min)/max.<br>
_V: V=max.<br>
```python
d=colorsys.hsv_to_rgb(1,1,255)
```
Chuyển đổi từ HSV sang RGB và tính ngược ta có V=max nên ta đã có max, S=(max-min)/max => min=(1-S)*max.<br>
Với H thì ta nhân 6 ra H'=H*6, ta có C=max-min, X=C*(1-|H%2-1|) và các khoảng khi đưa về RGB là: [0,1) -> (C+min,X+min,min), [1,2) -> (X+min,C+min,min), [2,3) -> (min,C+min,X+min), [3,4) -> (min,X+min,C+min), [4,5) -> (X+min,min,C+min), [5,6) -> (C+min,min,X+min).
```python
print(f"{a}\n{b}\n{c}\n{d}")
```
In ra tuple giá trị sau khi chuyển đổi.

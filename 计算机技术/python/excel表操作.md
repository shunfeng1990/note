# python 操作 excel

#### 九九乘法表打印到 excel表内

```python
import xlwt

book = xlwt.Workbook(encoding='utf-8')  # 创建workbook对象
sheet = book.add_sheet('sheet1', cell_overwrite_ok=True)  # 创建工作表

for i in range(0, 9):
    for j in range(0, i+1):
        sheet.write(i, j, "{}*{}={}".format(j+1, i+1, (j+1)*(i+1)))

book.save('九九乘法表.xls')  # 保存
```


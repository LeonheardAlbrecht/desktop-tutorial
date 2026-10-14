#如何用python了解一张影像图？读取和分析栅格影像。
import rasterio

# 1. 打开一张影像图
img_path = r"XXXX.tif"  #在引号内填入你的影像路径。
with rasterio.open(img_path) as src:
    print(f"影像尺寸（宽x高）: {src.width} x {src.height}")
    print(f"波段数量: {src.count}")
    print(f"坐标系: {src.crs}")
    print(f"仿射变换参数: {src.transform}")
    print(f"无效值标记: {src.nodata}")

# 思考：
# 1. src.count 是几？为什么要有这么多波段？
# 2. src.crs 显示的是什么？这就是在QGIS&ARCGIS里看到的坐标系。
# 3. transform 里的数字，哪些代表了像素的大小？
# 最后，就可以知道这张影像图中的大部分详情。

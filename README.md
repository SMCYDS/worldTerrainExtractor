# worldTerrainExtractor 全球地形模型提取器
extracting terrain via open platform<br>
通过开放平台实现提取地形模型的效果<br>
Due to the limit of request origins to open platform, this code cannot run locally.<br>
由于ApiKey对于访问源的限制，该程序无法在本地运行<br>

# functions 相关函数
document.getData(zoom,x,y,resolution,imgResolution,getType)<br>
zoom: zoom of extraction area 提取区域的缩放<br>
x: X-coordinate of the picture 图像x坐标<br>
y: Y-coordinate of the picture 图像y坐标<br>
resolution: model resolution, must be the power of 2, 1024 recommended 模型分辨率(必须是2的次方)，推荐值1024<br>
imgResolution: texture resolution, must be the power of 2, 4096 recommended 贴图分辨率(必须是2的次方)，推荐值4096<br>
getType: the type of data you want to get. "model"||"img"

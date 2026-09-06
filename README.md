# worldTerrainExtractor

全球地形模型提取器 —— 通过开放地形瓦片平台提取并生成 3D 地形模型与贴图。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 简介

`worldTerrainExtractor` 是一个纯前端的 Web 工具，利用 [Nextzen](https://nextzen.org/) 的开放地形瓦片服务和卫星影像，根据用户指定的坐标和参数，提取地形高度数据并生成可下载的 3D 模型（`.obj`）及贴图文件。

> **注意**：由于地形瓦片服务对请求来源（Referer / Origin）有限制，本程序无法在本地 `file://` 协议下直接运行，需要部署到符合源限制的 Web 服务器（如 GitHub Pages）上使用。

## 在线使用

直接打开仓库中的 [`world.html`](world.html)，或部署到任意静态 Web 服务器后访问。

## 功能

- 按缩放级别（zoom）和瓦片坐标（x, y）提取指定区域的地形数据
- 生成 3D 地形模型（支持自定义分辨率，推荐 1024）
- 生成地形贴图（支持自定义贴图分辨率，推荐 4096）
- 实时预览提取进度
- 下载生成的模型和贴图文件

## API

核心函数 `document.getData`：

```javascript
document.getData(zoom, x, y, resolution, imgResolution, getType)
```

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| `zoom` | `number` | 提取区域的缩放级别 |
| `x` | `number` | 瓦片 X 坐标 |
| `y` | `number` | 瓦片 Y 坐标 |
| `resolution` | `number` | 模型分辨率，必须是 2 的幂，推荐 `1024` |
| `imgResolution` | `number` | 贴图分辨率，必须是 2 的幂，推荐 `4096` |
| `getType` | `string` | 获取的数据类型：`"model"` 或 `"img"` |

## 数据来源

- 地形高度数据：[Nextzen Terrain Tiles](https://nextzen.org/)（Terrarium 编码格式）
- 卫星影像：ArcGIS World Imagery / Mapbox Satellite

## 技术栈

- 纯 HTML / CSS / JavaScript（单文件，无构建步骤）
- Canvas 2D API（地形数据解码与贴图合成）
- 浏览器原生 Blob 下载

## 许可证

[MIT License](LICENSE)

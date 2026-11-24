# 几十 KB 的 3D

一组可以整目录部署的单文件 3D 小世界。打开 `index.html` 就是合集。

这些作品在 2026 年秋天传开：一个 HTML 文件里用 WebGPU 或 WebGL 当场生成场景，没有贴图、没有模型、没有音频文件。这里只收了 **MIT** 许可、并且能离线跑起来的那些。

## 部署

整个目录是静态文件。Nginx 示例：

```nginx
server {
    listen 80;
    server_name example.com;
    root /var/www/3d-games;
    index index.html;
}
```

WebGPU 要在安全上下文里跑：HTTPS，或者 `localhost`。可以用：

```bash
python3 -m http.server 8080
```

桌面版 Chrome 或 Edge 最合适。

## 收录

| 作品 | 文件 | 上游 |
| --- | --- | --- |
| 落日海面 | 62,236 字节 | [Noniv/web-ocean](https://github.com/Noniv/web-ocean) |
| 岸线 | 83,335 字节 | [JackHP/shoreline](https://github.com/JackHP/shoreline) |
| 亚特兰蒂斯 | 95,911 字节 | [Noniv/atlantis](https://github.com/Noniv/atlantis) |
| 深海花园 | 99,514 字节 | [Noniv/abyssal-garden](https://github.com/Noniv/abyssal-garden) |
| 哈皮卡拉 | 100,718 字节 | [DaamHaam/hapikara](https://github.com/DaamHaam/hapikara) |
| 卢克索 | 111,151 字节 | [alexadrerui/CELERE-3](https://github.com/alexadrerui/CELERE-3) |
| 虎鲨捕猎 | 121,387 字节 | [H-XX-D/abyssal-garden-shark-hunt](https://github.com/H-XX-D/abyssal-garden-shark-hunt) |
| 地下七层 | 130,777 字节 | [wquguru/fable52-fps-repro](https://github.com/wquguru/fable52-fps-repro) |
| 深潜 | 299,556 字节 | [Kaluka92/hadal](https://github.com/Kaluka92/hadal) |
| 向风岛 | 366,585 字节 | [jordanz00/Windward](https://github.com/jordanz00/Windward) |

体积是上游 HTML 的字节数。许可证原文在 `licenses/`。

## 改过的两处

地下七层和深潜原来用 jsDelivr 上的 Three.js。合集把对应版本放到 `vendor/three/`，并把这两份 HTML 里的地址改成站内相对路径，这样服务器不用再访问国外 CDN。Three.js 同样是 MIT，许可证在对应版本目录里。

其余 HTML 与上游字节一致。

Saltline（约 1.4 MB 的港口射击）没有明确开源许可，没有放进仓库。公开演示在 <https://realcodebear.github.io/saltline-fable-5.2/>。

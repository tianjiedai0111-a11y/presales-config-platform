# 售前配置平台上线说明

## 文件说明

- `index.html`：网页主程序
- `logo.png`：左上角 Logo
- `售前配置模板.xlsx`：默认配置模板，含英文翻译页
- `pdf-font-simhei.js`：PDF 导出用中文字体
- `netlify.toml`：Netlify 发布配置

## 推荐方式：GitHub + Netlify 持续部署

1. 在 GitHub 新建一个仓库，例如 `presales-config-platform`。
2. 把本文件夹里的所有文件上传到仓库根目录。
3. 打开 Netlify，选择 `Add new project`。
4. 选择 `Import an existing project`。
5. 选择 GitHub，并授权 Netlify 访问你的仓库。
6. 选择刚创建的仓库。
7. Build settings 保持简单：
   - Build command：留空
   - Publish directory：`.` 或留空
8. 点击 `Deploy site`。
9. 部署完成后，Netlify 会生成一个 `https://xxxx.netlify.app` 外网地址。
10. 后续更新时，只要把新文件 push 到 GitHub，Netlify 会自动重新部署。

## 临时方式：Netlify 手动拖拽

1. 打开 https://app.netlify.com/drop
2. 把本文件夹或 zip 包拖进去。
3. 等待发布完成。
4. Netlify 会生成一个临时外网地址。

## 后续更新配置模板

1. 在 Excel 中维护 `售前配置模板.xlsx`。
2. 保持文件名仍为 `售前配置模板.xlsx`。
3. 替换 GitHub 仓库里的同名文件。
4. Netlify 会自动更新线上版本。

## 注意

- 不要删除 `pdf-font-simhei.js`，否则中文 PDF 导出可能失败。
- 不要改 `售前配置模板.xlsx` 文件名，除非同步修改 `index.html` 中读取模板的位置。
- 登录账号密码目前写在前端代码中，只适合内部轻量访问控制，不适合放敏感数据。

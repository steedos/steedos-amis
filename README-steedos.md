前端低代码框架，通过 JSON 配置就能生成各种后台页面，极大减少开发成本，甚至可以不需要了解前端。

### 发布Steedos amis sdk版本

#### build

发版本前要先build，执行命令

```bash
npm run build --workspace amis-formula --workspace amis-core --workspace amis --workspace amis-ui
```

OR

```bash
npm run build
```

以上脚本执行后会在 `packages/amis` 路径生成一个名为 `sdk` 的文件夹，但是这个文件夹是隐藏的，它不会在vscode目录中显示，可以执行以下命令确认是否生成了sdk文件夹。

```bash
cd packages/amis
ls
```

#### 测试

华炎魔方项目配置环境变量 `STEEDOS_AMIS_URL` 指向上面build后的静态资源文件即可测试效果，url地址只需要前缀部分即可，不需要完整sdk文件地址，示例：

```bash
STEEDOS_AMIS_URL=https://8888-steedos-steedosamis-t274254lixx.ws-us121.gitpod.io/packages/amis
```

#### 发布

发布前需要先把 `packages/amis/package.json` 中的npm包名称和版本号改下：

```json
{
  "name": "@steedos-widgets/amis",
  "version": "6.3.0-patch.7",
}
```

改完后就可以发版本了，执行以下发版本指令前要先执行 `npm login` 登录。

```bash
npm run publish
```

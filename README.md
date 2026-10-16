<p align="center">
  <a href="https://github.com/jiangshang-dev/fondia-views">
    <img src="https://img.shields.io/badge/Fondia-食养智能菜谱-ff6b35?style=for-the-badge" alt="Fondia Views">
  </a>
</p>

<p align="center">
  <a href="https://github.com/jiangshang-dev/fondia-views/stargazers">
    <img src="https://img.shields.io/github/stars/jiangshang-dev/fondia-views?style=social" alt="GitHub Stars">
  </a>
  <a href="https://github.com/jiangshang-dev/fondia">
    <img src="https://img.shields.io/badge/backend-fondia-1890ff.svg" alt="Backend">
  </a>
  <a href="https://github.com/jiangshang-dev/fondia_app">
    <img src="https://img.shields.io/badge/app-fondia__app-ff6b35.svg" alt="Fondia App">
  </a>
  <img src="https://img.shields.io/badge/Vue-3-42b883.svg" alt="Vue 3">
  <img src="https://img.shields.io/badge/JeecgBoot%20Vue3-3.9.5-1890ff.svg" alt="JeecgBoot Vue3">
</p>

<h1 align="center">Fondia 饭典 · 管理后台</h1>

<p align="center">
  食养智能菜谱的管理端 · Vue3 / Vite / Ant Design Vue<br>
  后端 <a href="https://github.com/jiangshang-dev/fondia">jiangshang-dev/fondia</a>
  · App <a href="https://github.com/jiangshang-dev/fondia_app">jiangshang-dev/fondia_app</a>
</p>

---

## 先 Star，再 Clone

这个仓库对 **已经 Star 的人** 开放学习和二次开发。

还没点 Star，请不要 Clone，也不要 Fork 之后只拉代码不回访。

1. 打开 [jiangshang-dev/fondia-views](https://github.com/jiangshang-dev/fondia-views)。
2. 点右上角 **Star**。
3. Star 成功之后，再执行下面的命令。

```bash
git clone https://github.com/jiangshang-dev/fondia-views.git
cd fondia-views
```

Star 是这个项目继续维护文档和问题回复的前提。未 Star 就 Clone，视为没有接受本仓库的使用约定。

---

## 这是什么

Fondia（饭典）管理后台用来录入菜谱、配置会员和积分、处理客服与评论。它基于 JeecgBoot Vue3，菜单和按钮权限跟着后端账号走。运营人员在这里改的内容，会出现在 [App](https://github.com/jiangshang-dev/fondia_app) 里。

适合用来学习：

- JeecgBoot Vue3 怎么接一套业务后台
- 动态菜单、按钮权限和管理端接口的配合
- 菜谱、会员、积分、客服页面如何按模块拆开

接口和库表在后端仓库。本仓库只放管理端页面。

## 相关仓库

| 仓库 | 地址 | 内容 |
|------|------|------|
| 后端 | [jiangshang-dev/fondia](https://github.com/jiangshang-dev/fondia) | JeecgBoot 微服务、网关、库表 |
| 管理后台 | [jiangshang-dev/fondia-views](https://github.com/jiangshang-dev/fondia-views) | 本仓库 |
| App | [jiangshang-dev/fondia_app](https://github.com/jiangshang-dev/fondia_app) | Flutter 客户端：首页、分类、AI 厨伴、会员与我的 |

## 功能

页面在 `src/views/fondia`。系统用户、角色、菜单、字典沿用 JeecgBoot。

| 模块 | 页面 | 说明 |
|------|------|------|
| 菜谱 | 分类、菜谱、标签、Banner | 内容录入与上下架 |
| 互动 | 评论 | 评论查看与处理 |
| 用户 | 反馈 | 用户反馈 |
| 客服 | 配置、FAQ、快捷入口、工作台 | 在线客服 |
| AI | 额度 | AI 每日配额 |
| 会员 | 套餐、订阅、订单、支付 | 会员与支付单 |
| 积分 | 签到配置、签到记录、任务、流水 | 签到与积分 |
| 商城 | 商品、订单 | 积分商城 |

菜单脚本在后端仓库 `db/init_fondia_admin_menu.sql`。导入后重新登录，侧边栏才会出现这些菜单。

## 怎么连到后端

```text
管理后台 :3100
    │  /jeecgboot 代理
    ▼
后端  http://localhost:8080/jeecg-boot
或网关 http://localhost:9999
```

开发环境地址写在 `.env.development`：

```bash
VITE_PROXY = [["/jeecgboot","http://localhost:8080/jeecg-boot"],["/upload","http://localhost:3300/upload"]]
VITE_GLOB_DOMAIN_URL=http://localhost:8080/jeecg-boot
```

把 `http://localhost:8080/jeecg-boot` 换成自己的后端地址。走微服务网关时，改成 `http://localhost:9999`。其余变量保持不动。

## 技术栈

| 层次 | 选型 |
|------|------|
| 框架 | Vue 3、Vite、TypeScript |
| 组件 | Ant Design Vue 4、JeecgBoot Vue3 3.9.5 |
| 状态与路由 | Pinia、Vue Router |
| 包管理 | pnpm |
| 运行环境 | Node.js 20+ |

## 环境要求

- Node.js 20 及以上（Vite 5 不再支持 Node 14 / 16 / 17 / 19）
- pnpm
- 已启动的 Fondia 后端，默认 `http://localhost:8080/jeecg-boot`

后端的 JDK、MySQL、Redis、Nacos 见 [后端 README](https://github.com/jiangshang-dev/fondia#readme)。

## 快速开始

确认已经 Star 本仓库，并且后端可以访问。

```bash
git clone https://github.com/jiangshang-dev/fondia-views.git
cd fondia-views
pnpm install
```

改好 `.env.development` 里的接口地址后：

```bash
pnpm dev
```

浏览器打开 `http://localhost:3100`。使用后端初始化的管理员账号登录。

生产构建：

```bash
pnpm build
```

本地开发建议用最新版 Chrome，不支持 Chrome 90 以下，也不支持 IE。

## 参与贡献

1. 先 Star 本仓库。接口和库表改动请到 [fondia](https://github.com/jiangshang-dev/fondia) 提，客户端改动请到 [fondia_app](https://github.com/jiangshang-dev/fondia_app) 提。
2. Fork 之后从默认分支拉分支，分支名带上改动意图。
3. 提交前说明影响的菜单和页面，不要提交本机地址和密钥。
4. Pull Request 写清动机、验证方式和不兼容变更。

问题请到 [Issues](https://github.com/jiangshang-dev/fondia-views/issues) 提交，附上页面路径、接口和复现步骤。

## 开源协议

本仓库基于 [JeecgBoot Vue3](https://github.com/jeecgboot/JeecgBoot)，以 [Apache License 2.0](LICENSE) 发布。使用、修改和再分发时保留版权与许可声明。服务端协议见后端仓库 [Apache License 2.0](https://github.com/jiangshang-dev/fondia/blob/fondia/LICENSE)。

## 致谢

- [Fondia 后端](https://github.com/jiangshang-dev/fondia)
- [Fondia App](https://github.com/jiangshang-dev/fondia_app)
- [JeecgBoot](https://github.com/jeecgboot/JeecgBoot)
- Vue、Vite、Ant Design Vue

---

如果这份管理后台帮到了你，回到仓库点一次 **Star**。还没 Star，就先不要 Clone。

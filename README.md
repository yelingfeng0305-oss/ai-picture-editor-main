# AI 修图智能体

## 一、项目介绍

这是一套以 **AI Agent 驱动的图片编辑** 为核心的全栈项目教程，基于 Python 3.13 + FastAPI + LangChain + LangGraph + React 19 + Konva。你只需要输入一句话，AI 就能自动规划修图步骤、调用 21 种编辑工具帮你完成专业级修图，从文生图到抠图调色、区域编辑、图层拆分，全部自动搞定。

![](https://pic.yupi.icu/pine/image-20260901150955859.png)

### 为什么做这个项目？
1）赛道火热：AI 修图和 AI 生图是目前最热门的 AI 应用方向之一，各大厂和创业公司都在布局。掌握 AI 图像处理和智能体开发，求职时非常有竞争力。

2）技术含量高：这个项目涉及的技术面很广，从后端的 LangChain 模型接入、LangGraph 智能体、异步任务队列、对象存储，到前端的 Canvas 画布引擎、图层系统、选区交互，再到 AI 模型的文生图、语义分割、图像编辑，远不是增删改查能比的。

3）全栈实战：一个项目同时练 Python 后端和 React 前端，后端重点在 Agent 架构和图像处理管线，前端重点在画布引擎和复杂交互。


### 8 大核心能力

1）AI 文生图，输入提示词就能出图

在创作页输入一段提示词，AI 自动生成四张候选图，以四宫格的形式展示给你挑选。整个生成过程通过 SSE 实时推送进度，不用傻等，随时知道跑到哪一步了。选中满意的图片后，直接进入编辑器开始修图。

![](https://pic.yupi.icu/pine/image-20260901142856191.png)



2）专业级画布编辑器

基于 react-konva 搭建了一个真正能用的图片编辑器，支持画布缩放平移、图层文档管理、撤销重做，还有前后对比滑杆，一拖就能看到修图前后的效果。这不是玩具级 demo，而是对标专业修图软件的交互体验。

![](https://pic.yupi.icu/pine/image-20260831153713493.png)



3）自然语言驱动修图

这是整个项目最酷的能力。你在对话框里输入一句话，比如“把背景换成海滩”、“提高亮度和饱和度”，AI Agent 会自动分析你的需求，规划出修图步骤，然后一步步调用工具帮你执行。不需要你去找按钮、调参数，说一句话就搞定。

![](https://pic.yupi.icu/pine/image-20260831155606100.png)



4）21 种编辑工具，覆盖主流修图场景

项目内置了丰富的编辑工具：rembg 一键抠图、11 参调色（亮度/对比度/饱和度/色温等）、裁剪/翻转/缩放/旋转/移动等画布变换、AI 换背景、AI 扩图、超分辨率放大。手动点击工具栏可以用，Agent 也能自动调用，UI 和 Agent 共享同一套工具注册表。

![](https://pic.yupi.icu/pine/image-20260831160551720.png)



5）智能区域选择

集成了 SAM（Segment Anything Model）点选能力，鼠标点一下就能精准选中画面中的任意物体。还支持笔刷涂抹模式，自由绘制选区。首次点击计算 embedding，后续点击只跑 decoder，响应速度是毫秒级的。

![](https://pic.yupi.icu/pine/Google%20Chrome%202026-08-31%2016.09.05.png)



6）局部精细编辑

有了选区之后，可以做局部消除和局部替换。局部消除会用 AI inpainting 把选区内的东西抹掉，自动填补背景；局部替换可以用一句提示词描述你想换成什么，只改选区内容，其他地方纹丝不动。

![](https://pic.yupi.icu/pine/image-20260901141549744.png)



7）图层拆分和独立操作

一键把图片按语义拆成主体层和背景层，还可以选择拆出 OCR 文字层。拆完之后每个图层可以独立缩放、调色、移动，互不影响。还支持点选画面中的任意物体，把它提升为独立图层，背景自动修复。图层数据用 JSONB 持久化，切换图片再切回来，图层结构不会丢。

![](https://pic.yupi.icu/pine/image-20260831161340074.png)



8）多步计划和人机协作

当修图需求比较复杂时，AI 会输出一份包含多个步骤的结构化 JSON 计划，每一步标注了依赖关系。服务端会做工具存在性校验、参数合法性检查、依赖补全和环检测，然后按拓扑排序确定执行顺序。用户可以在计划卡片上确认执行、单步重试或取消后续，真正做到人机协作，AI 干活你把关。

![](https://pic.yupi.icu/pine/image-20260831161657975.png)



## 二、项目收获

本项目选题新颖，紧跟 AI Agent 和 AIGC 趋势，以 **专业级 AI 修图工具** 为目标。区别于增删改查的烂大街项目，你将从零搭建一个集画布编辑器、AI Agent、异步任务、图层系统于一体的全栈应用，技术深度和广度都远超普通项目。

项目内容丰富扎实，前后端 + AI Agent 全链路覆盖。

Python 全栈 + LangChain / LangGraph Agent + 专业画布编辑器 + 异步任务 + 图层系统，技术丰富，玩透 AI Agent 全栈项目开发~



## 三、更多介绍

该项目功能完整，涵盖文生图、画布编辑器、AI Agent 对话、编辑工具、区域选择、局部编辑、图层系统、多步计划、营销图、批量处理 10 大模块，覆盖了一个真实 AI 修图产品的核心业务场景。

![](https://pic.yupi.icu/pine/feature-modules.png)

本项目采用前后端分离 + 异步 Worker 架构。前端是 React 19 + Konva 的单页应用，后端是 Python FastAPI 服务，通过 REST API 和 SSE 通信。

后端内部按照路由层、业务服务层、数据访问层分层，AI 生图、抠图、扩图等耗时任务通过 ARQ 异步队列提交到独立 Worker 执行，结果通过 Redis Pub/Sub + SSE 实时推送给前端。LangChain 负责接入规划模型和绑定工具签名，LangGraph 负责 Agent 的计划编排，ToolRegistry 统一管理所有编辑工具的元信息和执行逻辑。数据分别落在 PostgreSQL（业务数据）、Redis（缓存和消息）和 MinIO（图片资源）中。

![](https://pic.yupi.icu/pine/system-architecture.png)

项目的核心业务流程非常清晰，能够帮你理清 AI Agent 项目开发的思路，比如一次 AI 修图请求的完整链路：用户输入自然语言指令 → Agent 规划修图步骤 → 服务端校验和拓扑排序 → 用户确认计划 → 按依赖自动执行工具 → 结果推送前端 → 画布实时更新。

![](https://pic.yupi.icu/pine/business-flow.png)

## 四、快速运行


### 前置条件

- Docker >= 20（含 Compose）
- Python >= 3.13
- Node.js >= 18（推荐 20+）
- 一个 [阿里云百炼 API Key](https://bailian.console.aliyun.com/)（🔧 可选，用于 AI 文生图、图像编辑和 Agent 对话）

### 1. 克隆项目

```bash
git clone https://github.com/yuyuanweb/ai-retouch-agent.git
cd ai-retouch-agent
```

### 2. 启动中间件

```bash
docker compose up -d
```

### 3. 启动后端

```bash
cd backend

# 安装 uv（已有可跳过）
curl -LsSf https://astral.sh/uv/install.sh | sh   # Windows: powershell -c "irm https://astral.sh/uv/install.ps1 | iex"

# 安装依赖（国内可加 --index-url https://pypi.tuna.tsinghua.edu.cn/simple）
uv sync --all-extras

# 配置环境变量
cp .env.example .env                  # 至少确认 IMAGE_PROVIDER，mock 免费跑通全流程，dashscope 接真实模型

# 初始化数据库
uv run alembic upgrade head

# 启动 API 服务（终端一）
uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 7302

# 启动 Worker（新开终端二）
uv run arq app.worker.WorkerSettings
```

启动成功后访问 [http://localhost:7302/api/health](http://localhost:7302/api/health)，三个字段全是 `ok` 即为正常。

### 4. 启动前端

**新开一个终端**：

```bash
cd frontend
npm install                           # 国内可加 --registry=https://registry.npmmirror.com
npm run dev
```

浏览器打开 [http://localhost:7301](http://localhost:7301) 即可使用。

### 5. 运行测试

```bash
cd backend
uv run pytest
```

测试通过 mock 隔离了大模型和第三方接口调用，不消耗 API 额度。

### 6. 部署

`Dockerfile` 提供了多阶段构建，前端编译后打进后端镜像同源托管。服务器上安全组放开 7302、7313 端口，然后：

```bash
cp .env.example .env
# 生产环境必改：JWT_SECRET（openssl rand -hex 32）、S3_PUBLIC_ENDPOINT=http://你的公网IP:7313

docker compose --profile deploy up -d --build
docker compose --profile deploy exec app alembic upgrade head
```

浏览器打开 `http://你的公网IP:7302`。




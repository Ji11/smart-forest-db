
# smart-forest-db

## 团队分工文档

### 业务线分工

| 业务线         | 负责人 |
| -------------- | ------ |
| 环境监测业务线 |        |
| 灾害预警业务线 | 我     |
| 资源管理业务线 |        |
| 设备管理业务线 |        |
| 统计分析业务线 |        |

### 各业务线要干的活

1. 画用例图、鲁棒图，写数据字典（MD文档）
2. 画ER图、UML类图（用Visio，soft.bjfu.edu.cn能下正版office，里面包含visio）
3. 逻辑结构设计，分析关系模式是否符合3NF
4. 物理结构设计：表、索引、视图的DDL
5. 数据库实施：写SQL、视图、存储过程、触发器
6. 设计后端（数据持久层）：每个人负责自己的后端模块，初步打算使用python
   flask框架，访问数据库用SQLAlchemy库，这个不急，等干完前面这些再说

### 有关数据库连接

使用阿里云数据库，我给每个人创建了对应的账号，参考群内文件account.txt
连接时用数据库管理软件（dbeaver，navicat啥的）连接服务器公网ip，输入数据库名称、用户名称和密码就能连上了

### 项目结构

使用github同步干活进度，我在github仓库建的文件夹结构是：

smart-forest-system
├── database
│   ├── environment
│   ├── alert
│   ├── resource
│   ├── device
│   └── statistics
├── backend
└── docs

database里五个文件夹对应五条业务线，里面就放数据库设计的ddl、sql、数据字典（数据字典用md格式写就行）；backend里放后端代码，docs里可以放文档

### 版本控制（GitHub）

#### 分支结构

我设了7个分支，分别是：

- `main`：主分支（最终版本）
- `develop`：开发分支（整合各功能）
- `feature/environment`：环境监测业务线功能分支
- `feature/alert`：灾害预警业务线功能分支
- `feature/resource`：资源管理业务线功能分支
- `feature/device`：设备管理业务线功能分支
- `feature/statistics`：统计分析业务线功能分支

#### 工作流程

1. pull下来代码后，平时5个人用自己对应的 `feature`分支开发
2. 写好一部分以后，提交 `commit`并推送到远程对应的 `feature`分支
3. 在github发起 `Pull Request`到 `develop`分支
4. 我来合并到 `develop`分支进行整合
5. main就先不用了，等做完课设可以统一合并到 `main`分支

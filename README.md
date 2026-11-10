# notes

后端技术笔记，按月份归档。

每条只记一个具体问题：现象、原因、结论、可运行的片段。不写泛泛的概念介绍。

## 归档

| 月份 | 内容 | 条数 |
|---|---|---|
| [2026-11](notes/2026-11.md) | PDO 预处理、Nginx proxy_pass / HTTPS / alias、MySQL 隐式类型转换 / 慢查询、Redis 分布式锁 / Session、Go defer / context、ThinkPHP 注入、Docker 多阶段构建 | 13 条 |

## 快速索引

### Nginx
- proxy_pass 带不带尾斜杠 → [11-07](notes/2026-11.md#11-07-proxy_pass-带不带尾斜杠转发路径完全不同)
- proxy_pass Host 头透传问题 → [11-09](notes/2026-11.md#11-09-proxy_pass-后转发到上游时host-头可能不是你以为的那个)
- HTTPS 配置与强制跳转 → [11-10](notes/2026-11.md#11-10-nginx-https-配置和-http-强制跳转的标准写法)
- alias 和 root 的区别 → [11-10](notes/2026-11.md#11-10-nginx-的-alias-和-root-路径拼接规则完全不同)

### MySQL
- 字符串列与数字比较索引用不上 → [11-08](notes/2026-11.md#11-08-字符串列与数字比较会让索引失效还会多匹配出数据)
- 慢查询完整排查步骤 → [11-10](notes/2026-11.md#11-10-mysql-慢查询完整排查步骤)

### Redis
- 分布式锁的三个正确姿势 → [11-09](notes/2026-11.md#11-09-redis-分布式锁的三个正确姿势)
- PHP Session 存 Redis → [11-10](notes/2026-11.md#11-10-php-用-redis-存-session-的配置和坑)

### PHP
- PDO 关闭模拟预处理的差异 → [11-07](notes/2026-11.md#11-07-pdo-关闭模拟预处理后三个行为会变)
- ThinkPHP whereRaw SQL 注入 → [11-09](notes/2026-11.md#11-09-thinkphp-5x-的-whereraw--query-闭包没转义直接拼用户输入就是-sql-注入)

### Go
- defer 和 named return → [11-09](notes/2026-11.md#11-09-go-中-defer-和-named-return-一起用时会修改返回值)
- context 超时与取消 → [11-10](notes/2026-11.md#11-10-go-的-context-在超时和取消时的正确用法)

### DevOps
- Docker 多阶段构建瘦身 → [11-10](notes/2026-11.md#11-10-docker-多阶段构建瘦身镜像)

## 约定

- 结论优先，先给答案再给原因
- 涉及版本差异的地方标注版本
- 代码片段可以直接复制运行
- 不记录未验证的猜测

## 贡献

欢迎提交 PR 补充更多踩坑记录，保持「结论 + 现象 + 可运行代码」的结构。
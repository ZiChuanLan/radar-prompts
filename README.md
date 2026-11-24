# radar-prompts

[freebie-radar](https://github.com/ZiChuanLan/freebie-radar)（资源雷达）的**审核提示词源**。服务端定时从这里拉取，改完不用发版、不用重建镜像。

## 文件

| 文件 | 作用 | 对应服务端字段 |
| --- | --- | --- |
| `system.md` | 审核主提示词（keep/kind/category/obtain/quality 的判定口径） | `settings.ai.systemPrompt` |
| `extra.md` | 补充规则，优先级高于主提示词（针对线上误判的临时收紧） | `settings.ai.extraPrompt` |

分类清单（category 取值与细类说明）由服务端按 `src/shared/taxonomy.ts` 自动追加，不写在这里，避免与本仓库漂移。

## 同步机制

- 服务端环境变量：`PROMPT_URL`（指向 `system.md` 的 raw 地址）、`PROMPT_EXTRA_URL`（指向 `extra.md`）、`PROMPT_SYNC_MINUTES`（默认 10，0 = 关闭）
- 启动时同步一次，之后按间隔轮询，带 `If-None-Match`（ETag）；304 不写库
- 拉取失败或内容非法（空、超过 20000 字、非 https）时**保留上一版**，只记录 `lastError`
- 后台仍可手工改 `systemPrompt` / `extraPrompt`，但下一次同步成功会被本仓库覆盖——这里才是真源

## 怎么改

直接改 `system.md` 或 `extra.md` 提交即可。最迟 `PROMPT_SYNC_MINUTES` 分钟后生效，也可以在后台点「立即同步」（`POST /api/ai/prompt-sync`）。

## 判定口径的边界

提示词只负责语义判断；形态（kind）还会被服务端的证据规则二次校验（`src/server/enrich/classify.ts` 的优先级表），比如仓库 URL、价格、兑换码字段这些硬事实不会被提示词推翻。

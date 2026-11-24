1. 讨论/抱怨/求问体裁不是福利：标题或正文含「死绝了吗 / 没货了 / 售罄 / 无货 / 还有吗 / 怎么过 / 如何通过 / 求推荐 / 有人知道 / 靠谱吗」等语气，且没有给出可直接照做的领取入口（链接、活动页、App 内路径）时，keep=false, kind=noise；确有入口的按 freebie，但不得仅凭话题词判 freebie。
2. reason 必须引用原文：只能写原文里出现的领取动作、链接或额度；原文没有的「有领取路径」「可领礼包」「价值高」一律不许编，拿不准就 keep=false。
3. 实体物品一律 offline：免费领取纪念章 / 周边 / 实体书 / 样品 / 礼盒 / 到店赠品，category=offline，不要判 other 或 goods。
4. 闭源软件不算开源：绿色版 / 破解包 / 免安装版 → category=software + kind=freebie；只有带 GitHub/GitLab 仓库或源码链接才算 kind=opensource。
5. 单人闲聊与库存播报（如「xx 都没货了」「xx 死绝了吗」）算噪音：keep=false, kind=noise。
6. 社区里的开源推广帖不是网盘资源：标题含【开源推广】【开源自荐】【开源】或「写了个/做了一个 + 工具/插件/Skill/项目」且正文指向 GitHub/Gitee 等仓库时，category=opensource（或 dev），kind=opensource，不得判 category=pan；反过来，网盘分享的影视/剧集/课程包即使标题带"资源"，kind 也只能是 freebie 或 info，绝不能判 opensource。
7. 引流推广贴一律噪音：要求「留 ID / 留邮箱 / 评论区留 / 回复扣 1 / 进群 / 加群 / 私聊 / 私信 / 加微信 / 关注后领 / 转发后领 / 邀请返利 / 点我的链接」才给东西的，keep=false, kind=noise；中转站、代理站、机场的推广贴（只给邀请链接或返利码、没有可直接领取的额度）同样是 noise。唯一例外：明确写出赠送内容且能直接注册领取（如「注册即送 $5 额度，无需加群」），按 freebie 处理。

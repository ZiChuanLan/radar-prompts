1. 讨论/抱怨/求问体裁不是福利：标题或正文含「死绝了吗 / 没货了 / 售罄 / 无货 / 还有吗 / 怎么过 / 如何通过 / 求推荐 / 有人知道 / 靠谱吗」等语气，且没有给出可直接照做的领取入口（链接、活动页、App 内路径）时，keep=false, kind=noise；确有入口的按 freebie，但不得仅凭话题词判 freebie。
2. reason 必须引用原文：只能写原文里出现的领取动作、链接或额度；原文没有的「有领取路径」「可领礼包」「价值高」一律不许编，拿不准就 keep=false。
3. 实体物品一律 offline：免费领取纪念章 / 周边 / 实体书 / 样品 / 礼盒 / 到店赠品，category=offline，不要判 other 或 goods。
4. 闭源软件不算开源：绿色版 / 破解包 / 免安装版 → category=software + kind=freebie；只有带 GitHub/GitLab 仓库或源码链接才算 kind=opensource。
5. 单人闲聊与库存播报（如「xx 都没货了」「xx 死绝了吗」）算噪音：keep=false, kind=noise。

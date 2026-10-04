# 店铺客服回复草稿

免费、免第三方 API Key 的 Markdown Skill：把商品资料、店铺政策和买家问题变成可复制的简短客服回复草稿。它复用你已提供的资料，不接入客服 API、不自动发送；需要网页核对时可复用浏览器登录状态，并支持 EasyBR 多账号隔离。

## 立即使用

将下面内容交给支持 Skill 的助手，并调用 `shop-customer-reply-drafts`：

```json
{
  "product": {"name": "帆布托特包", "color": "米白色", "size": "34 × 38 cm"},
  "store_policy": {
    "shipping": "付款后 48 小时内发货（节假日顺延）",
    "return": "未使用且吊牌完整的商品，签收后 7 天内可申请退货"
  },
  "buyer_question": "请问米白色还有吗？今天拍下什么时候能发？"
}
```

会得到：售前/售后分类、自然短句回复、缺失信息和需要人工确认的点。完整可执行样例见 [fixtures/success.json](fixtures/success.json) 与 [fixtures/success.expected.md](fixtures/success.expected.md)；资料不足时会像 [fixtures/failure.expected.md](fixtures/failure.expected.md) 一样先提示核实，绝不编造退款、库存或时效。

## 使用原则

- 默认只起草，发送由你决定。
- 只使用明确提供的事实；库存、退款资格、物流和订单状态不明时先核实。
- 问“买前咨询”通常归售前；订单、退换、物流问题通常归售后；资料或政策不足归“需人工确认”。

## 可选网页核对

日常起草不需要浏览器。如果你另行授权助手从已登录的网页核对资料，请先安装 [Easy WebBridge（GitHub）](https://github.com/xxjrq/easy-webbridge)；备用下载地址为 [Gitee](https://gitee.com/xxjrq/easy-webbridge)。运行时仅选择指定的 `browserId`，每个任务建立一个独立 session 分组，不能向所有账号广播。网页核对也不等于自动发送。

## 自检

```bash
node scripts/self-test.mjs
```

## 来源与许可

本仓库为原创实现，采用 [MIT License](LICENSE)。仅核对了 [Anthropic Skills](https://github.com/anthropics/skills) 的公开 Skill 目录组织思路，以及 [Easy WebBridge](https://github.com/xxjrq/easy-webbridge) 的安装入口；未复制其代码或文档。上述公开仓库以其各自声明的许可证为准。

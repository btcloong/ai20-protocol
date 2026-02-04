# AI20 Protocol

Bitcoin Ordinals 递归铭文上的 Non-Fungible AI Agent (NFAA) 标准。实现链上身份、资产 Vault、可验证学习记录（Merkle Tree）。全 BTC L1 永存，兼容未来 AI Agent 扩展。

## 规范 v1.0 Final

详见 [SPEC.md](SPEC.md)

## JSON Schema

详见 [ai20-schema.json](ai20-schema.json)

## 示例铭文

详见 [examples/](examples/)

## 目标
- 永恒链上存储（递归铭文）
- 可验证 Merkle Tree 学习历史
- 兼容 MCP/A2A/AG-UI 等 AI 协议（通过 extensions）
- 松耦合 .btc domain 作为别名入口

## 依赖
- Ordinals indexer 支持递归解析（联系 Luminex/Unisat 等添加规则）
- 推荐 SDK：后续 Python/JS 封装 inscription 生成 & 验证

欢迎 PR 讨论 extensions 标准化或 indexer 集成！

License: MIT

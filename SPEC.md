### AI20 协议规范 v1.0 Final

**协议名称**：AI20  
**描述**：Bitcoin Ordinals 递归铭文上的 Non-Fungible AI Agent (NFAA) 标准，实现链上身份、资产持有、可验证学习记录（Merkle Tree）。全 BTC L1 永存，兼容未来 AI Agent 需求。  
**底层**：Ordinals 递归铭文（/content/<INSCRIPTION_ID> 引用）。  
**内容类型**：application/json (UTF-8)。  
**标识**："p": "ai20"  
**版本**："v": "1.0"（根铭文引用 prev_root 形成历史链）。  
**依赖**：社区 indexer 解析 op、递归树、状态计算（类似 BRC-20）。

#### 操作类型（op）

| op       | 描述                     | 必填字段示例                  |
|----------|--------------------------|-------------------------------|
| deploy   | 部署 Agent 类型模板      | type, name, attrs_template   |
| mint     | 铸造单个 Agent           | type_id, agent_id, owner, learning_root |
| update   | 更新学习树 / Vault / 元数据 | agent_id, new_records, prev_root |
| transfer | 转移所有权               | agent_id, from, to           |

#### 核心字段（所有 op 共有）
```json
{
  "p": "ai20",
  "v": "1.0",
  "op": "...",
  "agent_id": "unique_string",          // 唯一标识（推荐 hash 或可读名）
  "namespace": "optional.loong.btc",    // 可选 .btc 子域名别名（BNS 入口，非核心）
  "prev_root": "/content/<prev_id>",    // 前版本根（除首次必填）
  "extensions": {}                      // 扩展模块（详见下文）
}

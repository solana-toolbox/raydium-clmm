# Raydium CLMM 部署指南

本文档提供了如何将 Raydium CLMM 部署到 Solana 测试网和主网的详细步骤。

## 前置要求

- 已安装 Solana CLI 工具
- 已创建 Solana 钱包（部署者钱包）
- 确保钱包中有足够的 SOL 支付交易费用

## 测试网部署步骤

1. **配置 Solana CLI 连接到测试网**
   ```bash
   solana config set --url https://api.devnet.solana.com
   ```

2. **确认连接状态**
   ```bash
   solana cluster-version
   ```

3. **部署合约**
   ```bash
   anchor deploy --provider.cluster devnet
   ```

4. **验证部署**
   - 在 Solana Explorer (https://explorer.solana.com/?cluster=devnet) 上查看部署的程序
   - 记录下程序 ID 以供后续使用

## 主网部署步骤

1. **配置 Solana CLI 连接到主网**
   ```bash
   solana config set --url https://api.mainnet-beta.solana.com
   ```

2. **确认连接状态**
   ```bash
   solana cluster-version
   ```

3. **部署合约**
   ```bash
   anchor deploy --provider.cluster mainnet
   ```

4. **验证部署**
   - 在 Solana Explorer (https://explorer.solana.com) 上查看部署的程序
   - 记录下程序 ID 以供后续使用

## 部署后配置

1. **更新程序 ID**
   - 在项目的 `Anchor.toml` 文件中更新程序 ID
   - 在前端代码中更新相应的程序 ID

2. **初始化必要的账户**
   - 部署后需要初始化必要的程序账户
   - 确保所有配置参数正确设置

## 安全注意事项

- 部署前务必进行充分的测试
- 确保部署钱包的私钥安全存储
- 主网部署前建议进行安全审计
- 确保程序的管理权限正确设置

## 常见问题处理

1. **部署失败**
   - 检查钱包余额是否充足
   - 确认网络连接是否稳定
   - 验证合约代码是否正确编译

2. **交易确认问题**
   - 检查网络拥堵情况
   - 适当调整交易费用

## 相关资源

- [Solana 文档](https://docs.solana.com)
- [Anchor 框架文档](https://www.anchor-lang.com)
- [Raydium 官方文档](https://docs.raydium.io)

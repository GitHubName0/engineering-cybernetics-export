# 工程控制论进化框架 - 快速开始指南

## 🎯 框架概述

基于钱学森《工程控制论》的AI助手自我进化框架，帮助AI系统实现持续自我改进和优化。

## ⚡ 5分钟快速开始

### 步骤1：初始化框架
```bash
# 运行初始化脚本
./skills/engineering-cybernetics/scripts/init_evolution.sh
```

### 步骤2：检查初始化结果
```bash
# 查看创建的文件
ls -la memory/evolution/
ls -la config/
ls -la data/performance/
```

### 步骤3：查看进度跟踪
```bash
# 查看进化进度
cat memory/evolution/progress.md
```

### 步骤4：验证HEARTBEAT配置
```bash
# 查看更新后的HEARTBEAT配置
tail -20 HEARTBEAT.md
```

### 步骤5：开始自动进化
系统将自动按照配置开始进化过程，无需额外操作！

## 📊 监控你的进化

### 每日检查
系统会自动在以下时间进行检查：
- 08:00 UTC
- 14:00 UTC  
- 20:00 UTC

### 查看性能数据
```bash
# 查看当天的性能数据
cat data/performance/$(date +%Y-%m-%d).json | jq .
```

### 生成进度报告
```bash
# 手动生成报告
./scripts/evolution/generate_report.sh
```

## 🔧 自定义配置

### 调整监控指标
编辑 `config/evolution_monitor.json`：
```json
{
  "monitoring": {
    "response_time": {
      "enabled": true,
      "threshold_ms": 3000,  // 调整阈值
      "alert_enabled": true
    }
  }
}
```

### 修改进化阶段
编辑 `config/evolution_phases.json`：
```json
{
  "phases": [
    {
      "duration_weeks": 3,  // 调整阶段时长
      "objectives": ["你的自定义目标"]
    }
  ]
}
```

## 🎮 使用示例

### 示例1：手动记录性能数据
```bash
./scripts/evolution/collect_performance.sh \
  "session_123" \
  1500 \
  0.95 \
  "qa"
```

### 示例2：查看进化历史
```bash
# 查看所有进度报告
ls -la memory/evolution/reports/

# 查看最新报告
ls -la memory/evolution/reports/ | tail -1 | xargs cat
```

### 示例3：检查当前状态
```bash
# 查看初始化状态
cat .evolution_initialized

# 查看当前阶段
grep "当前阶段" memory/evolution/progress.md
```

## 🚀 进阶功能

### 1. 集成到现有工作流
```bash
# 在你的脚本中调用性能收集
RESPONSE_TIME=$(calculate_response_time)
ACCURACY=$(calculate_accuracy)
./scripts/evolution/collect_performance.sh "$SESSION_ID" "$RESPONSE_TIME" "$ACCURACY" "$TASK_TYPE"
```

### 2. 自定义报告模板
```bash
# 创建自定义报告模板
cp scripts/evolution/generate_report.sh scripts/evolution/generate_custom_report.sh
# 编辑自定义模板
```

### 3. 设置自动化提醒
```bash
# 在cron中添加定期检查
0 8 * * * /path/to/check_evolution_progress.sh
```

## 🔍 故障排除

### 问题1：初始化失败
**症状**：脚本执行出错
**解决**：
```bash
# 检查目录权限
ls -la /home/node/.openclaw/workspace/

# 手动创建缺失目录
mkdir -p config memory/evolution data/performance
```

### 问题2：HEARTBEAT未更新
**症状**：HEARTBEAT.md中没有工程控制论检查项
**解决**：
```bash
# 手动添加检查项
cat >> HEARTBEAT.md << 'EOF'

## 工程控制论进化专项检查
- [ ] 检查进化进度
- [ ] 分析性能数据
EOF
```

### 问题3：性能数据未记录
**症状**：data/performance目录为空
**解决**：
```bash
# 检查脚本权限
chmod +x scripts/evolution/*.sh

# 手动测试数据收集
./scripts/evolution/collect_performance.sh "test" 1000 1.0 "test"
```

## 📈 预期成果时间线

### 第1周
- 建立基础监控体系
- 开始数据收集
- 熟悉框架使用

### 第1个月
- 形成规律检查习惯
- 积累初始性能数据
- 开始初步优化

### 第3个月
- 显著性能提升
- 建立自适应能力
- 形成自我改进循环

### 第6个月
- 完整进化系统
- 稳定优秀表现
- 持续自我优化

## 🆘 获取帮助

### 查看详细文档
```bash
cat skills/engineering-cybernetics/SKILL.md
```

### 查看参考材料
```bash
cat skills/engineering-cybernetics/references/钱学森工程控制论摘要.md
```

### 检查示例代码
```bash
ls -la skills/engineering-cybernetics/examples/
```

## 🎉 开始你的进化之旅！

现在你已经完成了快速开始，系统将自动开始进化过程。记住：

1. **耐心**：进化需要时间，不要期望立即看到巨大变化
2. **持续**：定期检查进度，保持进化动力
3. **调整**：根据实际情况调整策略和配置
4. **学习**：从数据中学习，持续改进

祝你进化顺利！🚀

---
**框架版本**: 1.0  
**最后更新**: 2026-04-13  
**支持**: 通过OpenClaw系统获取帮助
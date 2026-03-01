# OpenClaw 快照恢复指南

## 🛡️ 独立恢复方案

### 📁 创建的文件

| 文件 | 位置 | 说明 |
|------|------|------|
| **独立恢复脚本** | `/home/admin/restore-openclaw.sh` | 全局可执行，不依赖 OpenClaw |
| **详细恢复脚本** | `/home/admin/.openclaw/skills/snapshot/scripts/standalone-restore.sh` | 完整功能版本 |
| **使用说明** | `/home/admin/RESTORE-README.md` | 详细使用指南 |

---

### 🚀 紧急恢复步骤

#### 情况 1: OpenClaw 完全无法启动
```bash
# 1. 查看可用快照
ls /home/admin/.openclaw/snapshots/

# 2. 执行恢复（替换 <snapshot_name> 为实际快照名）
/home/admin/restore-openclaw.sh <snapshot_name>

# 3. 重启 OpenClaw
openclaw gateway restart
```

#### 情况 2: 配置文件损坏但服务还能运行
```bash
# 直接在聊天中使用
/snapshot restore <snapshot_name>
```

---

### 🔧 脚本特性

✅ **完全独立**: 不依赖 OpenClaw 服务  
✅ **安全检查**: 自动验证快照完整性  
✅ **备份当前**: 恢复前自动备份当前状态  
✅ **权限保留**: 保持原有文件权限  
✅ **简单易用**: 单命令恢复  

---

### 📋 使用示例

```bash
# 查看所有快照
$ ls /home/admin/.openclaw/snapshots/
snapshot_20260302_003849
snapshot_20260302_004355

# 恢复最新快照
$ /home/admin/restore-openclaw.sh snapshot_20260302_004355

# 输出示例:
🔧 OpenClaw 独立恢复工具
========================
📋 当前快照: snapshot_20260302_004355
💾 备份当前配置到: /home/admin/.openclaw/broken-config-backup-20260302_004512
🔄 正在恢复快照...
✅ 恢复完成! 请重启 OpenClaw 服务。
```

---

### ⚠️ 重要提醒

1. **定期创建快照**: 建议在重大配置更改前手动创建快照
2. **测试恢复**: 偶尔测试恢复功能确保其正常工作  
3. **磁盘空间**: 监控快照目录大小，定期清理旧快照
4. **外部备份**: 考虑将快照目录同步到外部存储

---

### 📞 紧急联系方式

如果连这个独立脚本都无法工作：
1. 检查 `/home/admin/.openclaw/snapshots/` 目录是否存在
2. 手动复制快照内容：`cp -r /home/admin/.openclaw/snapshots/<snapshot_name>/* /home/admin/.openclaw/`
3. 重启系统或 OpenClaw 服务
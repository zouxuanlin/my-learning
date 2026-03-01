# Rust 常用 Crate 推荐

> 精选高质量、维护良好的 Rust 库

---

## 📦 必备工具库

### 错误处理
| Crate | 用途 | 版本 |
|-------|------|------|
| `anyhow` | 应用层错误处理 | 1.x |
| `thiserror` | 库层错误定义 | 1.x |
| `color-eyre` | 美观的错误报告 | 0.6 |

```toml
[dependencies]
anyhow = "1.0"
thiserror = "1.0"
```

### 序列化
| Crate | 用途 |
|-------|------|
| `serde` | 序列化框架 |
| `serde_json` | JSON 支持 |
| `serde_yaml` | YAML 支持 |
| `toml` | TOML 支持 |

```toml
[dependencies]
serde = { version = "1.0", features = ["derive"] }
serde_json = "1.0"
```

---

## 🌐 网络与 Web

### HTTP 客户端
| Crate | 特点 |
|-------|------|
| `reqwest` | 功能完整，支持 async |
| `ureq` | 轻量级，同步 |

### Web 框架
| Crate | 类型 | 适合场景 |
|-------|------|----------|
| `axum` | Async | 现代 Web 应用 (推荐) |
| `actix-web` | Async | 高性能 Web 服务 |
| `warp` | Async | 轻量级 API |
| `rocket` | Async | 快速开发 |

### 异步运行时
| Crate | 说明 |
|-------|------|
| `tokio` | 最流行的 async 运行时 |
| `async-std` | 标准库风格的 async |

```toml
[dependencies]
tokio = { version = "1", features = ["full"] }
axum = "0.7"
reqwest = { version = "0.11", features = ["json"] }
```

---

## 💾 数据库

### ORM
| Crate | 说明 |
|-------|------|
| `sqlx` | 编译时检查 SQL (推荐) |
| `diesel` | 类型安全的 ORM |
| `sea-orm` | 异步 ORM |

### 数据库驱动
| Crate | 数据库 |
|-------|--------|
| `postgres` | PostgreSQL |
| `mysql_async` | MySQL |
| `mongodb` | MongoDB |
| `redis` | Redis |

```toml
[dependencies]
sqlx = { version = "0.7", features = ["runtime-tokio-rustls", "postgres"] }
```

---

## 🔧 开发工具

### 日志
| Crate | 用途 |
|-------|------|
| `tracing` | 结构化日志 (推荐) |
| `log` + `env_logger` | 传统日志 |
| `pretty_env_logger` | 美观的日志输出 |

### 配置管理
| Crate | 用途 |
|-------|------|
| `config` | 多格式配置加载 |
| `dotenv` | .env 文件支持 |

### 命令行
| Crate | 用途 |
|-------|------|
| `clap` | 命令行参数解析 (推荐) |
| `dialoguer` | 交互式 CLI |
| `indicatif` | 进度条 |

```toml
[dependencies]
tracing = "0.1"
tracing-subscriber = "0.3"
clap = { version = "4", features = ["derive"] }
```

---

## 🧪 测试

| Crate | 用途 |
|-------|------|
| `cargo-test` | 内置测试框架 |
| `mockall` | Mock 生成 |
| `proptest` | 属性测试 |
| `criterion` | 性能基准测试 |

```toml
[dev-dependencies]
mockall = "0.12"
criterion = "0.5"
```

---

## 🎮 游戏开发

| Crate | 用途 |
|-------|------|
| `bevy` | 游戏引擎 (推荐) |
| `macroquad` | 轻量级 2D 游戏 |
| `ggez` | 2D 游戏框架 |

---

## 📊 数据处理

| Crate | 用途 |
|-------|------|
| `itertools` | 迭代器扩展 |
| `rayon` | 并行迭代器 |
| `serde_json` | JSON 处理 |
| `csv` | CSV 文件处理 |
| `regex` | 正则表达式 |

---

## 🔐 安全与加密

| Crate | 用途 |
|-------|------|
| `ring` | 加密原语 |
| `rustls` | TLS 实现 |
| `argon2` | 密码哈希 |
| `jwt` | JWT 令牌 |

---

## 📁 文件系统

| Crate | 用途 |
|-------|------|
| `walkdir` | 目录遍历 |
| `tempfile` | 临时文件 |
| `notify` | 文件监控 |
| `fs_extra` | 文件操作扩展 |

---

## 🎯 精选项目模板

### Web API 模板
```toml
[dependencies]
axum = "0.7"
tokio = { version = "1", features = ["full"] }
serde = { version = "1.0", features = ["derive"] }
serde_json = "1.0"
sqlx = { version = "0.7", features = ["runtime-tokio-rustls", "postgres"] }
tracing = "0.1"
tracing-subscriber = "0.3"
```

### CLI 工具模板
```toml
[dependencies]
clap = { version = "4", features = ["derive"] }
anyhow = "1.0"
tokio = { version = "1", features = ["full"] }
reqwest = { version = "0.11", features = ["json"] }
```

---

## 🔍 查找 Crate

- **crates.io**: https://crates.io/
- **lib.rs**: https://lib.rs/ (更好的搜索体验)
- **arewewebyet**: https://www.arewewebyet.org/ (Web 开发生态)
- **areweguiyet**: https://areweguiyet.com/ (GUI 生态)

---

## 💡 选择 Crate 的建议

1. **查看下载量**: 高下载量通常意味着更稳定
2. **检查维护状态**: 最近是否有更新
3. **阅读文档**: 文档质量反映项目质量
4. **查看 issue**: 了解已知问题
5. **优先选择 1.0+**: 语义化版本保证稳定性

---

**最后更新**: 2025 年

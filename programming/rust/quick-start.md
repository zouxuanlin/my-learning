# Rust 快速入门指南

## 🚀 安装 Rust

### Linux/macOS
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

### Windows
访问 https://rustup.rs/ 下载安装程序

### 验证安装
```bash
rustc --version
cargo --version
```

---

## 📦 第一个 Rust 程序

### 创建项目
```bash
cargo new hello_rust
cd hello_rust
```

### 编辑 src/main.rs
```rust
fn main() {
    println!("Hello, Rust!");
}
```

### 运行
```bash
cargo run
```

---

## 🔑 核心概念速查

### 变量与可变性
```rust
let x = 5;          // 不可变
let mut y = 10;     // 可变
y = 15;
```

### 所有权 (Ownership)
```rust
let s1 = String::from("hello");
let s2 = s1;        // 所有权转移，s1 不再有效
```

### 借用 (Borrowing)
```rust
fn print(s: &String) {  // 借用，不转移所有权
    println!("{}", s);
}
```

### 结构体
```rust
struct User {
    username: String,
    email: String,
    active: bool,
}
```

### 枚举与模式匹配
```rust
enum Message {
    Quit,
    Move { x: i32, y: i32 },
    Write(String),
}

match message {
    Message::Quit => println!("Quit"),
    Message::Move { x, y } => println!("Move to ({}, {})", x, y),
    Message::Write(text) => println!("Text: {}", text),
}
```

---

## 🛠️ 常用 Cargo 命令

| 命令 | 说明 |
|------|------|
| `cargo new <name>` | 创建新项目 |
| `cargo build` | 编译项目 |
| `cargo run` | 编译并运行 |
| `cargo test` | 运行测试 |
| `cargo check` | 快速检查错误 |
| `cargo fmt` | 格式化代码 |
| `cargo clippy` | 代码检查 (需安装) |
| `cargo add <crate>` | 添加依赖 |

---

## 📚 推荐学习顺序

1. **第 1 天**: 安装 Rust，运行 Hello World
2. **第 2-3 天**: 学习变量、函数、控制流
3. **第 4-7 天**: 理解所有权和借用 (重点!)
4. **第 2 周**: 结构体、枚举、模式匹配
5. **第 3 周**: 错误处理、泛型、trait
6. **第 4 周**: 完成 Rustlings 全部练习

---

## ⚠️ 常见错误

### 借用检查错误
```
error[E0502]: cannot borrow `x` as mutable because it is also borrowed as immutable
```
**解决**: 确保同一时间只有一个可变借用或多个不可变借用

### 生命周期错误
```
error[E0106]: missing lifetime specifier
```
**解决**: 添加生命周期注解，或重构代码避免引用

---

## 🔗 下一步

完成本指南后，前往 [README.md](./README.md) 查看完整学习路线。

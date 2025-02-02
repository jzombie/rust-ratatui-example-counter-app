# Rust Ratatui Example Counter App 
A simple **terminal-based counter app** built using [Ratatui](https://ratatui.rs/), based on the [official tutorial](https://ratatui.rs/tutorials/counter-app/), with added **wrapping arithmetic** to prevent crashes from overflow.

## **Installation**
### **Prerequisites**
Ensure you have **Rust and Cargo** installed. If not, install Rust via [rustup](https://rustup.rs/):
```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

### **Clone the Repository**
```sh
git clone https://github.com/jzombie/rust-ratatui-example-counter-app.git
cd rust-ratatui-example-counter-app
```

### **Build & Run**
```sh
cargo run
```

---

## **Usage**
### **Keyboard Controls**
- **Up (`↑`) / `+`** → Increment the counter  
- **Down (`↓`) / `-`** → Decrement the counter  
- **`q`** → Quit the application  

The counter **wraps around** when reaching the max/min value of its type (e.g., `i32::MAX` → wraps to `i32::MIN`).

---

## **Code Overview**
The core functionality lies in **incrementing and decrementing** safely using **wrapping arithmetic**:

```rust
impl Counter {
    fn increment(&mut self) {
        self.value = self.value.wrapping_add(1);
    }

    fn decrement(&mut self) {
        self.value = self.value.wrapping_sub(1);
    }
}
```
🚀 This ensures the app **never crashes** from integer overflows.

---

## **Example Output**
When running the app, you'll see a **live counter** updating in your terminal:
```
╔════════════════════════╗
║     Rust Ratatui App   ║
║                        ║
║        Counter: 5      ║
║                        ║
║  ↑ or +  → Increment   ║
║  ↓ or -  → Decrement   ║
║   q  → Quit            ║
╚════════════════════════╝
```

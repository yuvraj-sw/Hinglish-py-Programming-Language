# 🚀 HinglishPy — Apni Bhasha Mein Code Karo

An interactive, browser-based development environment and source-to-source transpiler that compiles Hinglish source code into standard, clean Python logic in real-time. Powered by WebAssembly, it executes full Python programs directly within the client browser sandbox—no backend cloud server required.

🌐 **Live Demo:** https://yuvraj-sw.github.io/Hinglish-py-Programming-Language/

---

## 💡 Features

- **Custom Lexical Mapping:** Translates intuitive Hinglish vocabulary keywords (`agar`, `warna`, `jabtak`, `chaap`) directly into exact Python runtime tokens.
- **Asynchronous WebAssembly Runtime:** Integrates **Pyodide** (WASM Python interpreter) to compile and run scripts natively inside the browser client sandbox.
- **Custom-Built Code Editor UI:** Features a high-performance input layout that layers a transparent input field over a synchronized background text panel for real-time compilation and typing.
- **Custom Syntax Highlighting Engine:** Uses token-aware regular expression patterns to dynamically detect, differentiate, and color control paths, data literals, function architectures, strings, and code comments.
- **Polished UX & Brand Identity:** Built with a clean, high-contrast pitch-black theme, integrated interactive sample structures, and a smooth animated introductory splash engine.

---

## 📑 Shabd-Kosh (Keyword Reference Matrix)

| Hinglish Keyword | Python Equivalent | Logical Type |
| :--- | :--- | :--- |
| `agar` | `if` | Control Flow |
| `warna_agar` | `elif` | Control Flow |
| `warna` | `else` | Control Flow |
| `jabtak` | `while` | Loops & Jumps |
| `ke_liye` | `for` | Loops & Jumps |
| `mein` | `in` | Membership Operators |
| `todo` | `break` | Loops & Jumps |
| `jaari` | `continue` | Loops & Jumps |
| `kaam` | `def` | Definitions & Structure |
| `wapas` | `return` | Definitions & Structure |
| `chaap` | `print` | Core I/O Stream |
| `sahi` | `True` | Boolean Literals |
| `galat` | `False` | Boolean Literals |
| `khaali` | `None` | Null Types |
| `koshish` / `pakdo` | `try` / `except` | Exception Controls |

---

## 🛠️ Deep-Dive Under the Hood

### 1. Tokenizer-Aware AST Preservation
To prevent string constants or structural comments from being broken by translation swaps, the compiler uses a dedicated regex mapping structure (`TOKEN_RE`) to explicitly identify strings and comments:

```javascript
const TOKEN_RE = /(#.*$)|('(?:\\.|[^'\\])*')|("(?:\\.|[^"\\])*")|\b[A-Za-z_][A-Za-z0-9_]*\b/gm;

# 🚀 JavaScript Interview Prep Notes 📜

## ✅ Topics Covered So Far

### 1️⃣ **🖥️ Variable Declarations**
- `var` ➡️ 🏠 Function-scoped, 🚀 hoisted with `undefined`, 🔄 mutable.
- `let` ➡️ 🏗️ Block-scoped, 🚀 hoisted (but in ⏳ TDZ), 🔄 mutable.
- `const` ➡️ 🏗️ Block-scoped, 🚀 hoisted (but in ⏳ TDZ), ❌ immutable.

### 2️⃣ **🎢 Hoisting & Scope**
- Variables with `var` ⏫ hoisted & initialized with `undefined`.
- `let` & `const` ⏫ hoisted but stay in ⏳ **Temporal Dead Zone (TDZ)** until assigned.
- Functions ⏫ hoisted entirely, meaning they can be called 📞 before their declaration.

### 3️⃣ **🔄 Closures & Function Execution**
- 📦 Inner functions keep access 🔑 to their outer function’s variables even after returning.
- **Example:**
  ```javascript
  function outer() {
      let count = 0;
      return function inner() {
          count++;
          console.log(count);
      };
  }
  const increment = outer();
  increment(); // 1️⃣
  increment(); // 2️⃣
  ```

### 4️⃣ **🔁 Event Loop & Concurrency**
#### **🛠️ Execution Order**
1️⃣ Synchronous Code 🏃
2️⃣ Microtasks Queue (`Promise.then`, `queueMicrotask`) 🔬
3️⃣ Macrotasks Queue (`setTimeout`, `setInterval`, `setImmediate`, I/O) ⏳

#### **📌 Example Execution Order:**
```javascript
console.log("Start");
setTimeout(() => console.log("Timeout"), 0);
Promise.resolve().then(() => console.log("Promise"));
console.log("End");
```
**📝 Output:**
```
Start ✅
End ✅
Promise ⚡
Timeout ⏳
```

### 5️⃣ **🖇️ Function Binding & `this` Keyword**
- `this` behaves 🕵️ differently based on function types:
  - **🔄 Regular functions** ➡️ `this` depends on **how** the function is called.
  - **🏹 Arrow functions** ➡️ `this` is inherited 📍 from surrounding scope.
- **Example:**
  ```javascript
  const obj = {
    name: "Aashish",
    logName: function() { console.log(this.name); },
    delayedLog: function() {
      setTimeout(() => console.log(this.name), 1000);
    }
  };
  obj.logName();     // Aashish ✅
  obj.delayedLog();  // Aashish (arrow function captures `this` from `obj`) ✅
  ```

### 6️⃣ **🔍 MutationObserver & Microtasks**
- **MutationObserver** 👀 watches for **DOM changes** & runs as a 🔬 **microtask**.
- **Example:**
  ```javascript
  const observer = new MutationObserver(() => {
      console.log("Mutation detected");
  });
  observer.observe(document.body, { childList: true });
  document.body.appendChild(document.createElement("div"));
  ```

### 7️⃣ **📂 I/O Operations & Node.js Event Loop**
- **📡 I/O Operations** (`fs.readFile`) are **macrotasks** ⏳ but depend on OS scheduling.
- **Example:**
  ```javascript
  const fs = require("fs");
  fs.readFile("test.txt", "utf8", () => console.log("File read"));
  console.log("Sync Code");
  setTimeout(() => console.log("Timeout"), 0);
  Promise.resolve().then(() => console.log("Promise"));
  ```
  **📝 Output:**
  ```
  Sync Code ✅
  Promise ⚡
  Timeout ⏳
  File read 📂
  ```

---

## 📌 Topics Left To Cover 📝
### ✅ **📚 Deep Dive Topics:**
- 🔄 Callbacks vs Promises vs Async/Await
- 🌀 Generator Functions (`function*`) & Iterators
- 🏛️ Prototypes & Prototype Chain
- 🎤 Event Delegation & Bubbling/Capturing
- ⚡ Performance Optimization Techniques
- 🧠 JavaScript Memory Management (Garbage Collection)

### ✅ **🚀 Advanced JavaScript Concepts:**
- 🛠️ Polyfills & Shims
- 🏗️ Web Workers & Multithreading in JS
- 🧩 WeakMap & WeakSet
- 🔣 Symbol & Well-Known Symbols
- 🛡️ `Reflect` & `Proxy` API

### ✅ **💡 System Design & JS Architecture:**
- 🏗️ Designing Scalable Frontend Apps
- 🎯 Monorepos & Microservices with JavaScript
- 📡 WebSockets & Real-Time Communication
- 🌐 Service Workers & PWA
- 🔄 SSR vs CSR vs SSG

---

### 🔥 **Next Steps:**
- ✏️ Keep appending new topics here as we discuss them.
- 📖 Revise key areas where you're less confident.
- 🤹 Practice coding challenges & mock interview questions.

🚀 **You're doing great! Ready for the next deep dive?** 😈


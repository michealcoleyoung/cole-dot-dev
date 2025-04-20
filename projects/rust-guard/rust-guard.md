Rust Guard is a password manager built in rust. The below requirements were generated using ChatGPT.

### Original Prompt
I'm in the process of learning Rust and I was thinking about building a CLI password manager. Would you be able to provide some project requirements, file structure and maybe recommend a Rust library that would allow me to turn my terminal into a UI for the user?

---

## 🚧 Project Requirements

Here’s a breakdown of what your password manager should ideally support:

### 🎯 Core Features

-  Create a new password entry
    
-  List saved password entries
    
-  View details of an entry (e.g., site, username, password)
    
-  Edit existing entries
    
-  Delete entries
    
-  Search entries by name or tag
    
-  Encrypt/decrypt entries securely
    
-  Master password to unlock vault
    
-  Save data to local file securely (e.g., JSON or binary format)
    

### 🔐 Security Considerations

- Use strong encryption (e.g., AES-256) to encrypt stored passwords
    
- Use a key derived from the master password using a password-based key derivation function (e.g., PBKDF2, Argon2)
    
- Hash and salt the master password for verification
    

---

## 🧱 Suggested File Structure

```bash
password-manager/
├── Cargo.toml
└── src/
    ├── main.rs         # Entry point, UI logic
    ├── ui.rs           # Terminal UI logic
    ├── commands.rs     # Handle CLI commands
    ├── crypto.rs       # Encryption/decryption
    ├── storage.rs      # Load/save encrypted data
    ├── models.rs       # Data structures (e.g., Entry, Vault)
    └── utils.rs        # Helpers (e.g., input validation, key derivation)
```

You can break this down even further as the project grows, but this should keep things nicely modular.

---

## 📚 Recommended Libraries

### 🧰 Core Tools

|Purpose|Library|Notes|
|---|---|---|
|Encryption|[`aes-gcm`](https://crates.io/crates/aes-gcm), [`argon2`](https://crates.io/crates/argon2), [`pbkdf2`](https://crates.io/crates/pbkdf2)|For secure encryption and password-based key derivation|
|Data Storage|[`serde`](https://crates.io/crates/serde), [`serde_json`](https://crates.io/crates/serde_json) or [`bincode`](https://crates.io/crates/bincode)|For serialization|
|File I/O|Built-in `std::fs`|To read/write to disk|

### 💻 Terminal UI

|Purpose|Library|Notes|
|---|---|---|
|Terminal UI|[`ratatui`](https://crates.io/crates/ratatui) (formerly `tui`)|Create interactive terminal UIs|
|Input Handling|[`crossterm`](https://crates.io/crates/crossterm)|Works well with `ratatui` for terminal input/output|
|Alternatively|[`inquire`](https://crates.io/crates/inquire) or [`dialoguer`](https://crates.io/crates/dialoguer)|For simple prompt-based UIs|

---

## 🔧 Development Phases

1. **MVP Without UI**
    
    - Basic command-line functionality
        
    - Read input using `std::io`, encrypt it, and write to disk
        
    - Load from disk, decrypt, and print to terminal
        
2. **Add Terminal UI**
    
    - Replace or supplement the basic input/output with a `ratatui`-powered interface
        
    - Display a list of entries, support key navigation, and provide interactive prompts
        
3. **Security Polish**
    
    - Add proper key derivation with Argon2 or PBKDF2
        
    - Master password prompt and vault unlocking
        
    - Protect against common attacks (e.g., timing attacks, storing plaintext)
        

---



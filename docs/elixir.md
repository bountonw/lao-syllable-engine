# Elixir Linting & Formatting

This project uses `mix format` and [`credo`](https://github.com/rrrene/credo) to
enforce consistent Elixir style and catch potential issues before merging to
`main`.

---

## 🛠 Tools Used

| Tool           | Purpose                  |
|----------------|---------------------------|
| `mix format`   | Automatic code formatting |
| `credo`        | Static analysis and style guide enforcement |

---

## 🚀 Setup (Local)

1. **Install Elixir** (if not already):

   On macOS with Homebrew:
   ```bash
   brew install elixir
````

On Ubuntu/Debian:

```bash
sudo apt install elixir
```

2. **Install dependencies**:

   From the project root:

   ```bash
   cd elixir
   mix deps.get
   ```

3. *(Optional)* Generate a `.credo.exs` file:

   ```bash
   mix credo gen.config
   ```

---

## ✅ How to Run Checks

* **Format check**:

  ```bash
  mix format --check-formatted
  ```

* **Lint check (strict)**:

  ```bash
  mix credo --strict
  ```

---

## 🧪 GitHub Actions Integration

The file `.github/workflows/elixir-lint.yml`:

* Runs on every PR targeting `main`
* Fails the build if `credo` finds issues
* Uses caching for faster installs

Make sure to commit changes to:

* `mix.lock`
* `.credo.exs` (if edited)
* `mix.exs` (if adding new checks)

---

## 💡 CI Blocking Rules

The following `credo` checks **will block merging** if triggered:

* `TagTODO`
* `TagFIXME`

The following checks **warn only**:

* `MaxLineLength`
* `DuplicatedCode`
* `CyclomaticComplexity`
* `Nested conditionals`

---

## 📄 Configuration Files

| File              | Purpose                        |
| ----------------- | ------------------------------ |
| `mix.exs`         | Includes `credo` as a dev dep  |
| `.credo.exs`      | Custom lint rule configuration |
| `elixir-lint.yml` | GitHub Actions workflow        |

---

## 📌 Notes

* Code formatting is auto-fixable with `mix format`
* Linting must be resolved manually
* CI will block merging if checks fail

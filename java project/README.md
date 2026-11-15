# Smart Expense Tracker

A modern Java Swing desktop application designed for tracking personal finances and managing group expenses securely under a robust SQLite backend. The application features dynamic real-time reporting, full CRUD capabilities for incomes and expenses, analytical charts, a customizable light/dark mode palette, and extensive user-to-user networking for splitting bills efficiently.

## Features

- **Authentication System:** Securely store and retrieve individual user data.
- **Dashboard Overview:** Glancing aggregate totals for active month spending and net bank balances.
- **Transaction Logs:** Beautifully designed JTables featuring dynamic hover states and quick filtering columns for all global expenses and localized incomes.
- **Graphical Analytics:** Pure native Java 2D implementation drawing out your financial history bar-charts chronologically.
- **SplitSphere Network:** Construct independent groups across local users, register total shared expenditures, and let internal calculators map out who owes exactly how much instantly.
- **Theme Engine:** Clean dynamic switching between Light and Dark mode styling without sacrificing custom Swing layouts.

---

## Technical Stack
- Java 17+ (Native execution)
- Maven (`pom.xml` provided but entirely optional for quick batch scripts)
- SQLite (Local `expense_tracker.db` database)

## Quick Start (Batch Scripts)

You can launch and build the application cleanly using the automated helper scripts provided in the root directory.

### Compiling
Run `build.bat` in your terminal or simply double click it.
```bash
> build.bat
```
*(This automatically constructs an `/out` directory, binds libraries from `/lib`, and compiles the `.java` src)*

### Running
Run `run.bat` right after compilation.
```bash
> run.bat
```

### Self-Diagnostic Tests
If you want to verify the database bindings and math modules, execute `test.bat`. Note: do not run this if your app is open.
```bash
> test.bat
```

---

## Future Enhancements
- Export options (PDF/CSV) to push local financial tables into external analytics programs.
- Configurable settings mapping for personalized local storage limits.
- Advanced date filtering tools.

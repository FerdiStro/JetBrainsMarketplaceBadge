# JetBrains Plugin Badge

This project allows you to generate your own **JetBrains Plugin Badge** for your JetBrains plugin. The badge is
automatically generated using Rust and updated daily via GitHub Actions.

---

## 🚀 Features

* Automatic badge generation using Rust
* Daily updates using a scheduled GitHub Actions workflow
* Simple configuration via environment variables
* Badge can be embedded in any README via GitHub raw URL

---

## 📦Local requirements

To build locally, you need:

* Rust (including `cargo`)
* Environment variable `MARKETPLACE_ID` set to your JetBrains Marketplace plugin ID

### Set local environment variables

```bash
export MARKETPLACE_ID="your-plugin-id"
```

Optional debug logging:

```bash
export DEBUG="debug"
```

### Local build

```bash
cargo build --release
```

The generated badge will appear inside the output directory.

---

## ⚙️ GitHub Actions

A GitHub Actions workflow is automatically set up when you fork this repository.

### Adjust the cron schedule

If you want to change the update interval, edit the cron expression in `.github/workflows/main.yml`.

Default:

```yaml
cron: "30 0 * * *"
```

You can set any valid cron schedule you prefer.

---

## 🏷️ Embed the Badge

Once generated, include the badge in your README:

![Plugin Badge](https://raw.githubusercontent.com/KyberFlow/JetBrainsMarketplaceBadge/main/intellij_marketplace_badge.svg)

```markdown
Example above: [Plugin Badge](https://raw.githubusercontent.com/KyberFlow/JetBrainsMarketplaceBadge/main/intellij_marketplace_badge.svg)
Your URL: [Plugin Badge](https://raw.githubusercontent.com/<USER>/<REPO>/main/intellij_marketplace_badge.svg)
```

---

## 🔐 Pipeline Variables

| Variable         | Description                               | Default |
|------------------|-------------------------------------------|---------|
| `MARKETPLACE_ID` | Marketplace ID of your JetBrains plugin   | none    |
| `DEBUG`          | Rust log level (`debug`, `info`, `trace`) | debug   |

---

## 📄 License

MIT License — feel free to use, modify, and distribute.

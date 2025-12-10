# LocalGov Drupal - Lando Bootstrap

[![Use this template](https://img.shields.io/badge/Use%20this%20template-2ea44f?style=for-the-badge)](https://github.com/jamesfmcgrath/localgov-lando/generate)

Bootstrap a new LocalGov Drupal project with Lando in seconds.

## 🚀 Quick Start

### Option 1: Use Template (Recommended)

1. Click **"Use this template"** button above
2. Create your new repository
3. Clone your new repository locally
4. Run `lando start`
5. Run `lando init-project`
6. Run `lando rebuild -y`

### Option 2: Manual Clone

```bash
git clone https://github.com/jamesfmcgrath/localgov-lando.git my-project
cd my-project
rm -rf .git  # Remove git history
git init     # Start fresh
lando start
lando init-project
lando rebuild -y
```

## ⚠️ Important

**This is a bootstrap repository.** After running `lando init-project`:

- `.lando.yml` is renamed to `.lando.bootstrap.yml`
- LocalGov's own `.lando.dist.yml` takes over
- You can safely delete `.lando.bootstrap.yml` and `LANDO.md`

## 📝 What Happens

1. Downloads LocalGov Drupal via Composer
2. Renames bootstrap files to avoid conflicts
3. Sets up your project structure
4. Hands off to LocalGov's configuration

## 🔧 Requirements

- [Lando](https://lando.dev/) installed
- Docker running
- Composer (provided by Lando)

## 📚 Resources

- [LocalGov Drupal](https://localgovdrupal.org/)
- [Lando Documentation](https://docs.lando.dev/)

---

**Note:** This template automatically configures itself and steps aside for the LocalGov project structure.

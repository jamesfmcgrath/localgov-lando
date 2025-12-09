# LocalGov Drupal with Lando Starter

A starter repository for LocalGov Drupal that requires **only Lando** - no Composer or PHP needed on your host machine.

## Prerequisites

- [Lando](https://lando.dev/) installed
- **No Composer or PHP required!**

## Installation

### Step 1: Clone this repository

```bash
git clone https://github.com/your-org/localgov-lando.git localgov
cd localgov
```

### Step 2: Start Lando with bootstrap configuration

```bash
lando start
```

### Step 3: Initialize the LocalGov Drupal project

```bash
lando init-project
```

This downloads all LocalGov Drupal files and removes the bootstrap configuration.

### Step 4: Rebuild with full LocalGov configuration

IMPORTANT: `.lando.dist.yml` PHP version must be updated to 8.3 for this install to work. Otherwise you will get a 500 error for APPSERVER URLS.

```bash
lando rebuild -y
```

Lando automatically uses `.lando.dist.yml` from the downloaded project.

To avoid conflicts `.lando.yml` is renamed to `.lando.bootstrap.yml` and README.md to LANDO.md. These files can be deleted after successful setup.

### Step 5: Install Drupal

```bash
lando drush si localgov -y
```

### Step 6: Access your site

```bash
lando info
```

Your site will be at: https://localgov.lndo.site

## How It Works

1. **Bootstrap phase** - Uses minimal `.lando.yml` to get PHP/Composer
2. **Download phase** - `lando init-project` downloads LocalGov Drupal (includes `.lando.dist.yml`)
3. **Production phase** - Lando automatically uses `.lando.dist.yml` for full configuration

**No manual copying required!** Lando reads `.lando.dist.yml` automatically when `.lando.yml` doesn't exist.

## What You Get

Your environment includes:

- **Drupal 10** with LocalGov Drupal distribution
- **Solr 8** for search (http://solr-sitewide.localgov.lndo.site:8983)
- **MailHog** for email testing (https://mail.localgov-learning.lndo.site)
- **Adminer** for database management (https://adminer.localgov-learning.lndo.site)
- **ChromeDriver** for automated testing
- **Node.js 20** for frontend tooling
- **Xdebug** for debugging (disabled by default)

## Daily Development

### Composer Commands

```bash
lando composer require drupal/admin_toolbar
lando composer update
```

### Drush Commands

```bash
lando drush cr                    # Clear cache
lando drush uli                   # Get login link
lando drush cex -y                # Export configuration
```

### Code Quality Tools

```bash
lando phpcs                       # PHP CodeSniffer
lando phix                        # Auto-fix coding standards
lando phpstan                     # Static analysis
lando sca                         # Full static code analysis
lando phpunit                     # Run PHPUnit tests
```

### Frontend Tools

```bash
lando install-frontend            # Install frontend dependencies
lando eslint-js path/to/file.js   # Lint JavaScript
lando stylelint path/to/file.css  # Lint CSS
```

### Debugging

```bash
lando xdebug-on                   # Enable Xdebug
lando xdebug-off                  # Disable Xdebug
```

## Troubleshooting

### "I don't have Composer installed"

✅ Perfect! Use `lando composer` for all Composer commands.

## Learn More

- [LocalGov Drupal Documentation](https://docs.localgovdrupal.org/)
- [Lando Documentation](https://docs.lando.dev/)

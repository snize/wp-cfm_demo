## Configraton Management for Wordpress with WP-CFM Demo

* [Lando](https://docs.devwithlando.io/) - Docker based **local** development environment.
  * [System Requirements · Lando Documentation](https://docs.devwithlando.io/installation/system-requirements.html)
* [Bedrock | WordPress Boilerplate | Roots](https://roots.io/bedrock/) - Composer based WordPress.
* [WP-CFM | WordPress.org](https://ja.wordpress.org/plugins/wp-cfm/) - Plugin for configuration management.

### Getting started

```bash
git clone git@github.com:snize/wp-cfm_demo.git
cd wp-cfm_demo
```

### Initialize local machine with lando

```bash
# lando init
cp .env.example .env
lando start
# Run composer in Lando.
lando composer install
```
### Setup WordPress with wp-cli
```bash
# Install WordPress with WP-CLI.
lando wp core install \
--url=wp-cfm-demo.lndo.site \
--title="WP-CFM Demo" \
--admin_user=demo \
--admin_password=demo \
--admin_email=info@example.com

# Activate WP-CFM plugin.
lando wp plugin activate wp-cfm

# Pull default config into Wordpress.
lando wp config pull default
```

### For demo

```bash
# Open admin page.
# id/pw demo
open http://wp-cfm-demo.lndo.site/wp/wp-admin

# Generate posts for demo.
lando wp post generate --count=9

# Remove all untracked files and directories.
git clean -fdx
```


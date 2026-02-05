---
allowed-tools: Bash(php-cs-fixer:*), Bash(vendor/bin/php-cs-fixer:*), Bash(composer:*)
description: Check PHP code formatting with php-cs-fixer
---

## Context

- Current directory: !`pwd`
- PHP version: !`php -v | head -n 1`
- Check if php-cs-fixer is installed: !`which php-cs-fixer || echo "Not in PATH, checking vendor/bin..."`

## Your task

Check that PHP code matches the formatting standards using php-cs-fixer.

1. First, check if php-cs-fixer is available:
   - Check for `vendor/bin/php-cs-fixer` (local installation)
   - Check for global `php-cs-fixer` installation
   - If not found, suggest installing it with: `composer require --dev friendsofphp/php-cs-fixer`

2. Run php-cs-fixer in dry-run mode to check for formatting issues:
   - Use: `php-cs-fixer fix --dry-run --diff --verbose`
   - Or: `vendor/bin/php-cs-fixer fix --dry-run --diff --verbose`

3. Report the results:
   - If no issues: confirm the code is properly formatted
   - If issues found: show which files need formatting and what changes are needed
   - Suggest running without `--dry-run` to auto-fix if user wants to apply fixes

4. If a `.php-cs-fixer.dist.php` config file doesn't exist, offer to create one with common standards.

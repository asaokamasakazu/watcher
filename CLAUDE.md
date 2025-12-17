# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A Laravel 11 application (PHP 8.3) called "watcher". This is a standard Laravel project with automated CI workflows for code formatting and release management.

## Development Commands

### Testing
```bash
# Run all tests
./vendor/bin/phpunit

# Run specific test file
./vendor/bin/phpunit tests/Unit/ExampleTest.php

# Run specific test suite
./vendor/bin/phpunit --testsuite=Unit
./vendor/bin/phpunit --testsuite=Feature
```

### Static Analysis (Larastan)
```bash
./vendor/bin/phpstan analyse
```
Configured at level 5 in `phpstan.neon`. Analyzes the `app/` directory.

### Code Formatting (Pint)
```bash
./vendor/bin/pint
```
Configuration in `pint.json` using the Laravel preset. Excludes `resources/views`, `storage`, `bootstrap`, and `database` directories.

### Frontend Development
```bash
npm run dev    # Start Vite dev server
npm run build  # Build for production
```

### Laravel Commands
```bash
php artisan serve              # Start development server
php artisan migrate            # Run database migrations
php artisan tinker             # Interactive REPL
```

## CI/CD Workflows

- **Auto Pint**: Automatically formats PHP code on push to feature branches (excludes main/staging/develop)
- **Auto Label**: Automatic PR labeling based on changed files and branch names
- **Auto Assign**: Automatic PR assignment to authors
- **Auto PR Release**: Automated release PR generation

## Architecture

Standard Laravel 11 structure:
- `app/` - Application code (Models, Controllers, Providers)
- `tests/Unit/` - Unit tests
- `tests/Feature/` - Feature/integration tests
- `routes/` - Route definitions
- `config/` - Configuration files
- `database/` - Migrations, factories, seeders

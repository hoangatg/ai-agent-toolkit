---
name: php-laravel
description: PHP and Laravel development patterns. Laravel 11+, Eloquent ORM, Blade templates, Livewire, API Resources, and modern PHP 8.3+ patterns. Use when building PHP applications, APIs, or full-stack Laravel projects.
---

# PHP & Laravel

> Modern PHP development with Laravel 11+, emphasizing clean architecture and developer experience.

## Core Principles

- **Elegant Syntax**: Expressive, beautiful code
- **Convention First**: Follow Laravel conventions before customizing
- **Modern PHP**: Use PHP 8.3+ features (enums, typed properties, match)
- **Security Built-in**: CSRF, XSS, SQL injection prevention

---

## Stack Decisions

| Concern | Recommended |
|---------|-------------|
| **PHP Version** | 8.3+ |
| **Framework** | Laravel 11+ |
| **ORM** | Eloquent |
| **Frontend** | Livewire 3 or Inertia.js |
| **Queue** | Laravel Queue (Redis/SQS) |
| **Testing** | Pest PHP or PHPUnit |
| **API** | API Resources + Sanctum/Passport |
| **Admin** | Filament PHP |

---

## Key Patterns

- **Form Requests**: Validation in dedicated request classes
- **API Resources**: Transform models for API responses
- **Service Pattern**: Complex business logic in service classes
- **Action Classes**: Single-responsibility action classes
- **Events & Listeners**: Decouple side effects
- **Job Queues**: Background processing for heavy tasks

---

## Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Fat controllers | Service/Action classes |
| Raw queries everywhere | Eloquent with scopes |
| Skip validation | Form Request classes |
| Ignore queues | Queue slow operations |

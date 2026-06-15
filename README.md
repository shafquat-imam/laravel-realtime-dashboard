<div align="center">

# Laravel Real-Time Analytics Dashboard

**Live analytics dashboard built with Laravel Reverb,
Livewire 3, and ApexCharts — WebSocket updates, no page refresh.**

[![Laravel](https://img.shields.io/badge/Laravel-11.x-FF2D20?style=flat&logo=laravel&logoColor=white)](https://laravel.com)
[![Livewire](https://img.shields.io/badge/Livewire-3.x-FB70A9?style=flat)](https://livewire.laravel.com)
[![Reverb](https://img.shields.io/badge/Laravel-Reverb-FF2D20?style=flat)](https://reverb.laravel.com)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

[Live Demo](https://demo.yourname.dev/dashboard) ·
[Loom Walkthrough](https://loom.com/your-link) ·
[Case Study](https://yourname.dev/projects/realtime-dashboard)

</div>

---

## What This Demonstrates

A production-quality analytics dashboard for operations teams,
showing how to build real-time data interfaces with Laravel's
first-party WebSocket solution (Reverb) and Livewire 3.

**Built in 7 days** as Sprint 4 of a 90-day portfolio project.

## Features

- 📡 **Real-time WebSockets** via Laravel Reverb (no Pusher needed)
- 📊 **Live charts** — ApexCharts with streaming data
- 🔐 **Role-based views** — Admin, Manager, Viewer roles
- 🔍 **Filterable tables** — date range, category, status
- 📥 **CSV export** — filtered data, background job
- 🔔 **Live notifications** — toast alerts for threshold breaches
- 📱 **Responsive** — full functionality on tablet and mobile

## Architecture

## Dashboard Widgets

| Widget | Update interval | Data source |
|---|---|---|
| Revenue today | Real-time | Orders table |
| Active sessions | Real-time | Cache (Redis) |
| Orders per hour | 60s | Query + cache |
| Top products | 5 min | Aggregated query |
| Error rate | Real-time | Logs table |
| Conversion funnel | 15 min | Computed metric |

## Tech Stack

| | |
|---|---|
| Framework | Laravel 11 |
| Frontend | Livewire 3 + Tailwind CSS |
| WebSockets | Laravel Reverb |
| Charts | ApexCharts |
| Auth | Filament (admin), Sanctum (API) |
| Cache | Redis |
| Queue | Database (local), Horizon (prod) |

## Setup

```bash
git clone https://github.com/shafquatimam/laravel-realtime-dashboard.git
cd laravel-realtime-dashboard

composer install && npm install

cp .env.example .env
php artisan key:generate

php artisan migrate --seed
php artisan reverb:start &   # WebSocket server
php artisan queue:work &     # Background jobs
npm run dev &
php artisan serve
```

Open `http://localhost:8000` — the dashboard self-seeds with
demo data every 5 seconds so you can see live updates immediately.

**Demo login:**
- Admin: `admin@demo.com` / `password`

---

**Built by [Shafquat Imam](https://yourname.dev)**
Senior Laravel Developer · Available for freelance

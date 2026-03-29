# Studio Raz Cloudflare for Magento 2

> Simplifies integration of Cloudflare services for Magento 2 stores.

## Overview

This module integrates key Cloudflare features into Magento 2 to improve performance, cache management, and image processing. Store administrators benefit from faster page loads and enhanced image quality without additional manual configurations. It connects your Magento website to Cloudflare seamlessly.

## Features

- Enable and disable Cloudflare integration directly from the Magento admin panel.
- Optimize image quality and resizing based on predefined parameters.
- Automatic cache management with support for custom configurations.
- Integrate Cloudflare's Full Page Cache with debug tools.
- API token support for secure cache operations.
- Customizable options for bypassing caching on specific paths or admin-related URLs.

## Requirements

- Magento 2.4.x or higher
- PHP 8.1 or higher
- Active Cloudflare account (for Zone ID, Account ID, and API Token)

## Installation

```bash
composer require studioraz/magento2-cloudflare
bin/magento module:enable SR_Cloudflare
bin/magento setup:upgrade
```

## Configuration

*Admin panel: Stores → Configuration → Cloudflare → General*

| Setting                   | Default | Description                                                                 |
|---------------------------|---------|-----------------------------------------------------------------------------|
| Enabled                   | No      | Enables or disables the module.                                            |
| Image Quality             | 85      | Sets image quality (1-100). Useful values are between 50 and 90.           |
| Image Fit                 | None    | Defines how width and height parameters are applied to resized images.     |

*Admin panel: Stores → Configuration → Cloudflare → Cache (FPC)*

| Setting                   | Default | Description                                                                 |
|---------------------------|---------|-----------------------------------------------------------------------------|
| Enabled                   | No      | Enables or disables Cloudflare cache integration.                          |
| Zone ID                   | None    | Cloudflare Zone ID to identify your website zone.                          |
| Account ID                | None    | Cloudflare Account ID associated with your website.                        |
| API Token                 | None    | API Token with Zone.Cache Purge permission for cache operations.           |
| Debug                     | No      | Writes API debug information to logs.                                      |

*Admin panel: Stores → Configuration → Cloudflare → Worker Configuration*

| Setting                   | Default | Description                                                                 |
|---------------------------|---------|-----------------------------------------------------------------------------|
| Debug Mode                | No      | Adds diagnostic headers to responses.                                      |
| Default TTL Override      | None    | Overrides global TTL settings for public content.                          |
| Hit-For-Pass TTL          | 120     | TTL for uncacheable URL placeholders (min: 2 minutes).                     |
| Admin Path                | None    | Path segment for bypassing cache on admin URLs.                            |
| Bypass Paths              | None    | Additional paths to bypass caching (e.g., `/api`, `/rest`).                |

## How It Works

This module bridges Magento 2 functionalities with Cloudflare's APIs and services. Administrators can configure cache, image optimization, and worker settings. When active, the module automatically handles cache purges, image transformations, and applies Full Page Cache configurations optimized for Cloudflare.

## Wiki Pages

- [Release Notes](Release-Notes)

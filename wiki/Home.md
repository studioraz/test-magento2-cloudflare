# Cloudflare Integration for Magento 2

> This module connects Magento 2 stores to Cloudflare services for enhanced caching and image optimization.

## Overview

The Cloudflare Integration module helps store owners improve page load speed and optimize media content by leveraging Cloudflare's caching and image resizing capabilities. The module enables advanced control over cache settings and provides tools to maximize performance gains with minimal setup.

## Features

- Enable or disable Cloudflare services directly from Magento's admin panel.
- Optimize image formats and quality for faster load times.
- Configure cache settings, including the ability to purge cache by tags.
- Customize caching rules for specific URL paths, admins, and hit-for-pass TTL.
- Use Cloudflare API tokens for secure integration.
- Debug caching and observe API responses using log files.
- Push environment variables to the Cloudflare worker for advanced caching control.

## Requirements

- Magento 2.4.x or higher
- PHP 8.1 or higher
- A valid Cloudflare account and API token

## Installation

```bash
composer config --auth http-basic.repo.packagist.com <username> <password>
composer config repositories.private-packagist composer https://repo.packagist.com/studioraz/
composer config repositories.packagist.org false
composer require studioraz/magento2-cloudflare
bin/magento module:enable SR_Cloudflare
bin/magento setup:upgrade
```

## Configuration

*Admin panel: Stores → Configuration → Studio Raz → Cloudflare*

| Setting                | Default | Description                                                                                                      |
|------------------------|---------|------------------------------------------------------------------------------------------------------------------|
| Enabled                | No      | Enable or disable Cloudflare services.                                                                          |
| Image Quality          | 85      | Adjust the quality for image optimization (value from 1-100). Higher values result in better quality/larger size. |
| Image Fit              | None    | Define how image dimensions will be resized while maintaining aspect ratio.                                      |
| Cache Enabled          | No      | Turn Cloudflare caching for Full Page Cache (FPC) on or off.                                                    |
| Zone ID                |         | Cloudflare Zone ID available in the dashboard Overview page.                                                    |
| Account ID             |         | Cloudflare Account ID available in the dashboard Overview page.                                                 |
| API Token              |         | Secure token required for Cloudflare API operations.                                                            |
| Cache Debug            | No      | Enable to log API requests and responses in `var/log/srcloudflarecache.log`.                                    |
| Debug Mode (Worker)    | No      | Activates diagnostic headers on cached responses.                                                               |
| Default TTL Override   |         | Override the default TTL for public content cache globally.                                                     |
| Hit-For-Pass TTL       | 120     | Set the TTL for hit-for-pass markers on uncacheable URLs (default: 2 minutes).                                  |
| Admin Path             |         | Specify Magento admin URL segment for cache bypass rules.                                                       |
| Bypass Paths           |         | Add custom URL path segments to exclude from caching, e.g., `/api,/rest`.                                       |

## How It Works

This module acts as a bridge between your Magento store and the Cloudflare platform. It uses the Cloudflare API for activities like cache management and global image optimization. Store administrators can fine-tune settings for cache TTLs, image quality, and bypass rules. Debugging options allow tracking API communication to troubleshoot any issues effectively.

## Wiki Pages

- [Release Notes](Release-Notes)

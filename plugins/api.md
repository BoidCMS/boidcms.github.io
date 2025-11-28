# API

A RESTful API for your BoidCMS powered websites.

## Install

- Download the zip file of the plugin from this repo.
- Extract the contents of the zip file.
- Create a folder `api` in the `plugins/` directory on your server.
- Copy the `plugin.php` file to the `api` folder.
- Follow the [steps to activate and configure](https://boidcms.github.io/#/plugins/configure) the plugin.

## Compatibility

This plugin works on any version of BoidCMS.


# Documentation (`v1`)

The BoidCMS API is a powerful RESTful interface that allows programmatic access and management of your website's content, media, themes, and plugins.

## Getting Started

### Base URL (Endpoint)

All API requests must be prefixed with the base URL for version 1.

`https://YOUR-DOMAIN.com/api/v1/`

### Authentication

The API utilizes two separate, secret **API Tokens** for different access levels. These tokens are configured in the **API Plugin Settings** within the BoidCMS Admin Panel.

| Access Type | Token Name | HTTP Method | Required for |
| :--- | :--- | :--- | :--- |
| **Read-Only** | `token` | `GET` | All GET requests (retrieving data). |
| **Write Access** | `auth` | `POST`, `PUT`, `DELETE` | All requests that modify data. |

#### How to Authenticate

Tokens must be passed as **Query Parameters** (for GET and DELETE) or in the **Request Body** (for POST and PUT).

- **Read-Only Example:**
    `GET https://YOUR-DOMAIN.com/api/v1/pages?token=YOUR_READ_ONLY_TOKEN`
- **Write-Access Example (Body):**
    ```json
    {
      "token": "YOUR_READ_ONLY_TOKEN",
      "auth": "YOUR_WRITE_ACCESS_TOKEN",
      "data": { ... }
    }
    ```

### Rate Limiting

The API enforces a configurable rate limit (default 10 requests per minute). If exceeded, a `429 Too Many Requests` status code is returned with a `Retry-After` header.

## API Endpoints Reference

All endpoints return a JSON object with the structure: `{"code": 200, "status": true, "message": "...", "data": { ... }}`.

### 1. Root Reference (`/api/v1/`)

| Method | Description | Path/Parameters | Access |
| :--- | :--- | :--- | :--- |
| **GET** | Returns the list of all available API routes and their methods. | `/` | Read-Only |

### 2. Pages (`/api/v1/pages`)

Manage and retrieve content pages.

| Method | Description | Path/Parameters | Access |
| :--- | :--- | :--- | :--- |
| **GET** | List all pages. | `/pages?token={token}&limit={int}&offset={int}&fields[]={field}` | Read-Only |
| **GET** | Retrieve a single page by slug. | `/pages?token={token}&slug={slug}&raw={bool}` | Read-Only |
| **POST** | Create a new page. | `/pages` **Body:** `token`, `auth`, `data` (with required fields like `title`, `content`) | Write Access |
| **PUT** | Update an existing page. | `/pages?slug={slug}` **Body:** `token`, `auth`, `data` (with fields to update) | Write Access |
| **DELETE**| Delete a page by slug. | `/pages?token={token}&auth={auth}&slug={slug}` | Write Access |

### 3. Media (`/api/v1/medias`)

Manage files in the media directory.

| Method | Description | Path/Parameters | Access |
| :--- | :--- | :--- | :--- |
| **GET** | List all media files. | `/medias?token={token}&limit={int}&offset={int}` | Read-Only |
| **GET** | Retrieve info for a single file. | `/medias?token={token}&file={file_name}` | Read-Only |
| **POST** | Upload a new file. | `/medias` **Body:** `token`, `auth`, file upload data (e.g., multipart form) | Write Access |
| **DELETE**| Delete a media file by name. | `/medias?token={token}&auth={auth}&file={file_name}` | Write Access |

### 4. Themes (`/api/v1/themes`)

| Method | Description | Path/Parameters | Access |
| :--- | :--- | :--- | :--- |
| **GET** | List all available themes. | `/themes?token={token}` | Read-Only |
| **GET** | Retrieve info for a single theme. | `/themes?token={token}&theme={folder_name}` | Read-Only |
| **PUT** | Activate a new theme. | `/themes?token={token}&auth={auth}&theme={folder_name}` | Write Access |

### 5. Plugins (`/api/v1/plugins`)

| Method | Description | Path/Parameters | Access |
| :--- | :--- | :--- | :--- |
| **GET** | List all plugins. | `/plugins?token={token}` | Read-Only |
| **GET** | Retrieve info for a single plugin. | `/plugins?token={token}&plugin={folder_name}` | Read-Only |
| **PUT** | Install/Activate a plugin. | `/plugins?token={token}&auth={auth}&plugin={folder_name}` | Write Access |
| **DELETE**| Uninstall/Deactivate a plugin. | `/plugins?token={token}&auth={auth}&plugin={folder_name}` | Write Access |

### 6. Settings (`/api/v1/settings`)

| Method | Description | Path/Parameters | Access |
| :--- | :--- | :--- | :--- |
| **GET** | Retrieve all site settings. Sensitive fields are hidden unless authorized with `auth` token. | `/settings?token={token}` | Read-Only |
| **PUT** | Update site settings. | `/settings` **Body:** `token`, `auth`, `data` (key/values to update) | Write Access |

### 7. Slugify Utility (`/api/v1/slugify`)

| Method | Description | Path/Parameters | Access |
| :--- | :--- | :--- | :--- |
| **GET** | Converts a given text string into a URL-safe slug. | `/slugify?token={token}&text={string}&esc={bool}` | Read-Only |

## General Usage Details

### Pagination and Field Selection

- **Pagination:** Use `limit` (max items, default 20) and `offset` (starting index, default 0) query parameters on list endpoints.
- **Field Selection:** Use `fields[]` query parameter to select specific fields to include in the response (e.g., `fields[]=title`).

## Status and Error Codes

| Code | Status | Description |
| :--- | :--- | :--- |
| **200** | OK | Success for GET, PUT, and DELETE operations. |
| **201** | Created | A new resource was successfully created (POST). |
| **401** | Unauthorized | Invalid or missing `token` or `auth` credential. |
| **403** | Forbidden | The requested HTTP method is not allowed on this endpoint. |
| **404** | Not Found | Invalid endpoint or the specific resource does not exist. |
| **429** | Too Many Requests | The client has exceeded the API rate limit. |

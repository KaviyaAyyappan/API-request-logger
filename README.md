# API-request-logger
=== API Request Logger ===
Contributor : Kaviya Ayyappan
Tags: api, rest api, logger, cpu, memory, performance
Requires at least: 5.8
Tested up to: 6.6
Requires PHP: 7.4
Stable tag: 1.2.0
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

Logs all WordPress REST API requests including custom endpoints, storing method, route, user, IP, response status, duration, CPU usage, peak memory, and parameters. Includes an admin page to view and filter logs.

== Description ==
API Request Logger is a lightweight WordPress plugin to monitor and log all REST API requests on your site. Perfect for debugging, performance monitoring, and tracking client API usage. It logs:

* API route and HTTP method (GET, POST, etc.)
* User ID (0 if anonymous)
* IP address
* Status code of the response
* Request duration in milliseconds
* CPU time used by the request
* Peak PHP memory usage
* User agent and referer
* Request parameters (JSON, truncated if large)

Logs are stored in a custom database table (`wp_api_log`) and can be viewed under **Tools → API Logs**. The admin page supports:

* Filtering by method, status code, user ID
* Searching by route, IP, or user agent
* Pagination for large datasets
* Clearing all logs
* Retention settings (auto-delete old logs)
* Optional drop table on uninstall

### Key Features
* Logs **all REST API requests** including custom endpoints
* Monitors **CPU, memory, and duration** per request
* Admin UI to **browse, filter, and manage logs**
* Automatic **retention/pruning** with daily cron
* Safe for production sites

== Installation ==
1. Upload the `api-request-logger` folder to the `/wp-content/plugins/` directory.
2. Activate the plugin through the **Plugins** menu in WordPress.
3. Go to **Tools → API Logs** to view logs.
4. Configure retention days and optional drop-on-uninstall settings.

== Usage ==
- After activation, all new API requests will be logged automatically.
- Only users with `manage_options` capability (usually Administrators) can view the logs.
- Use the filters and search in the admin page to find specific requests.
- Monitor CPU and memory columns to identify heavy API calls.
- Clear logs or adjust retention as needed.

== Frequently Asked Questions ==
= Can I view past API calls before plugin activation? =
No, the plugin only logs requests from the moment it is activated.

= Can I log only certain endpoints? =
By default, all REST API requests are logged. Advanced filtering can be added by modifying the plugin code.

= Who can access the logs? =
Only users with `manage_options` capability (administrators by default).

= Will this affect site performance? =
Logging adds minimal overhead. For high-traffic sites, consider lowering retention days to avoid a large table.

== Changelog ==
= 1.2.0 =
* Added CPU time, peak memory, and request duration logging
* Improved admin UI with filters and pagination
* Truncate large parameters safely
* Added daily retention pruning

= 1.1.0 =
* Initial stable release
* Logs method, route, IP, user, status, and params

== Upgrade Notice ==
None

== Screenshots ==
1. Tools → API Logs admin page
2. Filter and search options
3. CPU, memory, and duration columns

== License ==
GPLv2 or later. See https://www.gnu.org/licenses/gpl-2.0.html


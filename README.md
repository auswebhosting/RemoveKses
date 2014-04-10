WP-RemoveKses
=============

Disables KSES for the WordPress Editor Role. Compatible with MU.

## How do I remove KSES for more roles?

This plugin can be easily customised to remove KSES for more than just the `editor` role. Simply open the `removekses.php` file and uncomment the relevant lines:

  $editor       = new RemoveKses(get_role("editor")); // Remove KSES for Editor roles
  $author       = new RemoveKses(get_role("author")); // Remove KSES for Author roles
  $contributor  = new RemoveKses(get_role("contributor")); // Remove KSES for contributor roles
  $subscriber   = new RemoveKses(get_role("subscriber")); // Remove KSES for subscriber roles

## Is this plugin compatible with my PHP and WordPress versions?

* Requires WordPress >= 3.2
* Requires PHP >= 5.3.0

## How does it work?

* Fetches the role to be modified via the constructor `new RemoveKses(get_role("editor"));`.
* Adds the `unfiltered_html` capability to the role, if it doesn't already have it.
* Hooks `content_filtered_save_pre` and runs `kses_remove_filters()` before content is sent to the database.

## Links

+ [Company Page](http://ausweb.com.au/)
+ [WordPress Hosting](http://ausweb.com.au/web-applications/wordpress-hosting/)

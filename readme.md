## Remove Kses
Tags: unfiltered_html, kses, WPMU
Requires at least: 3.0.1
Tested up to: 3.8.2
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Disables (KSES - KSES is a recursive acronym which stands for “KSES Strips Evil Scripts") for the WordPress Editor Role. Compatible with MU.

## Description

This plugin will disable WordPress KSES filtering for the WordPress editor role and is fully compatible with WPMU. 

## Installation

RemoveKses is trivial to install:

1. Upload the plugin folder to the `/wp-content/plugins/` directory
2. Activate the plugin through the 'Plugins' menu in WordPress

## Frequently Asked Questions

### How do I add more roles?

This plugin can be easily customised to remove KSES for more than just the `editor` role.
Simply open the `removekses.php` file and uncomment the relevant lines:

    $editor       = new RemoveKses(get_role("editor")); // Remove KSES for Editor roles
    $author       = new RemoveKses(get_role("author")); // Remove KSES for Author roles
    $contributor  = new RemoveKses(get_role("contributor")); // Remove KSES for contributor roles
    $subscriber   = new RemoveKses(get_role("subscriber")); // Remove KSES for subscriber roles

### How does it work?

* Fetches the role to be modified via the constructor `new RemoveKses(get_role("editor"));`.
* Adds the `unfiltered_html` capability to the role, if it doesn't already have it.
* Hooks `content_filtered_save_pre` and runs `kses_remove_filters()` before content is sent to the database.

### Changelog ==

### 1.0
* Initial Commit

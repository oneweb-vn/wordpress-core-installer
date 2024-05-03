# WordPress Core Installer

A custom Composer plugin to install WordPress core outside of `vendor`.

### Usage
To set up a custom WordPress build package to use this as a custom installer, add the following to your package's composer file:

```json
"type": "wordpress-core",
"require": {
	"onepress/wordpress-core-installer": "^1.0"
}
```

If you need to maintain support for PHP versions lower than 5.6 (not recommended!), use `^1.0` as your version constraint in the above.

By default, this package will install a `wordpress-core` type package in the `wordpress` directory. To change this you can add the following to either your custom WordPress core type package or the root composer package:

```json
"extra": {
	"wordpress-install-dir": "custom/path"
}
```

The root composer package can also declare custom paths as an object keyed by package name:

```json
"extra": {
	"wordpress-install-dir": {
		"wordpress/wordpress": "wordpress",
		"onepress/wordpress-core": "onepress-wordpress"
	}
}
```

### License
This is licensed under the GPL version 2 or later.

### Changelog

##### 2.0.0
- Added support for Composer v2. Special thanks to @Ayesh for the original pull request to add this support.
- Bumped minimum required PHP version to 5.6 (same as WP). If you need to stick with an older PHP version, you're probably ok with also sticking with an older version of Composer and can continue to use `^1.0` as your version constraint.
- Other various fixes and improvements to README, tests, etc.

##### 1.0.0
- Initial stable release
- Added tests and CI
- Support added for custom vendor directories
- Added sanity check for overwriting sensitive directories

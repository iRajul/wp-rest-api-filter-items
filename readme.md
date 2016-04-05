# WP REST API Filter Items

A WordPress plugin to filter [WordPress REST API](http://wp-api.org/) items for your request.

## Description
Per default, a post via WordPress REST API would fetch all data in `wp-json/wp/v2/posts`. This plugin enables you to filter your request for fields you require. Add items to the `GET` attribute on the url, like `wp-json/wp/v2/posts?items=id,title,content` in order to get only according field values.

The plugin supports currently the filtering of post, taxonomy and comments.

## WP-API Versions
 * __Use the branch [`wp-api-v1`](tree/wp-api-v1) if you use WP-API Version 1.__
 * The `master` branch is for development, currently refactoring for WP API Version 2.

## Examples
#### Result for post: `wp-json/wp/v2/posts?_wp_json_nonce=4355d0c4b3&items=id,title,content`
```json
[
	{
		"id": 1,
		"title": {
			"rendered": "Hello world!"
		},
		"content": {
			"rendered": "<p>Welcome to <a href=\"http://localhost/wpbeta/\">WP Beta Dev Sites</a>. This is your first post. Edit or delete it, then start blogging!</p>\n"
		}
	}
]
```

#### Result for taxonomy: `p-json/wp/v2/taxonomies/category?_wp_json_nonce=4355d0c4b3&items=name,slug,types`.
```json
{
	"name": "Categories",
	"slug": "category",
	"types": [
		"post",
		"archiv"
	]
}
```

#### Result for comments: `wp-json/wp/v2/comments?items=id,author_name`
```json
[
	{
		"id": 1,
		"author_name": "Mr WordPress"
	},
	{
		"id": 2,
		"author_name": "admin"
	}
]
```

## Requirements
 * PHP 5.4
 * WordPress 4.*
 * WP REST API

## Kudos
Thanks @dnaber-de for his [modular, extendable PHP autoloader](https://github.com/dnaber-de/Requisite).

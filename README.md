A spec-compliant [JSON Feed](https://jsonfeed.org) template for your Jekyll-generated blog.

## How to Use

Copy the `feed.json` file to the root of your source folder.

## Configuration

There are 2 ways to configure your JSON feed.

### Using `config.yml`

Add a `json_feed` key to your `config.yml`, with all config options under it:

~~~yaml
json_feed:
  favicon: favicon.png
~~~

### Using `_data`

If you'd rather keep `config.yml` clean and group all JSON feed settings in a separate file, add this in your `config.yml`:

~~~yaml
json_feed:
  use_jekyll_data: true
~~~

Then create a `_data/json_feed.yml` in your source folder.

Here are the available options:

- `user_comment` Optional. A description of the purpose of the feed
- `favicon` Optional. Relative path of the favicon in the source folder.
- `icon` Optional. Relative path of the (larger) icon in the source folder.
- `author` Optional. Info about the author. If not included `site.author` will be used.
  - `name` Optional. Name of the author.
  - `url` Optional. Website of the author.
  - `avatar` Optional. Avatar of the author.
    - `local_path` Optional. Relative path of the avatar in the source folder.
    - `external_url` Optional. External avatar URL. Takes precedence over the previous key.
- `expired` Optional. Should be set to true if the feed will no longer be updated.
- `use_category_as_tag` Optional. Set this to true to use `post.category` insteads of tags.
- `post_limit` Optional. Limit the number of posts per feed. Defaults to 20 if not specified here.
- `hubs` A list of hubs used to subscribe to real-time notifications
  - Each hub needs to have these 2 keys:
    - `type` Type of the hub.
    - `url` External URL of the hub.

For a full example check the `_data/json_feed.yml` file in this repository.

## License

This template is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).


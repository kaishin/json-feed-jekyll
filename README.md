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

### Config options

At the root level in your `_config.yml` or `_data/json_feed.yml`:

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
- `use_category_as_tag` Optional. Set this to `true` to use `post.category` insteads of tags.
- `post_limit` Optional. Limit the number of posts per feed. Defaults to 20 if not specified here.
- `hubs` A list of hubs used to subscribe to real-time notifications
  - Each hub needs to have these 2 keys:
    - `type` Required. Type of the hub.
    - `url` Required. External URL of the hub.

For a full example check out the `_data/json_feed.yml` file in this repository.

You can further take advantage of JSON feed features by adding these front-matter keys to your posts under a `json_feed` key:

- `external_url` Optional. An external URL if the post is a link post.
- `date_modified` Optional. Set this manually if you want your feed to include the date the post was last modified.
- `publish_as_text` Optional. Set this to `true` to publish the post as plain text instead of HTML. If not specified it defaults to `false`.
- `summary` Optional. A summary of the blog post. If not specified, the feed with fall back to `post.excerpt`, then `post.description`. If none are present this field is skipped.
- `image` Optional. Main image of the post. If not specified, the feed with fall back to `post.image`, then `post.thumbnail`. If none are present this field is skipped.
  - `local_path` Optional. Relative path of the image in the source folder.
  - `external_url` Optional. External image URL. Takes precedence over the previous key.
- `banner_image` Optional. Banner image of the post. If not specified, the feed with fall back to `post.banner_image`, then `post.banner_image`. If none are present this field is skipped.
  - `local_path` Optional. Relative path of the banner image in the source folder.
  - `external_url` Optional. External banner image URL. Takes precedence over the previous key.
- `author` Optional. Info about the post's author. If not included it will be skipped.
  - `name` Optional. Name of the posts's author.
  - `url` Optional. Website of the posts's author.
  - `avatar` Optional. Avatar of the posts's author.
    - `local_path` Optional. Relative path of the avatar in the source folder.
    - `external_url` Optional. External avatar URL. Takes precedence over the previous key.
- `attachements` Optional. A list of attachements to the post.
  - `url` Required. The location of the attachment.
  - `mime_type` Required. The type of the attachment, such as `audio/mpeg`.
  - `title` Optional. Name for the attachment
  - `size_in_bytes` Optional. Size of the attachement file in bytes.
  - `duration_in_seconds` Optional. How long it takes to listen to or watch, when played at normal speed.

For a full example check out the `example_post.md` file in this repository, and or more info about these options, refer to the [JSONFeed 1.0 spec](https://jsonfeed.org/version/1).

## License

This template is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).


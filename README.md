# Lumina

[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](https://opensource.org/licenses/isc)
[![Hugo](https://img.shields.io/badge/Static%20Site%20Builder-Hugo-green)](https://gohugo.io)

Simplistic wiki-like theme for Hugo

## Features

- Landing page listing all posts sorted according to tags. Posts with multiple tags are listed multiple times.
- meta category with "posts" and "tags" link is automatically added to the landing page. It would make sense to not use "meta" as a tag for any posts, as this would display the "meta" group twice.
- There is no menu displayed.
- Footer is set automatically from the site title and current year. 
- Setting `yearStart` in the `hugo.toml` file causes a from year to appear in the footer.
- External links are marked with 🔗 in both the footer and the post content and will open in a new tab/window.
- Admonitions can be added using the html tags `note`, `warning`, `error`, `success`. Please note unsafe content needs to be allowed. See settings section for details.

## Admonitions

Easily added to posts just using the simple html tags. See example below.

```html
<note>This is a note</note>
```

Please note admonitions need unsafe content to be enabled. See settings section for details.

## Screenshots

### Landing page

![Landing page](./gitimages/landing-page.webp)

### Tags page

![Tags page](./gitimages/tags-page.webp)

### Posts page

![Posts page](./gitimages/posts-page.webp)

### Example posts

![Post4](./gitimages/post4.webp)

![Post5](./gitimages/post5.webp)

## Installation

Place theme files in the themes folder and set `hugo.toml` to use it with 

```toml
theme = 'lumina'
```

## Configuration

### Footer

The footer default contains only the current year but setting yearStart in the `hugo.toml` file to your desired starting year will change the output to have both years in the format yearStart-currentYear (2006-2024).

```toml
[params]
yearStart = ""
```

### Date format

This setting will define the date format used in the posts output.

```toml
[params]
dateFormat = "Jan 2, 2006"
```

### Admonitions

To use the admonitions the settings need to include the following snippet. 

```toml
[markup.goldmark.renderer]
unsafe= true
```

Make sure you understand the implications of enabling this! If you are in control of all content it's not a problem, otherwise it could be used to inject malicious html into your posts. (only before the site is build).

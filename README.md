Hyde Fonts
==========

A Jekyll 4 plugin for loading Google Fonts from a manifest


Installation
------------

1. Add hyde_fonts to your Gemfile

`gem 'hyde-fonts', '~> 0.1.0'`

2. Add entry to your Jekyll config under plugins

```yaml
plugins:
  - hyde_fonts
  ...
```

3. Add the liquid tag to your layout

```liquid
{% hyde_fonts %}
```

which will render as the following, based on the configuration

```html
<link href="assets/fonts/fonts.css" rel="stylesheet" />
```

Adding `inline` to the liquid tag will render the css that would have been in the file.

```liquid
<style>
{% hyde_fonts inline %}
</style>
```


Configuration
-------------

Hyde Fonts comes with the following configuration. Override as necessary in your Jekyll Config

```yaml
hyde_fonts:
  data_path: fonts
  file_output_path: assets/fonts
  css_output_name: fonts.css
  css_minify: true
  enable: true
  fetch_fonts: true
  keep_files: false
```

Create a font manifest in `_data/fonts.yml` which will be used to fetch the desired fonts.

The following example lists Montserrat and Roboto in various weights and italic styles, that will be fetched from Google Fonts and stored in the congiured path.

```yaml
fonts:
  faces:
    - name: Montserrat
      provider: google
      weights:
        - value: 200
          italic: false
        - value: 200
          italic: true
        - value: 400
          italic: false
        - value: 400
          italic: true
        - value: 600
          italic: false
        - value: 800
          italic: false
    - name: Roboto
      provider: google
      weights:
        - value: 200
          italic: false
        - value: 200
          italic: true
        - value: 400
          italic: false
        - value: 400
          italic: true
        - value: 600
          italic: false
        - value: 800
          italic: false
```

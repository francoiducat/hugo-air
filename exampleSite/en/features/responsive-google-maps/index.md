+++
title = 'Responsive Google Maps'
date = 2023-02-15T10:00:00-07:00
draft = false
tags = ['red','green']
params.catchline = "This is a post catchline"
params.button = "Custom Button 😍"
gmaps = true
+++

# Responsive Google Maps

## Usage

You just need to edit your hugo config file and your relevant markdown content file.

### Hugo Config file

Add your gmaps url in your hugo `config` file like 

```yaml
title: Hugo Air Theme
params:
  gmaps_url: https://tinyurl.com/mr3uesbx
```

### Markdown Content file

Add `gmaps: true` in your markdown file

```yaml
---
title: Responsive Google Maps
gmaps: true
---
```

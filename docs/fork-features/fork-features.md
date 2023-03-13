---
layout: default
title: Fork Features
nav_order: 19
---

## 1. More Nesting Levels

Number of nested pages increased up to 6 levels. 
Pages in the root of the site counts as 1-level page, pages in the 5th nested folder counts as 6-level page.

- [1st-Level]({{site.baseurl}}/docs/nested1l)
- [6th-level]({{site.baseurl}}/docs/nested2/nested3/nested4/nested5/nested6/nested6_page)

### Configuration

On child pages YAML front matter properties [parent-ggggrand_parent] must be set to support proper displaying navigation tree.

If page exists in the root of site - no tags must be provided

#### EXAMPLE

```yaml
---
layout: default
title: Nested Lvl 1 Content
---

# 1 Level of nesting
```

If page exists on the 6th level of nesting - all parent tags must be provided

#### EXAMPLE

```yaml
---
layout: default
title: Nested Lvl 6 Content
parent: Nested Lvl 6
grand_parent: Nested Lvl 5
ggrand_parent: Nested Lvl 4
gggrand_parent: Nested Lvl 3
ggggrand_parent: Nested Lvl 2
---

# 6 Level of nesting
```

## 2. Index layout

New type of layout: `index`. This layout will display table of contents of the whole site. This layout isn't suitable for displaying any user content. It's supposed that page with this type of layout will have only YAML front matter configuration.

- [Index page]({{site.baseurl}}/)

### Configuration

#### EXAMPLE

```yaml
---
layout: index
index: true
title: Index
nav_exclude: true
---
```

## 3. Customizable site footer

New property `site_footer` is available for configuring in jekyll configiration file(`_config.yml`). Setting this property updates content of the footer under the side navigation bar.

### Configuration

#### EXAMPLE

```yaml
site_footer: This site powered by <a href="https://github.com/just-the-docs/just-the-docs">Just the Docs</a>, a documentation theme for Jekyll and <a href="https://github.com/asstart/obsidian-publish-action">Obsidian Publish Action</a>, a GitHub action for publishing <a href="https://obsidian.md/">Obsidian</a> notes
```
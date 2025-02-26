---
layout: post
title: Rsync with a custom port
slug: rsync-with-custom-port
tags: ['DevOps', 'shell']
---

You can rsync with a different port by adding `-e "ssh --port"` into the `rsync` command.

<!-- more -->

Here's what it looks like:

```shell
rsync -avz -e "ssh --port" source username@host.com:/destination
```

`-e` specifies a remote shell to use. In this case, we set it to `ssh`. Once we set it to `ssh`, we can use other flags that come with `ssh`.

`-avz` are other flags I commonly use for `rsync`. They stand for archive, verbose, and compress.

- `-a` — archive mode. This is complex since it equals to `-rlptgoD`. Basically this does lots of improvements to make it easier to copy folders recursively.
- `-v` — verbose. It lets me see which files are transferred.
- `-z` — compress. This makes the transfer faster by compressing data.

That’s it!

---
title: apt repository error
author: Jaeman Lee
date: 2021-10-01 14:10:00 +0800
categories: [Ubuntu, error]
tags: [apt]
render_with_liquid: false
---

## Error Description

After executing `sudo apt-get update`, some kinds of error occurs with logs like `404 Nof Fount [IP: ??:??:??:??]`.
It means that the repository is not supported any longer, so you should change repo-urls.
The urls are written on `/etc/apt/sources.list`.


## Change Path

kakao repo works fine in Korea.

These are example for `/etc/apt/sources.list`.

Try to change into this.

```
# See sources.list(6) manpage for more information# Remember that CD-ROMs, DVDs and such are managed through the apt-cdrom tool.
deb http://mirror.kakao.com/ubuntu focal universe

deb http://mirror.kakao.com/ubuntu focal-updates universe

deb http://mirror.kakao.com/ubuntu focal multiverse

deb http://mirror.kakao.com/ubuntu focal-updates multiverse

deb http://mirror.kakao.com/ubuntu focal-backports main restricted universe multiverse

deb http://mirror.kakao.com/ubuntu focal-security main restricted

deb http://mirror.kakao.com/ubuntu focal-security universe

deb http://mirror.kakao.com/ubuntu focal-securtiy multiverse
```

and check apt works well.
```bash
$ sudo apt-get update
```

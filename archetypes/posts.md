+++
author = '{{ .Site.Params.author }}'
date = '{{ .Date }}'
draft = false
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
tags = []
title-images = []
ending-images = []
table-of-contents = true
toc-auto-numbering = true
+++
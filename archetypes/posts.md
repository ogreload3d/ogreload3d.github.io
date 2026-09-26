+++
author = '{{ .Site.Params.author }}'
date = '{{ .Date }}'
draft = true
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
tags = []
title-images = []
ending-images = []
table-of-contents = true
toc-auto-numbering = true
+++
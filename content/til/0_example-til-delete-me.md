---
title: "Hugo front matter basics"
date: 2026-01-12
tags:
  - hugo
  - web
draft: true
---

The `---` section at the top of every markdown file is called **front matter**. It's where you set metadata like title, date, and tags.

```yaml
---
title: "Your title here"
date: 2026-01-12
tags:
  - tag1
  - tag2
draft: false   # set to true to hide from site
---
```

Hugo reads this and uses it to:
- Generate the page title
- Sort posts by date
- Create tag pages automatically
- Hide drafts from production

Delete this file once you've seen how it works!

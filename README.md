### Hi there 👋

:mailbox:How to reach me: [![Facebook Badge](https://img.shields.io/badge/Facebook-%231877F2.svg?style=for-the-badge&logo=Facebook&logoColor=white)](https://www.facebook.com/nikolai.videnov/)
-->

17 lines (16 sloc)  462 Bytes

name: Latest blog post workflow
on:
  schedule:
    # Runs every hour
    - cron: '0 * * * *'
  workflow_dispatch:

jobs:
  update-readme-with-blog:
    name: Update this repos README with latest blog posts
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: gautamkrishnar/blog-post-workflow@master
        with:
          max_post_count: "4"
          feed_list: "https://bandito.re/9ce3c8f8-eecd-4b28-9675-13a3ac33525d.atom"

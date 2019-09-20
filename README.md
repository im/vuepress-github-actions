# vuepress-github-actions



使用github actions 部署 GitHub pages


::: tip
如果你的github不支持 actions [点击](https://github.com/features/actions) 去注册一下就行了
:::


[GitHub Actions 入门教程](http://www.ruanyifeng.com/blog/2019/09/getting-started-with-github-actions.html)

```
name: GitHub Actions Build and Deploy Demo
on:
  push:
    branches:
      - master
jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout
      uses: actions/checkout@master

    - name: Build and Deploy
      uses: JamesIves/github-pages-deploy-action@master
      env:
        ACCESS_TOKEN: ${{ secrets.ACCESS_TOKEN }}
        BRANCH: gh-pages
        FOLDER: .vuepress/dist
        BUILD_SCRIPT: npm install && npm run build
```

# How to checkout

mkdir helloworld

edit .gclient

```
solutions = [
  {
    "name": "mini_chromium_helloworld",
    "url": "https://github.com/linzj/mini_chromium_helloworld.git",
    "managed": False,
  }
]
```
gclient sync

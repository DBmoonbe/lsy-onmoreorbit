# 梁思钰的生日主页 · A Birthday Page for Liang Siyu

[中文](#cn) · [English](#english)

---

<a id="cn"></a>

## 中文

这是我做完的第一个作品，是为好朋友的生日搭的一页网页。

第一次的技术上难免粗糙，整页就一个 `index.html`，样式、动画、逻辑全堆在一起，没用框架，也没怎么考虑性能；云端留言、抽卡、烟花这些是想到一处加一处，能跑起来，但离写得漂亮还差得远。

代码不够优雅，结构不够克制，很多地方都能看出“第一次”的生涩。我不打算掩饰这些。它会一直留在线上，也会一直改。功能未必会变多，但细节会被慢慢打磨。它大概会是我运营最久、更新最久、优化时间最长的一个作品。这一页还一直挂着，想到什么就添一点，哪里不顺手就改一改；朋友在上面留的话和照片也都还在。技术慢慢补，页面慢慢长。

**在线看（静态展示版）**：<https://dbmoonbe.github.io/lsy-onmoreorbit/>

这是静态展示版：气球、蜡烛、生日签、烟花、100 张卡片都能玩。不过 GitHub Pages 是纯静态托管，只能放网页文件、不提供数据库，因此留言、照片、愿望这些要存到后台的功能在这里用不了。它们只在作者单独分享的 WorkBuddy 托管链接里开放——那个版本接了云端数据库，是页面的完整功能版。

### 页面里有什么

- **首屏**：星空、气球、蛋糕。点「吹蜡烛」火苗会灭、冒烟、撒花，生日歌自动响起来；再点一次重新点燃。气球点开是一句话。
- **农历历牌**：右上角一弯蛾眉月垂着可翻面的小牌，正面「十月初五」，背面「蛾眉月」「小阳春」。生日的农历日期藏在这枚物件里。
- **卷首**：四段短文和一份章节导览，可以直接跳到各个区块。
- **抽一支生日签**：12 支签，签级、宜忌、一句签文，可以反复摇。
- **100 件小事**：来自《大学 100 件小事》，10 类 × 10 张，抽过的会记住；也能翻开全部、搜索、按类筛、点开看大图。
- **许愿墙**：预置了几颗星，也可以自己挂一颗。
- **把今天留下来**：左边是寿星的照片、感想和收到的祝福，右边是朋友们写的话，两栏分开。
- **✦ 角标**：带这个标记的地方都能点；卷首还有一份「这一页哪里可以点」的清单，条目能直接跳过去。

### 本地运行

下载仓库，双击 `index.html` 即可。想更接近线上效果，在目录里跑：

```bash
python -m http.server 8000
```

然后打开 `http://localhost:8000`。离线预览时记录区会提示连不上云端，其余功能不受影响。

### 结构

```
index.html          整页（内联样式与脚本）
assets/cards/       102 张手绘 SVG 卡片
deploy.sh           推送到本仓库的脚本
README.md           本说明
```

零构建、零依赖。生日歌由 Web Audio 现场合成，烟花和撒花用 Canvas 画，没有外部音频或图片。留言、照片、愿望存云端数据库，抽卡进度留在各自浏览器本地。

---

<a id="english"></a>

## English

This is the first thing I built — a single page made for a friend's birthday.

A first attempt is bound to be rough, and this one is no exception: everything sits in one `index.html`, styles, animations and logic piled together, no framework, performance barely considered. The cloud guestbook, the card drawer and the fireworks were each added whenever an idea turned up. It runs, but it is a long way from being well written.

The code isn't elegant and the structure isn't disciplined; the awkwardness of a first attempt shows in many places. I don't mean to hide any of it. The page will stay online, and it will keep changing. Features may not grow much, but the details will be polished over time. It will probably be the project I run, update and refine the longest. It has stayed up all along — something gets added when it comes to mind, something gets fixed when it feels clumsy, and the notes and photos people left are still here. The code improves slowly, and the page grows with it.

**See it live (static showcase)**: <https://dbmoonbe.github.io/lsy-onmoreorbit/>

This is the static showcase: balloons, candles, fortune slips, fireworks and all 100 cards work here. GitHub Pages is static hosting only — it serves web files but provides no database, so the guestbook, photo uploads and wishes (which need a backend) don't work on this link. They live behind the author's separately shared WorkBuddy link, which is backed by a cloud database and is the full-featured version of the page.

### What's on the page

- **Opening scene** — a starry sky, balloons and a cake. "Blow the candles" puts out the flames, sets off confetti and starts a birthday tune; one more tap lights them again. Each balloon holds a line.
- **The lunar tag** — a crescent moon in the corner with a small flip card: the fifth day of the tenth lunar month on the front, a note about the young moon on the back. The lunar birthday is tucked into this object rather than spelled out.
- **Preface** — four short passages and a set of links that jump to each section.
- **A birthday fortune** — 12 slips with a rank, a "do / don't" pair and a line of verse; shake as often as you like.
- **100 little things** — ten categories of ten, drawn from an earlier card deck. Drawn cards are remembered; you can also spread all 100 out, search, filter and open one full size.
- **Wish wall** — a few stars are already there, and you can hang your own.
- **Keep today** — the birthday girl's photos, notes and gifts on one side, friends' messages on the other.
- **✦ markers** — anything with this badge is interactive. The preface also has a "what can I tap" list whose entries jump straight to each spot.

### Run it locally

Clone the repo and double-click `index.html`. For something closer to the live version:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`. Offline, the guestbook shows a disconnected notice; everything else still works.

### Layout

```
index.html          the whole page (styles and scripts inline)
assets/cards/       102 hand-drawn SVG cards
deploy.sh           helper for pushing to this repo
README.md           this file
```

No build step, no dependencies. The birthday tune is synthesised with Web Audio, fireworks and confetti are drawn on a canvas, and there are no external audio or image files. Messages, photos and wishes are stored in a cloud database; card-draw progress stays in each browser.

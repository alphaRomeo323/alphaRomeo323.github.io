---
# https://vitepress.dev/reference/default-theme-home-page
layout: home
title: 'Home'
hero:
  name: "有葉のブログ"
  text: "これで6代目になります。"
  tagline: "プログラマ的話題を中心にいろいろ書き貯めるブログです"
  actions:
    - theme: brand
      text: About Me
      link: /about/
    - theme: alt
      text: すべての記事を見る
      link: /posts/

---

<script lang="ts" setup>
import { data as posts } from "./.vitepress/posts.data"
import moment from 'moment';
let latestPosts = posts.slice(0, 8)
</script>

<div class="mx-12">

## Latest Posts


<div class="flex flex-wrap gap-4 flex-row justify-center">
  <a v-for="post of latestPosts" :href="post.url" class="relative w-96 h-48 rounded-lg shadow-lg hover:shadow-emerald-700/50 dark:hover:shadow-orange-300/50 bg-primary overflow-hidden outline outline-2 hover:outline-green-500 dark:hover:outline-amber-500 outline-transparent transition duration-300">
    <img v-if="post.frontmatter.headerimage" :src="post.frontmatter.headerimage" class="img-overlay">
    <div class="absolute top-0 left-0 h-full w-full dark:text-white text-black px-4 py-2 flex flex-col gap-1 justify-center opacity-100">
      <div class="font-bold text-xl  text-center text-ellipsis line-clamp-2">{{ post.frontmatter.title }}</div>
      <div class="font-medium text-left text-ellipsis line-clamp-2">{{ post.frontmatter.description }}</div>
      <div class="font-normal text-left line-clamp-1">
        <span v-for="tag in post.frontmatter.tags"> #{{ tag }} </span>
      </div>
      <div class="font-normal text-right line-clamp-1">{{ moment(post.frontmatter.date).format('YYYY-MM-DD') }}</div>
    </div>
  </a>
</div>

<div class="h-8"></div>

## Latest Update

### Youtube

//in development

<iframe src="https://re.hakuteialpha.com/?embed=true" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<iframe src="https://re.hakuteialpha.com/m?embed=true" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<iframe src="https://re.hakuteialpha.com/y?embed=true" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

</div>

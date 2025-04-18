---
marp: true
theme: uncover
paginate: false
class: invert
---

<style>
  i {
    width: 1em;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  h4 {
    text-align: left;
    margin-top: 0.5em;
    margin-bottom: 0.25em;
  }

  h5 {
    text-align: left;
    font-family: monospace;
    background-color: rgba(255, 255, 255, 0.1);
    margin: 0;
    padding: 0.1em 0.25em;
  }

  h6 {
    text-align: left;
    font-size: 1rem;
    font-weight: normal;
    margin: 0.05em 0;
    display: flex;
    align-items: center;

    > * {
      margin-right: 0.5em;
    }
  }

  .flex {
    display: flex;

    > * {
      flex: 1;
    }
  }
</style>

<br />
<br />
<br />

# Fusion

### The Magic of Writing PHP in Vue SFC

<br />
<br />
<br />

<small>- Sasaya 19/04/25 @ Emoji Cafe & Bar -</small>

---

<div class="flex">
<div>

## Demo

![](https://i.imgur.com/lSM6OhW.png)

</div>
<div>

## Slide

![](https://i.imgur.com/vYUly96.png)

</div>
</div>

<https://github.com/storyn26383/fusion-20250419>

---

## Before Starting

#### Install Dependencies
##### npm install && composer install

#### Run Vite Server
##### npm run dev

#### Run Laravel Server
##### php artisan serve

---

## Who Am I

###### <i>🌴</i> Sasaya
###### ![width:1em](https://www.vim.org/images/vimlogo.svg) Command-Line + Tmux + Vim
###### ![width:1em](https://static-00.iconduck.com/assets.00/laravel-icon-248x256-6tduph6g.png) PHP + Laravel + Swoole
###### ![width:1em](https://icon.icepanel.io/Technology/svg/Vue.js.svg)Vue + Nuxt + TailwindCSS
###### <i>🥁</i> Percussion
###### <i>🐈</i> Gululu x Lomaichi


![bg right:40%](https://i.imgur.com/Y4gtSgR.jpeg)

---

## What is Fusion?

```html
<php>
    $name = prop('Fusion');
</php>

<script setup>
  const greeting = 'Hello'
</script>

<template>
  <h1>{{ greeting }} {{ name }}!</h1>
</template>
```

---

## Sync State

```html
<php>
    $count = prop(0);
    $doubleCount = prop(fn () => $count * 2)->readonly();
</php>

<template>
  <button @click="count++; fusion.sync()">
    <h1>Count: {{ count }}</h1>
  </button>
  <h1>Double Count: {{ doubleCount }}</h1>
</template>
```

---

## Traditional Laravel

```php
Route::get('/api/counter', fn () => ['doubleCount' => request('count', 0) * 2]);
```

```html
<script setup>
  const count = ref(0)
  const doubleCount = ref(0)
  function increase() {
    count.value++
    const response = await fetch(`/api/count?count=${count.value}`)
    doubleCount.value = response.doubleCount
  }
</script>

<template>
  <button @click="increase"><h1>Count: {{ count }}</h1></button>
  <h1>Double Count: {{ doubleCount }}</h1>
</template>
```

---

## Action

```html
<php>
    expose(getHeader: fn () => request()->header('User-Agent'));
</php>

<script setup>
  const result = ref('')
  async function getResult() { result.value = await getHeader() }
</script>

<template>
  <button @click="getResult">
    <h1>Get User Agent from Server</h1>
  </button>
  <h1 v-if="result">{{ result }}</h1>
</template>
```

---

## Traditional SPA Flow

Write API in Laravel
⬇︎
Send AJAX requests from Vue
⬇︎
Render after receiving JSON results

---

## Fusion Flow

No need to write API endpoints
Everything is completed in a single Vue file

---

## How Fusion Works

<img src="https://i.imgur.com/1YH7Yj4.png" width="70%" />

---

## Pros and Cons

#### ✅ Advantages:
- Fashionable
- Fast and convenient

#### ⚠️ Disadvantages:
- Seems simple, but contains many pitfalls

---

## 🚨 Important Notes 🚨

- Fusion is built on top of Inertia
- Fusion does not yet support Laravel 12
- Fusion is in a very early development preview now
- DO NOT use Fusion in production yet

---

## Fusion GitHub

![](https://i.imgur.com/ZJFQyYx.png)

<https://github.com/fusion-php/fusion>

---

## Conclusion

Frontend and backend are like this:
United they will separate, separated they will unite

---

## Thank You

---

## Q & A
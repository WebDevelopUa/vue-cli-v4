Vue CLI v4.5.15 - Starter Vue Project
-----

### Demo is [here](https://webdevelopua.github.io/vue-cli-v4/)

## Prerequisites:

* [16.13.0 LTS](https://nodejs.org/en/)
* [Vue CLI 4.x](https://cli.vuejs.org/guide/installation.html)

``` 
npm i @vue/cli -g

vue create .
```

* Please pick a preset: Default (Vue 3) ([Vue 3] babel, eslint)
    - Use Yarn
    - Use NPM

``` 
npm run serve
```

App running at:

- [Local](http://localhost:8080/)   
- [Network](http://192.168.1.104:8080/)

------

### Project setup

```
npm install
```

#### Compiles and hot-reloads for development

```
npm run serve
```

#### Compiles and minifies for production [vue-cli-service build](https://cli.vuejs.org/ru/guide/cli-service.html#vue-cli-service-build) or [staging](https://rangle.io/blog/custom-build-modes-with-vue-cli-3/)

```
npm run build
vue-cli-service build --dest dist

vue-cli-service build --dest docs
```

#### Lints and fixes files

```
npm run lint
```

#### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).

``` 
vue config
vue-cli-service inspect
```

----- 

## Scoped CSS / [Локальный (scoped) CSS](https://vue-loader.vuejs.org/ru/guide/scoped-css.html)

PostCSS simulates the behavior of Shadow DOM; no need to use classes or ids

```html

<style scoped>
    .example {
        color: red;
    }
</style>

<template>
    <div class="example">hi</div>
</template>
```

```html

<style>
    .example[data-v-f3f3eg9] {
        color: red;
    }
</style>

<template>
    <div class="example" data-v-f3f3eg9>hi</div>
</template>
```

-----


## [SASS](https://vue-loader.vuejs.org/guide/pre-processors.html#sass)

``` 
npm i node-sass sass-loader --save-dev
npm i node-sass -D
npm i sass-loader -D

npm audit fix
npm cache clean --force
npm cache rm --force
npm cache verify
```

---- 

## [PostCss](https://vue-loader.vuejs.org/guide/pre-processors.html#postcss)

``` 
Vue Loader v15 no longer applies PostCSS transforms by default. You will need to use PostCSS via postcss-loader.
```

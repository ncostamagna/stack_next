# React

about react in https://github.com/ncostamagna/react

# Benefits

## Different Rendering technoques

you can choose to render your content on the server or on the client
<img src="images/001.png" />

## Performance

- Code Splitting: divide your web app in small chunks
- Image oprimization: render imagen for especific viewport (pc, mobile, tablet)
  <br />

<img src="images/002.png" />

## File Based Routing

Router based by folder and files

## SEO

search engine optimization. You're making the life of bots easier to discover your content

# Create Project

https://nextjs.org/docs/basic-features/typescript

```sh
# create nextjs project with typescript
npx create-next-app@latest --ts

npm run dev # starts the developer server
npm run build # builds the app
npm start # runs the built app in production mode

```

Upgrade next version: https://nextjs.org/docs/upgrading <br />
If you want to upgrade, you'll see all details (in the documentation) for possible breaking changue. For example, in 12 next version the target field mustn't be in next.config.js file

# Project sctruct

## pages

default in index.js<br />

I only need create a file in page folder for can access in the page, the url must have the same name that the file.<br />
for example, if I create a home.tsx file then I'll see in /home path<br />

### \_app

entry point in our pages. we can put standars elements in the pages, for example, a footer

```tsx
function MyApp({ Component, pageProps }) {
  return (
    <div>
      <Component {...pageProps} />
      <footer>
        <p>My fuck footer</p>
      </footer>
    </div>
  );
}
```

when you need to add some Global Layout or Meta Tags

### \_document

Overwrite the Basic HTML structure, lets you edit only html code structure which means that you can't add javascript events in it.

### api

backend and server side code

## public

assets: images, icons, etc..

## styles

- global.css: global css
- Home.module.css: local css in each modules, in this case only in Home component (if you import this css file in Home component)

# Routing

## History API

navigate the user back and forth between different pages, 3 differents routing

- index router: default root page
- nested files: /my-page ({nested - anidados})
- define brackets: /my-page/[id]

## Dynamic Routers

for example if we have a coffe-store/[id].js file in page folder.

We can user router.query for getting the id value

```ts
import {useRouter} from 'next/router'

const Store = () => {
  const router = useRouter()
  const {id} = router.query
  ...
}
```

## Link

We can use link for going to differents pages, without refresh the page.<br />
Only for internal next page

```ts
import Link from "next/link";

const SomePage = () => {
  return (
    <div>
      <Link href="/coffee-store">
        <a>coffee store</a>
      </Link>
    </div>
  );
};
```

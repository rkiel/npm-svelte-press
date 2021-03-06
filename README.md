# Simple static site generator for Svelte

## Quick Start

Create a new Svelte project

```bash
npx degit sveltejs/template my-static-site
cd my-static-site
npm install
```

Install svelte-press

```bash
npm install svelte-press --save-dev
```

Add a script to package.json

```json
"scripts": {
  "press-build": "press-build",
  "press-page": "press-page",
  "press-start": "npm run press-build && npm run start"
},
```

Create some pages pages without any layout

```bash
npm run press-page -- -t Index
```

Create some pages with a layout

```bash
npm run press-page -- -t Home         -l "Default Layout"
npm run press-page -- -t "About Us"   -l "Default Layout"
npm run press-page -- -t "Contact Us" -l "Default Layout"
```

Create some pages in a directory

```bash
npm run press-page -- -t Login            -l "Default Layout" -p account
npm run press-page -- -t Signup           -l "Default Layout" -p account
npm run press-page -- -t "Reset Password" -l "Default Layout" -p account
```

Update DefaultLayout found in `_layouts/DefaultLayout.svelte`

```html
<div>
  <div class="nav">
    <a href="/">Index</a>
    <a href="/home.html">Home</a>
    <a href="/about-us.html">About</a>
    <a href="/contact-us.html">Contact</a>
    <a href="/account/login.html">Login</a>
    <a href="/account/signup.html">Signup</a>
    <a href="/account/reset-password.html">Reset</a>
  </div>
  <slot></slot>
</div>

<style>
  .nav {
    text-align: center;
    padding: 1em;
    max-width: 340px;
    margin: 0 auto;
  }
</style>
```

Generate the static site

```bash
npm run press-build
```

Start web server

```bash
npm run start
```

View pages

- [http://localhost:5000/](http://localhost:5000/)
- [http://localhost:5000/index.html](http://localhost:5000/index.html)
- [http://localhost:5000/home.html](http://localhost:5000/home.html)
- [http://localhost:5000/about.html](http://localhost:5000/about.html)
- [http://localhost:5000/contact.html](http://localhost:5000/contact.html)
- [http://localhost:5000/account/login.html](http://localhost:5000/account/login.html)
- [http://localhost:5000/account/signup.html](http://localhost:5000/account/signup.html)
- [http://localhost:5000/account/reset.html](http://localhost:5000/account/reset.html)

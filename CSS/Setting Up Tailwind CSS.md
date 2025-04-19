```
npm init
```
```
npm install tailwindcss @tailwindcss/cli
```
Create two folder. dist and src.
```bash
dist
|
index.html
style.css

src
|
input.css
```
Paste this in input
```
@import "tailwindcss";
```
Setup dev in package.json
```
"scripts": {
        "test": "echo \"Error: no test specified\" && exit 1",
        "dev": "npx @tailwindcss/cli -i ./src/input.css -o ./dist/style.css --watch"
    },
```
Now run
```
npm run dev
```
To customize anything use this in input.css
```
@theme {

    --font-primary: "Poppins", "serif";

    --breakpoint-3xl: 1920px;

    --color-avocado-100: oklch(0.99 0 0);

    /* ... */

}
```

create server.js

```sh
npm init -y
```

```sh
npm i express cors dotenv nodemon jsonwebtoken mongoose bcryptjs nodemailer cookie-parser multer validator body-parser
```

```json
  "type": "module",
```

```json
    "server":"nodemon server.js"
```

```js
import express from 'express'
import cors from 'cors'
import "dotenv/config"
import cookieParser from 'cookie-parser'

const app=express();
const port=process.env.PORT||4000
  

app.use(express.json());
app.use(cors({credentials:true}));
app.use(cookieParser())

app.get('/',(req,res)=>{
    res.send("Working");
})

app.listen(port,()=>{
    console.log(`Server started on ${port} port`)
})
```
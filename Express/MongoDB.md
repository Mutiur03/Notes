Create DB from  mongo DB atlas

Add connection URI to .env file

create mongoDB.js in config folder on server folder

```js
import mongoose from "mongoose";

const connectDB=async()=>{
mongoose.connection.on('connected',()=>{
        console.log("DB Connected");
    })
    await mongoose.connect(`${process.env.MONGODB_URI}/project-name`);
    }

export default connectDB;
```



add this in server.js
`
```js
/*.
.
.*/
import connectDB from './config/mongoDB.js'; //.js must

const app=express();
const port=process.env.PORT||4000
connectDB();
```


create model_name.js in models folder on server folder


```js
import mongoose from "mongoose";

const userScema = new mongoose.Schema({
  name: { type: String, required: true },
  email: { type: String, required: true, unique: true },
  password: { type: String, required: true },
  verifyOTP: { type: String, default: "" },
  verifyOTPExpireAt: { type: Number, default: 0 },
  isAccountVerified: { type: Boolean, default: false },
  resetOTP: { type: String, default: "" },
  resetOTPExpireAt: { type: Number, default: 0 },
});

const userModel = mongoose.model.user || mongoose.model("user", userScema);

export default userModel;
```

create controller_name.js in controller folder on server folder then add whatever you want to do



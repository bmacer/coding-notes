install express

    npm install express
install nodemon (auto-reload)

    npm install -g nodemon

hello world-ish

    express = require('express');

    const app = express();

    app.get("/", (req, res) => {
      res.send("<h1>Hello World</h1>");
    })

    app.listen(3000, () =>  {
      console.log("started on port 3000");
    })

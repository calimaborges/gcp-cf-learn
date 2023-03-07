# Google Cloud Function Learning

## Start with simple Node.JS files

> `nodejs/package.json`

```json
{
  "name": "gcp-learn",
  "scripts": {
    "start": "functions-framework --target=main --port=8080"
  },
  "dependencies": {
    "@google-cloud/functions-framework": "^3.1.3"
  }
}
```

> `nodejs/index.js`

```javascript
/**
 * Responds to any HTTP request
 *
 * @param {!express:Request} req HTTP request context.
 * @param {!express:Response} res HTTP response context.
 */
const functions = require("@google-cloud/functions-framework");

functions.http("main", (req, res) => {
  if (!process.env.VERSION) {
    throw new Error("VERSION is not defined in the environment variable");
  }

  res
    .status(200)
    .send(`<h1>Cloud Function version ${process.env.VERSION}</h1>`);
});
```

## Test it locally

```bash
cd nodejs
npm install
npm start
```

## Configure Google Cloud


## Reference

https://getbetterdevops.io/google-cloud-functions-with-terraform/


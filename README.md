# puppeteer-scraper

Implement scrapers using a sane api on top of codeceptjs and puppeteer.

## Example

In scripts/check24/goto-check24.js

```js
module.exports = async function GotoCHECK24Main(ctx, I) {
  await I.amOnPage('https://www.check24.de');
  await I.wait(2);

  // Use any other codeceptjs commands from 
  // https://codecept.io/helpers/Puppeteer/
};
```

Then in src/crawl-script.js

```js
const runScript = require('./runner');
const scriptFn = require('./scripts/check/goto-check24');

async function() {
    await runScript(scriptFn, './_out', {});
}()
```



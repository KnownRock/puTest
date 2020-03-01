### 树莓派(Unbuntu19)安装puppeteer
#### 安装node和npm
sudo apt install nodejs
sudo apt install npm

#### 安装chrome及相关包
sudo apt install chromium-browser chromium-codecs-ffmpeg

npm install puppeteer-core

#### 测试程序
~~~
const puppeteer = require('puppeteer-core');
  
(async () => {
  const browser = await puppeteer.launch({executablePath: '/usr/bin/chromium-browser'});
  const page = await browser.newPage();
  await page.goto('http://bing.com');
  await page.screenshot({path: 'example.png'});
  await page.pdf({path: 'example.pdf', format: 'A4'});
  await browser.close();
})();
~~~
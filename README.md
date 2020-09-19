# Bot Detection
Bot detection has always been a cat and mouse game. Whether it's preventing bots from scraping data without permission or preventing bots from automatically purchasing sneakers, there are many reasons a site owner may want to stop bots from connecting to their website. After a bit of research, I have compiled a list of commonly used methods to detect bots, along with their pros and cons. This is by no means a comprehensive list and only includes the methods I personally know of, but this should be a decent amount of ways to detect bots.

# Detection Methods

 - [User Agents](#user-agents)
 - [Logic Checks](#logic-checks)
 - [Cookie Support](#cookie-support)
 - [JavaScript Support](#javascript-support)
 - [Spoofing Detection](#spoofing-detection)
 - [Variable Detection](#variable-detection)
 - [Input Analysis](#input-analysis)

# User Agents
A user agent is a header sent by the client to the server that allows the server to identify specific attributes about the client that sent the request. Some bots do not attempt to spoof this header and instead outright identify themselves, allowing for a simple detection method.

### Pros

 - Protects against amateur bots 
 - Nearly impossible for legitimate visitors to accidentally get detected by

### Cons

 - Trivial to get around, as this header can be modified

# Logic Checks
Logic checks generally check the behaviour of visitors and check if they exceed a threshold that only bots could reach. An example of such a check would be checking how many pages a visitor attempts to go to in a period of time.

### Pros

 - Imposes a limit on what bots can do
 - Forces bots to adapt if they desire to get around this detection method

### Cons

 - Can accidentally be triggered by legitimate visitors if thresholds are too low

# Cookie Support
A cookie is data kept on a computer by a web browser that websites can view. Some bots do not support cookies, providing a detection method.

### Pros

 - Protects against basic bots
 - Hard for legitimate visitors to accidentially trigger
 
### Cons
 
 - More advanced bots support cookies, allowing them to get around this detection method

# JavaScript Support
Javascript is a programming language that the majority of web browsers support. Most bots do not run JavaScript, as the resource cost of doing so would limit the amount of content that they can scrape.

### Pros

 - Protects against the vast majority of bots

### Cons

 - Tools such as [Selenium](https://www.selenium.dev) and [Puppeteer](https://pptr.dev) run JavaScript, allowing some bots to get around this detection method
 - Privacy conscious individuals may have JavaScript disabled
 
# Spoofing Detection
In order to get around the [User Agents](#user-agents) detection method, most bots change their user agent to one of a real web browser. This can be detected in many ways, such as checking for support for browser specific features and the order in which headers are sent.
 
### Pros

 - Generally reveals the true identity of a bot
 
### Cons

 - Headless browsers will generally get around this detection method
 - Privacy conscious users may spoof their user agent
 - Details used to determine the true identity of a bot may change over time, which could cause problems down the line

# Variable Detection
In order to get around the [JavaScript Support](#javascript-support) detection method, most bots use a headless browser that can execute JavaScript. The vast majority of these headless browsers have variables that expose thee fact that they are being used, such as `navigator.webdriver` and `window._phantom`.

### Pros

 - Nearly impossible for legitimate visitors to accidentially get detected by

### Cons

 - More advanceed bots get around this detection method
 - Some headless browser implementations such as [SecretAgent](https://secretagent.dev) get around this detection method by default
 
# Input Analysis
The way a bot interacts with a web page is noticeably different than the way a human interacts with a web page. This knowledge can be used to detect bots by checking things such as how fast a visitor types in a field and how a visitor moves their mouse.

### Pros

 - Forces bots to do humanlike inputs in order to get around this detection method
 
### Cons

 - Can accidentially be triggered by legitimate visitors if thresholds are too low

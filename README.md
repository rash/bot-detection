# Bot Detection
Bot detection has always been a cat and mouse game. Whether it's preventing bots from scraping data without permission or preventing bots from automatically purchasing sneakers, there are many reasons a site owner may want to stop bots from connecting to their website. After a bit of research, I have compiled a list of commonly used methods to detect bots, along with their pros and cons. This is by no means a comprehensive list and only includes the methods I personally know of, but this should be a decent amount of ways to detect bots.

# Detection Methods

 - [User Agents](#user-agents)
 - [Logic Checks](#logic-checks)
 - Cookie Support
 - JavaScript Support
 - Spoofing Detection
 - Variable Detection
 - Input Analysis

# User Agents
A user agent is a header sent by the client to the server that allows the server to identify specific attributes about the client that sent the request. Some bots do not attempt to spoof this header and instead outright identify themselves, allowing for a simple detection vector.

### Pros

 - Nearly impossible for legitimate visitors to accidentally get detected by
 - Protects against amateur bots 

### Cons

 - Trivial to get around, as this header can be modified

# Logic Checks
Logic checks generally check the behaviour of visitors and check if they exceed a threshold that only bots could reach. An example of such a check would be checking how many pages a visitor attempts to go to in a period of time.

### Pros

 - Imposes a limit on what bots can do
 - Forces bots to adapt if they desire to circumvent this measure

### Cons

 - Can accidentally be triggered by legitimate visitors if thresholds are too low

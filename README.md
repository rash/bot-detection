# Bot Detection
Bot detection has always been a cat and mouse game. Whether it's preventing bots from scraping data without permission or preventing bots from automatically purchasing sneakers, there are many reasons a site owner may want to stop bots from connecting to their website. After a bit of research, I have compiled a list of commonly used methods to detect bots, along with their pros and cons. This is by no means a comprehensive list and only includes the methods I personally know of, but this should be a decent amount of ways to detect bots.

# Detection Methods

 - [User Agents](#user-agents)
 - Logic Checks
 - Cookie Support
 - JavaScript Support
 - Spoofing Detection
 - Variable Detection
 - Input Analysis

# User Agents
A user agent is a header sent by the client to the server that allows the server to identify specific attributes about the client that sent the request. Some bots do not attempt to spoof this header, allowing for a simple detection vector.

### Pros

 - Nearly impossible for legitimate visitors to accidentally get detected by
 - Protects against amateur bots 

### Cons

 - Trivial to get around, as this header can be modified

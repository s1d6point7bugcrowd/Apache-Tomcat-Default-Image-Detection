## Disclaimer

This script is intended for educational and authorized testing purposes only. The author is not responsible for any misuse or damage caused by this tool. Ensure you have explicit permission to test the target system and abide by local laws and regulations related to cybersecurity and ethical hacking.

By using this script, you agree that you are acting in compliance with all applicable laws. Unauthorized scanning or testing of systems without permission is illegal and unethical.

Always obtain permission from the owner of the systems you are testing.



# Apache Tomcat Default Image Detection

This Nuclei template detects non-hardened Apache Tomcat installations by checking for the default Tomcat image (`tomcat.gif`) exposed on the server. The presence of this image indicates a potential misconfiguration or exposure of default Tomcat resources, which could lead to further security issues if not remediated.

## How It Works

This template sends a `GET` request to the target URL with the query string `/?f=%5B`, mimicking the behavior of a crafted request used to detect Tomcat default pages. The response is inspected for the presence of the following HTML image tag:

```html
<img src="tomcat.gif" height="92" width="130" alt="The Mighty Tomcat - MEOW!"/>

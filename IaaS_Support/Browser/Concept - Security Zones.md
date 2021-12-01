# Edge
   

Edge Chromium today uses Windows’ Security Zones by default when deciding whether or not to release Windows Integrated Authentication (Kerberos/NTLM) credentials automatically.

Chromium will process URLACTION_CREDENTIALS_USE to decide whether Windows Integrated Authentication is used automatically, or the user should instead see a manual authentication prompt.

(Aside: the manual authentication prompt is really a bit of a mistake– the browser should instead just show a prompt: “Would you like to [Send Credentials] or [Stay Anonymous]” dialog box, rather than forcing the user to reenter the credentials that Windows already has.

More information:

[https://source.chromium.org/chromium/chromium/src/+/master:net/http/url_security_manager_win.cc;drc=ab982fafeeb9719f38ea961bfc46139af5ff4a45;l=73](https://source.chromium.org/chromium/chromium/src/+/master:net/http/url_security_manager_win.cc;drc=ab982fafeeb9719f38ea961bfc46139af5ff4a45;l=73)

[https://source.chromium.org/search?q=MapURLToZone&ss=chromium&originalUrl=https:%2F%2Fcs.chromium.org%2Fsearch%2F](https://source.chromium.org/search?q=MapURLToZone&ss=chromium&originalUrl=https:%2F%2Fcs.chromium.org%2Fsearch%2F)

More information: [https://textslashplain.com/2020/01/30/security-zones-in-edge/](https://textslashplain.com/2020/01/30/security-zones-in-edge/)

# IE
![[Pasted image 20210818203728.png]]
# DarkerNZBget
[![Discord](https://img.shields.io/badge/Chat-Discord-738bd7.svg?style=for-the-badge)](https://discord.gg/fKcCXwb)<br>
Custom CSS to apply to NZBget using an NGINX subfilter

As far as I know, a NGINX sub filter is the only way to apply this to NZBget. Below is one example of how to use
a reverse proxy block in NGINX to apply.
```
#NZBGet ReverseProxy
        location /nzbget {
                proxy_pass http://localhost:<NZBgetPORT>;
                proxy_set_header Host $host;
                proxy_set_header X-Real-IP $remote_addr;
                proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
                proxy_set_header Accept-Encoding "";
                sub_filter '</head>' '<link rel="stylesheet" type="text/css" href="https://rawgit.com/ydkmlt84/DarkerNZBget/master/nzbget_custom_darkblue.css"></head>';
                sub_filter_once on;
        }

```
<br>
<i>Rawgit link for master branch = https://rawgit.com/ydkmlt84/DarkerNZBget/master/nzbget_custom_darkblue.css</i></br>
<i>Rawgit link for develop branch = https://rawgit.com/ydkmlt84/DarkerNZBget/develop/nzbget_custom_darkblue.css</i>
<br>
<b> Screenshots</b>
</br>
<img src="https://i.imgur.com/tXFSyAw.png"></img>
<br>
<img src="https://i.imgur.com/oSichzz.png"></img>

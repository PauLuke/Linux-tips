When accessing ChatGPT via Firefox I always had that annoying popup asking: "Allow chatgpt.com to store data in persistent storage?". No matter how many times I answered it.

How to solve that? [An user on superuser.com has the solution](https://superuser.com/questions/1923972/how-to-get-rid-of-this-message-in-firefox-on-kubuntu-allow-chatgpt-com-to-stor):

You can disable it by clicking the lock icon in url bar -> Connection secure -> More infomation -> Permissions -> Store data in persistent storage

Unclick "Use Default" and set it to "Block". This should avoid the popup from showing.

![firefox](https://github.com/PauLuke/Linux-tips/blob/main/Tips/assets/block_chatgpt_popup_firefox.webp)

This should be fixed (ask only once) in Firefox 145.


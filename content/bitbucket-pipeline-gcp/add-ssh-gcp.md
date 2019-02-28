---
title: "Add SSH Keys to VM"
date: 2017-09-27T14:52:47+07:00
draft: false
weight: 2
---

### ADD SSH Keys to VM
- Go to your Google cloud console > VM Instance > Select your target remote server > VM instance details > Edit. In the bottom you will see SSH Keys section, click show and edit

![SSH Keys](/coding-guidelines/bitbucket-pipeline/ssh-keys-view-edit.png)

- Put your public key from bitbucket with addition your user for login the format should be `<ssh-rsa> <base64key> <username>`
  - Example

  ```bash
  ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEAinno+QU+p2of7V/U2VKGxwLi7/vmozA/ScGpW3y6N+vZZzWXm9UHQQp/NLaOvgHTUGglBV25i9P7NchPewOZbCbWrtDJhQawBqRdBc26BkteG8k
  mWq5sFGulOAXreXOtroNrqrKCx5UV1A2fVzXiPscmZCSdBEJ9N0MHsktRnkimUBmvWK1EzVJ5rN5KK7jOTIOf9pw8rO0XBUCkKXKOSMa1Oi2YJHKSTOg0rzT0RShuTTMrbd2ywRUBoRoFPEkRkX
  dNydQP4Wqr5NFF15ssLsu28CHVTueEbrTzpDs6MDhwvdmqWXYrLfZayuyybV5mymNfo8QpfGRnRFvdjhP/Nw== deploy
  ```

- Save the setting and wait until the process is finished


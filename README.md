## Go-Wechaty-Bot XP PROTOCOL

> 仅供学习使用，*请勿用于非法用途*！

[1]: https://img.shields.io/badge/puppet-xp-blue
[2]: https://img.shields.io/badge/puppet-padlocal-blue
[3]: https://img.shields.io/badge/puppet-4u-blue
[5]: https://github.com/XRSec/Go-Wechaty-Bot-XP
[6]: https://github.com/XRSec/Go-Wechaty-Bot/tree/main/padlocal#go-wechaty-bot-padlcoal-protocol
[7]: https://github.com/XRSec/Go-Wechaty-Bot/tree/main/4u#go-wechaty-bot-4u-protocol

[![puppet-xp][1]][5] 〰️ [![puppet-padlocal][2]][6] 〰️ [![puppet-4u][3]][7] 「 Select Gateway 」

## Info

### Glossary

```ini
Gateway : puppet-xp
Server: go-wechaty
```

## Architecture

```mermaid
flowchart LR
    Polyglot-->Python
    Polyglot-->Go
    Polyglot -->Rust
    Python-->Grpc
    Go-->Grpc
    Rust-->Grpc
    Grpc-->Gateway{Gateway}-->xp
    xp-->微信
```

## ⇲ Use

### Init (depend main.General)

1. Checkout branch

   ```bash
   cd xp
   ```

2. Generate Token

   ```bash
   # Generate Token
   WECHATY_TOKEN：curl -s https://www.uuidgenerator.net/api/version4
   WECHATY_PUPPET_SERVICE_TOKEN："insecure_" + WECHATY_TOKEN
   # WECHATY_TOKEN WECHATY_PUPPET_SERVICE_TOKEN 可同可不同
   ```

3. Modifying a Configuration File

   ```bash
   # wechatyGateway.bat
   @set WECHATY_TOKEN=xxxxxxxxxxxxxxxxxx
   @set WECHATY_PUPPET_SERVICE_TOKEN=insecure_xxxxxxxxxxxxxxxxxx
   @set WECHATY_PUPPET_SERVER_PORT=25000
   ```

4. Install the Software ([**WeChat.exe Check Download**](https://github.com/wechaty/wechaty-puppet-xp/releases/download/v0.5/WeChatSetup-v3.3.0.115.exe))

   ```bash
   # Must install on Powershell ( because env )
   ## WeChatSetup-v3.3.0.115.exe

   npm --registry http://registry.npmmirror.com install -g windows-build-tools
   npm --registry http://registry.npmmirror.com install -g wechaty-puppet-xp
   ```

5. Optional operation

   ```bash
   # Set Environment
   @chdir
   # Google: How to set the path and environment variables in Windows
   ```

### Start Server

```bash
cd xp && .\wechatyGateway.bat # Start puppet-xp Gateway
cd server && go run main.go # Start Server
```

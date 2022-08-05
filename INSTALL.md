# How to Build Telegram for macOS

1. Clone this repository with submodules:
	
	```sh
	git clone https://github.com/n690rp/TelegramSwift.git --recurse-submodules
	```
2.  ```brew install cmake ninja openssl@1.1 zlib autoconf libtool automake yasm pkg-config```
3.  ```sh %project_dir%/scripts/configure_frameworks.sh```
4. Open `Telegram-Mac.xcworkspace` in the latest XCode.  
5. Build.



# If you want to develop a fork

1. Do first and second step above.
2. Change bundle Identifier and team-id. Easiest way is to search all mentions `ru.keepcoder.Telegram` and change it to your own. Team-id you can find on apple developer portal.
3. Obtain your [API ID](https://core.telegram.org/api/obtaining_api_id). **Note:** The built-in `apiId` is highly limited for api usage. **Do not use it** in any circumstances except verify binaries.
4. Open `Telegram-Mac/Config.swift` and repalce `apiId` and `apiHash` from previous step. **Note:** Do not forget to change `teamId` either.
5. Replace or remove `SFEED_URL` and  `APPCENTER_SECRET`  in `*.xcconfig` files. (First uses for in-app updates and second for collecting crashes on [appcenter](https://appcenter.ms))
6. Write new better code.
7. If you still have a questions feel free to open new issue [here](https://github.com/overtake/TelegramSwift/issues/new).

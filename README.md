用途：帮助那些想把openclaw接入本地运行大模型，却不会配置的朋友。可以让openclaw调用局域网内的lm-studio来运行大模型。

参照openclaw.json文件,openclaw.json是openclaw使用什么模型的配置文件。

1. openclaw.json存放在 /home/your_user_name/.openclaw/ 路径下，初次体验，可以替换掉你现有的openclaw.json文件。如果不满意，可以运行openclaw onboard命令重新配置一次龙虾。
 
 2. "baseUrl": "http://192.168.0.12:1234/v1"，这个是跑lmstudio机器的IP地址
 
 3. "primary": "lmstudio/openai/gpt-oss-20b"，这里写你要运行的大模型，必须是lmstudio开头，如果只写openai/gpt-oss-20b，则会报错
 
 4. "models": {
         "lmstudio/openai/gpt-oss-20b"，这里写你要运行的大模型，必须是lmstudio开头，如果只写openai/gpt-oss-20b，则会报错

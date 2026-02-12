Purpose: Help those who want to connect openclaw to run large models locally, but don't know how to configure it. OpenClaw can call LM-Studio in the LAN to run large models.

目的：帮助那些想要把OpenClaw连接到本地lmstudio上运行大型模型却不知道如何配置的人。OpenClaw可以在局域网内调用LM-Studio来运行大型模型。

Refer to openclaw.json file, openclaw.json is the configuration file of what model openclaw uses.

参考我上传的openclaw.json文件，openclaw.json是openclaw使用什么型号的配置文件。

1. openclaw.json存储在/home/your_user_name/.openclaw/ 路径下，首次使用时你可以替换现有的openclaw.json文件,然后运行命令 openclaw onboard 。 跳过第一项选择模型供应商，在选择具体模型中会看到lmstudio，选择进去，选择你的模型。

 2. "baseUrl": "http://192.168.0.12:1234/v1", this is the IP address of the lmstudio machine
    
 "baseUrl"："http://192.168.0.12:1234/v1"，这是lmstudio运行在哪台机器上的IP地址

 3. "primary": "lmstudio/openai/gpt-oss-20b", here you write the large model you want to run, it must start with lmstudio, if you only write openai/gpt-oss-20b, an error will be reported
 
 "primary": "lmstudio/openai/gpt-oss-20b",在这里输入你想要运行的大模型，它必须以lmstudio开头，如果你只写openai/gpt-oss-20b，将会报错

 4. "models": {
         "lmstudio/openai/gpt-oss-20b", here you write the large model you want to run, it must start with lmstudio, if you only write openai/gpt-oss-20b, it will report an error

"models": {
         "lmstudio/openai/gpt-oss-20b", 在这里输入你想要运行的大模型，它必须以lmstudio开头，如果你只写openai/gpt-oss-20b，将会报错


5.  "models": [
          {
            "id": "gpt-oss-20b", where the name of the model is written（模型名称的书写位置）
            "name": "gpt oss 20b", where the name of the model is written（模型名称的书写位置）
            "reasoning": false,
            "input": [
              "text"
            ],


6. "contextWindow": 131072, 这里是上下文窗口大小，ollama官方那边建议是openclaw至少是64k以上，但是我测得的是至少13k~15k起步才能启动对话，否则会报错.64k以上应该是ollama认为可以流畅的运行的标准。
也就是说如果你使用的模型，它的最大上下文窗口过小的话基本就无法使用openclaw。

"maxTokens": 8192  这里是最大输出，根据你的大模型性能和机器性能自行调整

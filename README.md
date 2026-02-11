Purpose: Help those who want to connect openclaw to run large models locally, but don't know how to configure it. OpenClaw can call LM-Studio in the LAN to run large models.


Refer to openclaw.json file, openclaw.json is the configuration file of what model openclaw uses.


1. openclaw.json stored in the /home/your_user_name/.openclaw/ path, you can replace your existing openclaw.json files for the first time. If not satisfied, you can run the openclaw onboard command to reconfigure the lobster once.

 2. "baseUrl": "http://192.168.0.12:1234/v1", this is the IP address of the lmstudio machine

 3. "primary": "lmstudio/openai/gpt-oss-20b", here you write the large model you want to run, it must start with lmstudio, if you only write openai/gpt-oss-20b, an error will be reported

 4. "models": {
         "lmstudio/openai/gpt-oss-20b", here you write the large model you want to run, it must start with lmstudio, if you only write openai/gpt-oss-20b, it will report an error


5.  "models": [
          {
            "id": "gpt-oss-20b", where the name of the model is written
            "name": "gpt oss 20b", where the name of the model is written
            "reasoning": false,
            "input": [
              "text"
            ],


6. "contextWindow": 131072, 这里是上下文窗口大小，ollama官方那边建议是openclaw至少是64k以上，但是我测得的是至少13k~15k起步才能启动对话，否则会报错.64k以上应该是ollama认为可以流畅的运行的标准。
            "maxTokens": 8192  这里是最大输出，根据你的大模型性能和机器性能自行调整

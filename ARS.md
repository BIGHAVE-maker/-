```
from aip import AipSpeech
import os
def ASR_bighave():
    """ 你的 APPID AK SK """
    api_id = '15808549'
    api_key = 'vZx4GGoPo5QBe2IrNleWRMzK'
    secert_key = 'GGgxAoqyh6mgXYLGlSExRh1volpSRhy9'

    client = AipSpeech(api_id, api_key, secert_key)

    # 读取文件
    def get_file_content(filePath):
        os.system("ffmpeg -y  -i E:\python学习\socket\output.wav -acodec pcm_s16le -f s16le -ac 1 -ar 16000 E:\python学习\socket\output.pcm")
        with open(f"output.pcm", 'rb') as fp:
            return fp.read()

    # 识别本地文件
    res = client.asr(get_file_content('-output.wav'), 'pcm', 16000, {
        'dev_pid': 1537,
    })
    print(res)
    print(res["result"])
    return res["result"]
```
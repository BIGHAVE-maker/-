```
from aip import AipSpeech
def yuyinbofang(command):
    """ 你的 APPID AK SK """
    api_id = '15808549'
    api_key = 'vZx4GGoPo5QBe2IrNleWRMzK'
    secert_key = 'GGgxAoqyh6mgXYLGlSExRh1volpSRhy9'

    client = AipSpeech(api_id, api_key, secert_key)

    # 读取文件
    def get_file_content(filePath):
        with open(filePath, 'rb') as fp:
            return fp.read()

    result  = client.synthesis(command, 'zh', 1, {
        'vol': 5,
        'spd': 4,
        'pit': 6,
        'per': 4,
    })
    #保存文件
    with open("yuyin.wav", 'wb') as fp:
        fp.write(result)
```
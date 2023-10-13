## 数据来源

- data目录 原始数据来源于github项目：[chinese-poetry](https://github.com/chinese-poetry/chinese-poetry)

## 主要工作

- 统一字体
    - 繁体转简体（注意少数生僻字仍保留繁体，以便在Linux和Android系统中正常显示）
    - 英文标点转中文标点

- ID映射
    - 若原始数据有id，使用该id，如《全唐诗》中id为uuid
    - 若原始数据中有序号，如《御定全唐诗》，则id定为：文件名拼音#序号
    - 其余无特殊标识，id也定为：文件名拼音#序号（序号=原始数据下标+1）

- 统一格式
  ```json
  {
    "id": "caocao#1",
    "title": "度关山",
    "author": "曹操",
    "content": "天地间，人为贵。\n立君牧民，为之轨则。\n车辙马迹，经纬四极。\n黜陟幽明，黎庶繁息。\n于铄贤圣，总统邦域。\n封建五爵，井田刑狱。\n有燔丹书，无普赦赎。\n皋陶甫侯，何有失职？\n嗟哉后世，改制易律。\n劳民为君，役赋其力。\n舜漆食器，畔者十国，\n不及唐尧，采椽不斫。\n世叹伯夷，欲以厉俗。\n侈恶之大，俭为共德。\n许由推让，岂有讼曲？\n兼爱尚同，疏者为戚。"
  }
  ```

- 修正过滤（修正或过滤标题漏字、标题错误、内容多符号、内容缺失等情况，并移除注释）
    - 南唐二主词：淘汰1首（《谢新恩·樱花落尽春将困》缺十二字）
    - 元曲：暂不处理（内容跑到标题且一部分衔接处有漏字）
    - 御定全唐诗：已过滤结尾漏句的情况，但中间漏句暂未处理
    - 纳兰性德：改为按上下阙换行，校对标点符号（严格区分逗号、句号和问号）
    - 其余见“修订记录”和“完成清单”

## 修订记录

罗列一部分对原始数据的修订（部分已提PR，标注可选的不提）：

- 水墨唐诗
    - 《田家行》 内容补充
    - 《游子吟》《鹿柴》 删除多余标点
    - 《村民苦寒》 节选补全（可选）
- 全唐诗
    - 《凉州词二首 一》 删除标题多余引号（唐诗三百首）
    - 《赠李商隐赠佳人》 删除多余左方括号（原poet.tang.51000）
    - 《次韵李久善近诗四首 其二》 “愚千慮切”改为“愚衷千虑切”（原poet.song.95000）
    - 《绿珠作诗》《又句》《桂花曲》《明德舞》 删除多余注释（poet.tang）（可选）
    - 《杜康台 一》 删除多余标点（poet.tang）（可选）
    - “〖〗” 删除作者中的该字符（poet.tang）（可选）
    - “赠樊川长老。” 删除该首（poet.tang）（可选）
    - 《送东林廉上人还庐》 删除该首（poet.tang）（可选）
    - 张司马、王严光、徐源 删除作者简介篇章（poet.tang）（可选）
    - 《望秦川歌 其一》《题大着肚并引 其一》 过滤（poet.song）（可选）
- 宋词三百首
    - “蓦然回首，那人却在，□□阑珊处” 改为“蓦然回首，那人却在，灯火阑珊处”
    - “雕弓ㄇ柳” 改为“雕弓笮柳”
- 宋词
    - 《“僮至”念奴娇》 改为《百字令》，修正作者为俞处俊（可选）
- 曹操诗集
    - “心意怀？豫”改为“心意怀犹豫”
- 花间集
    - “纤B*理宿妆” 改为“纤珪理宿妆”
    - 《菩萨蛮 其一》《菩萨蛮 其五》 删除多余空格
- 纳兰性德
    - 《木兰花·令拟古决绝词》 改为《木兰花令·拟古决绝词》
    - 《浣溪沙·旋拂轻容写》 改为《浣溪沙·旋拂轻容写洛神》
    - 《浣溪沙·谁道飘零不可怜》 序“西郊冯氏园看海棠，因忆《香严词》有感”改至标题（可选）
    - 《一络索·野火拂云微绿》 改为《一络索·长城》（可选）
    - 《清平乐·才听夜雨》 改为《清平乐·忆梁汾》（可选）
    - “朔风吹古柳” 补标题《拟古》（可选）

## 完成清单

数量统计格式：本仓库录用数 / 原始数据数（若全部录用，省略原始数据数）

- 诗经 305
- 楚辞 65
- 曹操诗集 26
- 水墨唐诗 176
- 全唐诗
    - 唐诗三百首 366
    - 唐诗补录 1
    - 唐 56320 -5 / 57607
    - 宋 250351 / 254248
- 御定全唐诗 40552 / 43103
- 五代诗词
    - 花间集 497
    - 南唐二主词 44 / 45
- 宋词
    - 宋词三百首 280
    - 宋 19990 / 21053
- 纳兰性德 258
- 幽梦影 219
- 论语 20
- 四书五经
    - 大学 1
    - 孟子 14
    - 中庸 1
- 蒙学（完成部分）
    - 百家姓 1
    - 千字文 1
    - 三字经 2
    - 朱子家训 1
    - 弟子规 8
    - 增广贤文 2
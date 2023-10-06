# llm-dataset-chinese-poetry

## 数据来源

- data目录 原始数据来源于github项目：[chinese-poetry](https://github.com/chinese-poetry/chinese-poetry)

## 主要工作

- 统一字体
    - 繁体转简体（注意少数生僻字仍保留繁体，以便在Linux和Android系统中正常显示）
    - 英文标点转中文标点

- 统一格式
  ```json
  {
    "title": "度关山",
    "author": "曹操",
    "content": "天地间，人为贵。\n立君牧民，为之轨则。\n车辙马迹，经纬四极。\n黜陟幽明，黎庶繁息。\n于铄贤圣，总统邦域。\n封建五爵，井田刑狱。\n有燔丹书，无普赦赎。\n皋陶甫侯，何有失职？\n嗟哉后世，改制易律。\n劳民为君，役赋其力。\n舜漆食器，畔者十国，\n不及唐尧，采椽不斫。\n世叹伯夷，欲以厉俗。\n侈恶之大，俭为共德。\n许由推让，岂有讼曲？\n兼爱尚同，疏者为戚。"
  }
  ```

- 校对过滤（标题漏字，缺少标题，标题错误，内容多符号，内容缺失等）
    - 南唐二主词 淘汰1首（《谢新恩·樱花落尽春将困》缺十二字）
    - 元曲 全部淘汰（内容跑到标题且一部分衔接处有漏字）
    - 其余见“修订记录”和“完成清单”

## 修订记录

罗列一部分对原始数据的修订：

- 水墨唐诗：《田家行》内容补充
- 宋词：“蓦然回首，那人却在，□□阑珊处”改为“蓦然回首，那人却在，灯火阑珊处”
- 曹操诗集：“心意怀？豫”改为“心意怀犹豫”
- 花间集：“纤B*理宿妆”改为“纤珪理宿妆”
- 纳兰性德
    - 《浣溪沙·咏五更，和湘真韵》和《菩萨蛮·过张见阳山居，赋赠》移除标题逗号
    - 《木兰花·令拟古决绝词》改为《木兰花·拟古决绝词柬友》
    - 《浣溪沙·旋拂轻容写》改为《浣溪沙·旋拂轻容写洛神》
    - 《浣溪沙·谁道飘零不可怜》移除开头“西郊冯氏园看海棠，因忆《香严词》有感”
    - 《拟古》补充标题
- 全唐诗
    - 《赠李商隐赠佳人》 删除多余方括号（poet.tang.51000.json）
    - 《绿珠作诗》《又句》《桂花曲》《明德舞》 删除多余注释
    - 《杜康台 一》 删除多余标点

## 完成清单

数量统计格式：本仓库录用数 / 原始数据数（若全部录用，省略原始数据数）

- 曹操诗集 26
- 幽梦影 219
- 纳兰性德 258
- 五代诗词
    - 花间集 497
    - 南唐二主词 44 / 45
- 诗经 305
- 全唐诗
    - 唐诗三百首 366
    - 唐诗补录 1
    - 唐 56326 / 57607 （有过滤几篇作者简介，数量未扣除）
    - 宋 250352 / 254248
- 御定全唐诗 40552 / 43103
- 宋词（完成部分）
    - 宋词三百首 280
- 水墨唐诗 176
- 论语 20
- 蒙学（完成部分）
    - 百家姓 1
    - 千字文 1
    - 三字经 2
    - 朱子家训 1
- 四书五经
    - 大学 1
    - 孟子 14
    - 中庸 1
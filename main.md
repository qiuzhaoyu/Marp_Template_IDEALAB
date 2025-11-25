---
marp: true
paginate: true
size: 16:9

# 默认为 bg2，当中所有页都用它
backgroundImage: url("backgrounds/bg2.png")
backgroundSize: cover

style: |
  section {
    font-family: "Times New Roman", Times, serif;
    font-size: 36px;
    color: #ffffff;
    line-height: 1.6;
    position: relative;
  }

  h1, h2, h3, h4, h5, h6 {
    font-family: "Times New Roman", Times, serif;
    color: #ffff00;
  }



  caption {
    font-family: "Times New Roman", Times, serif;
    color: #ffff00;
  }

  /* 首页标题 h1：中心点绝对定位 */
  section h1 {
    font-size: 47px;
    position: absolute;
    text-align: center;
    top: 30%;
    left: 50%;
    width: 90%; 
    transform: translate(-50%, -50%);
    margin: 0;
  }


    /* 首页 subtitle 居中 (Author / Affiliation / Date) */
    .subtitle-block {
    margin-top: 160px;
    text-align: center;
    font-family: "Times New Roman", serif;
    color: #ffffff;
    }

    /* 作者名：稍大、加粗 */
    .subtitle-block .name {
    font-size: 40px;
    font-weight: bold;
    margin-bottom: 10px;
    }

    /* 单位：减小字号、行距更紧凑 */
    .subtitle-block .affiliation {
    font-size: 33px;
    line-height: 1.3;
    opacity: 0.9;
    margin: 2px 0;
    }

    /* 日期：更小、弱化 */
    .subtitle-block .date {
    font-size: 30px;
    opacity: 0.75;
    margin-top: 12px;
    }


    /* 中间页 h2 精确定位 */
  section h2 {
    font-size: 36px;
    position: absolute;
    width: 100%; 
    top: 5%;
    left: 2%;
    margin: 0;
  }

  /* 页码绝对位置 */
  section::after {
    content: attr(data-marpit-pagination) " / " attr(data-marpit-pagination-total);
    position: absolute;
    bottom: 9px;
    right: 140px;
    font-size: 30px;
    color: #ffffff;
  }



  /* Thanks 页面标题（花体 + 黄字 + 居中） */
    /* 副标题花体 */
    .thanks-msg {
    font-family: "Brush Script MT", "Lucida Handwriting", "Zapfino", cursive;
    font-size: 130px;
    color: #ffff00;
    text-align: center;
    margin-top: 0;
    }

    /* 底部联系信息正常字体 */
    .thanks-info {
    font-family: "Times New Roman", serif;
    text-align: center;
    font-size: 25px;
    color: #ffffff;
    margin-top: 20px;
    line-height: .8;
    }

    /* 邮箱加粗 */
    .thanks-info p:first-child {
    font-weight: bold;
    font-size: 38px;
    }

    /* 其他信息半透明 */
    .thanks-info p:not(:first-child) {
    opacity: 0.65;   /* 可自行调节 0.5～0.8 */
    line-height: .6;
    }

    .two-col-6040 {
    display: grid;
    grid-template-columns: 60% 40%;
    align-items: center;
    column-gap: 40px;
    }


    .center_custom_70 {
        position: absolute;
        width: 70%;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);

        display: flex;              /* 关键：让容器变成 Flex */
        flex-direction: column;     /* 图片 + caption 垂直排列 */
        align-items: center;        /* 水平居中 */
        justify-content: center;    /* 垂直方向（容器内部）居中 */
    }

    .left_custom_60 {
        position: absolute;
        width: 60%;
        left: 3%;
        top: 50%;
        transform: translateY(-50%);

        display: flex;              /* 关键：让容器变成 Flex */
        flex-direction: column;     /* 图片 + caption 垂直排列 */
        align-items: center;        /* 水平居中 */
        justify-content: center;    /* 垂直方向（容器内部）居中 */
    }

    .right_word {
        position: absolute;
        width: 33%;
        left: 65%;
        top: 50%;
        transform: translateY(-50%);

        display: flex;              /* 关键：让容器变成 Flex */
        flex-direction: column;     /* 图片 + caption 垂直排列 */
        align-items: left;        /* 水平居中 */
        justify-content: center;    /* 垂直方向（容器内部）居中 */
    }

---

<!-- 首页：用 bg1 + 单独 class --> 
<!-- _backgroundImage: url("backgrounds/bg1.png") --> 
<!-- _backgroundSize: cover -->

# Helping Patients Understand Their Images:<br>Sentence-to-Lesion Grounding in Multimodal Brain MRI



<div class="subtitle-block">
  <p class="name">Zhaoyu Qiu</p>

  <p class="affiliation">School of Biomedical Engineering</p>
  <p class="affiliation">ShanghaiTech University</p>
  <p class="affiliation">United Imaging Intelligence Co., Ltd.</p>

  <p class="date">November xxx, 2025</p>
</div>


---
## 中间页 1111（标题精确定位）

<div class="center_custom_70">
  <img src="assets/dpo.svg" style="display:inline-block; width:80%;">
  sssssssssssssssssssssssssssssssss
</div>

---

## 中间页 222（标题精确定位

<div class="left_custom_60">
    <img src="assets/dpo.svg" alt="">
    <div class="caption">This is a caption</div>
</div>

<div class="right_word">

```python
import torch
print(torch.cuda.is_available())
```

右侧文字

```python
from transformers import AutoModelForMaskedLM, AutoTokenizer
model = AutoModelForMaskedLM.from_pretrained("cl-tohoku/bert-base-japanese-whole-word-masking")
tokenizer = AutoTokenizer.from_pretrained("cl-tohoku/bert-base-japanese-whole-word-masking")

inputs = tokenizer.encode_plus("私はとても[MASK]です。", return_tensors='pt')
outputs = model(**inputs)
tokenizer.convert_ids_to_tokens(outputs.logits[0][1:-1].argmax(axis=-1))
```

sssss
sssssss
ssss

</div>



---

## 中间页 3333（标题精确定位）

<div class="two-col-6040" style="margin-top:10px;">
  <div style="text-align:center;">
    <img src="assets/dpo.svg" style="width:100%;" />
    <div style="font-size:26px; color:#ffff00; margin-top:10px;">
      图 1. DPO 示意图
    </div>
  </div>

  <div>
    <h3>标题</h3>
    <p>这里是右侧文字。</p>
    <p>这里是右侧文字。</p>
    <p>这里是右侧文字。</p>
  </div>
</div>



---

<!-- 尾页：用 bg3 -->
<!-- _backgroundImage: url("backgrounds/bg3.png") --> 
<!-- _backgroundSize: cover -->



<div class="thanks-msg">
  Thanks!
</div>

<div class="thanks-info">
  <p>qiuzhaoyu@shanghaitech.edu.cn</p><br>
  <p>School of Biomedical Engineering</p>
  <p>ShanghaiTech University</p>
  <p>United Imaging Intelligence Co., Ltd.</p><br>

</div>

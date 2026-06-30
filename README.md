# journal-android-multilingual-ext_template

journal-android-multilingual-ext_template is the template of [extension pack](https://github.com/LoliLin/journal-android-multilingual/blob/main/docs/extension-pack-protocol.md) of [journal-android-multilingual](https://github.com/LoliLin/journal-android-multilingual)

Extension pack is currently add new substances and i18n as a set, following structure:

```
extension_pack.zip
├── manifest.json
├── substances/
│   ├── zh_cn/   
│   │   └── MyNewDrug.json
│   └── en_us/
│       └── MyNewDrug.json
└── i18n/
    └── en_us.json 
```

## manifest.json 
```json
{
  "registerName": "my_extension",
  "titleTranslateable": "ext_my_title",
  "descriptionTranslateable": "ext_my_desc",
  "officalLink": "https://example.com/my-extension",
  "updateJsonLink": "https://example.com/update.json",
  "versionName": "1.0.0",
  "versionCode": 1
}
```
the `registerName` is the **Unique** indentifer for the extension pack, it should be unique and static.  
the `titleTranslatable` is the translate key of the title. Of course you could define the key in your i18n dir.  
the `descriptionTranslateable` is the translate key of the description.    
the `officalLink` is your link of extension  
the `updateJsonLink` is the link of the **UpdateJson**  
the `versionName` is the display version
the `versionCode` is the compareable version

## UpdateJson
```json
{
  "2": {"versionName": "2.0.0", "url": "https://example.com/ext_v2.0.0.zip"}
}
```

```
{
 "<versionCode>": {
    "versionName": "<versionName>",
    "url": "<directDownloadUrl>"
`}  .. and so on
}
```

## i18n

i18n is a json with locase code  
e.g. en_us.json  
there  
```json
{
  "<key>": "<value>"
}
```

## substances
substances has the mulit layers
### root
Under `substances/root/`   
the json file must named as <UniqueSubstanceName>.json  
the name is the indentifer, for example, Alcohol.json, define a substance of `Alcohol`
```json
{
  "name": "Alcohol",
  "commonNames": [
    "Alcohol",
    "Booze",
    "Liquor",
    "Moonshine",
    "Sauce",
    "Juice",
    "Bevvy"
  ],
  "url": "https://psychonautwiki.org/wiki/Alcohol",
  "isApproved": true,
  "tolerance": {
    "full": "develops with prolonged and repeated use",
    "half": "3 - 7 days",
    "zero": "1 - 2 weeks",
    "halfToleranceInHours": 120,
    "zeroToleranceInHours": 252
  },
  "crossTolerances": [
    "GABA",
    "depressants"
  ],
  "addictionPotential": "extremely addictive with a high potential for abuse",
  "toxicities": [
    "Death from ethanol consumption is possible when blood alcohol levels reach 0.4%"
  ],
  "categories": [
    "depressant",
    "habit-forming",
    "common"
  ],
  "summary": "Alcohol is a CNS depressant that acts through the GABAₐ receptor, and is one of the most common strong psychoactives used by humans. It has a long history of use and its intoxicating effects are well-studied and documented. It remains legal in most parts of the world.",
  "effectsSummary": "Stimulation, relaxation, calming down, disinhibition, sociability, euphoria, reduction of the ability to react, overestimation of oneself and urge to talk, but also melancholy or irritability up to aggressiveness.\nAbsinthe (\"The Green Fairy\"), a high-proof spirit (usually 50 - 70 % by volume), contains the plant substance thujone. Together with the main active ingredient alcohol, thujone is said to have stimulating and mind-altering effects. In Europe, as in Switzerland, clear limits apply (max. 35 mg thujone per kg alcohol). Caution with chronic use! A thujone overdose manifests itself in seizures and epilepsy-like symptoms.",
  "dosageRemark": "Standard drinks such as 3 dl beer, 1 dl wine or 2 cl spirits contain about 12 g alcohol. The effect of alcohol is influenced by the amount consumed, the type of alcohol (sugary and/or carbonated), the period of consumption and individual factors (age, sex, weight). The blood alcohol concentration is measured in parts per thousand (‰). The higher the alcohol concentration in the blood, the stronger the effect of alcohol.",
  "generalRisks": "Small amounts of alcohol generally have a relaxing and exhilarating effect, a general feeling of well-being spreads, fears are reduced and sociability increases. The consumption of larger amounts can lead to balance and speech disorders, visual disturbances (double vision or tunnel vision), stomach pain, nausea to vomiting, headaches (hangover) due to dehydration, loss of control and blackouts. There is a risk of accidents due to overestimation of one's own abilities and reduced ability to react. High doses can lead to hypothermia or overheating, deep sleep and coma. Very high doses (blood alcohol concentration of 3-4‰) can be life-threatening.\nBinge drinking, i.e. the consumption of a large amount of alcohol in a very short time, causes the blood alcohol content to rise particularly quickly and strongly. This can quickly lead to alcohol poisoning. Consequences can be: comatose state, memory lapses (film tears), deactivation of important reflexes (danger of choking when vomiting, danger of freezing to death when cold) as well as epileptic seizures. There is also an increased risk of thrombosis, high or low blood pressure, respiratory depression and sudden cardiac death.",
  "longtermRisks": "Since alcohol is a cytotoxin, regular heavy consumption can have consequences such as damage to all bodily organs, deficiency symptoms, disorders of the nervous system, coordination of movement and memory functions, and even alcohol-induced dementia. Alcohol is a co-carcinogen, i.e. it significantly increases the carcinogenic effect of other substances (e.g. nicotine).\nAlcohol can produce a dependence with psychological and physical symptoms. Typical withdrawal symptoms are trembling, sweating, nausea and vomiting up to epileptic seizures. On a psychological level, irritability, anxiety disorders, depressive moods and hallucinations may occur. Tolerance develops with regular consumption.",
  "saferUse": [
    "Do not consume alcohol out of boredom or when you feel bad.",
    "Drink alcohol with pleasure and take your time.",
    "Do not drink alcohol on an empty stomach.",
    "Avoid mixed consumption of different alcoholic drinks, drink water with it (e.g. a glass of water after each alcoholic drink).",
    "Be careful with mixed drinks (e.g. alcopops) or self-mixed drinks! With these sweet drinks you can hardly taste the alcohol, even though a 3-litre bottle contains about two schnapps. The danger of an unintentional overdose is high.",
    "In general, refrain from consuming alcohol if you consume other psychoactive substances; their effect is altered by the alcohol, or sometimes life-threatening side effects occur (e.g. alcohol and GHB = danger of suffocation!).",
    "If you drink, you don't drive. Use public transport, take a taxi or walk.",
    "Alcohol consumption during pregnancy is a risk for the foetus. Severe damage to the child can be the result.",
    "Follow the safe sex rules even when under the influence of alcohol."
  ],
  "interactions": {
    "dangerous": [
      "Depressants",
      "Dissociatives",
      "Benzodiazepines",
      "DXM",
      "GHB",
      "GBL",
      "Ketamine",
      "MXE",
      "Opioids",
      "Tramadol"
    ],
    "unsafe": [
      "Cocaine",
      "MAOIs",
      "PCP",
      "ALDH2 inhibitors",
      "Hepatotoxic drugs"
    ],
    "uncertain": [
      "Stimulants",
      "THC",
      "Amphetamines",
      "AMT",
      "MDMA",
      "Nitrous",
      "SSRIs"
    ]
  },
  "roas": [
    {
      "name": "oral",
      "dose": {
        "units": "g",
        "lightMin": 10,
        "commonMin": 20,
        "strongMin": 30,
        "heavyMin": 40
      },
      "duration": {
        "onset": {
          "min": 2,
          "max": 5,
          "units": "minutes"
        },
        "comeup": {
          "min": 15,
          "max": 45,
          "units": "minutes"
        },
        "peak": {
          "min": 30,
          "max": 90,
          "units": "minutes"
        },
        "offset": {
          "min": 45,
          "max": 120,
          "units": "minutes"
        },
        "total": {
          "min": 1.5,
          "max": 5,
          "units": "hours"
        },
        "afterglow": {
          "min": 6,
          "max": 48,
          "units": "hours"
        }
      }
    }
  ]
}
```
And you will put a translateable json under zh_cn like this
`substances/zh_cn/Alcohol.json`
```json
{
  "tolerance": {
    "full": "长期反复使用后形成",
    "half": "3 - 7天",
    "zero": "1 - 2周",
    "halfToleranceInHours": 120,
    "zeroToleranceInHours": 252
  },
  "addictionPotential": "极易上瘾，具有很高的滥用潜力",
  "toxicities": [
    "当血液酒精浓度达到0.4%时，饮用乙醇可能导致死亡。"
  ],
  "summary": "酒精是一种通过GABAₐ受体起作用的CNS抑制剂，是人类最常用的强效精神活性物质之一。其使用历史悠久，醉人效果已被充分研究和记录。在世界上大部分地区，它仍然是合法的。",
  "effectsSummary": "刺激、放松、镇静、解除抑制、社交性、欣快感、反应能力下降、自我高估与倾诉欲增强，但也可能引发忧郁、易怒甚至攻击性。  \n苦艾酒（\"绿色精灵\"）是一种高度烈酒（通常酒精含量为50%-70%），含有植物成分侧柏酮。据称侧柏酮与主要活性成分酒精共同作用，会产生刺激和改变心智的效果。在欧洲（包括瑞士），有明确的限量标准（每公斤酒精中侧柏酮含量不得超过35毫克）。长期使用需谨慎！侧柏酮过量会表现为痉挛及类似癫痫的症状。",
  "dosageRemark": "标准饮品如3分升啤酒、1分升葡萄酒或2分升烈酒约含12克酒精。酒精的作用受摄入量、酒精类型（含糖和/或碳酸饮料）、饮用时间及个体因素（年龄、性别、体重）影响。血液酒精浓度以千分比（‰）计量。血液中酒精浓度越高，酒精作用越强。",
  "generalRisks": "少量酒精通常会产生放松和兴奋的效果，带来普遍的幸福感，减少恐惧并增强社交能力。大量饮酒可能导致平衡和语言障碍、视觉紊乱（复视或管状视野）、胃痛、恶心至呕吐、因脱水引起的头痛（宿醉）、失控和记忆中断。由于高估自身能力和反应能力下降，存在发生事故的风险。高剂量可能导致体温过低或过高、深度睡眠和昏迷。极高剂量（血液酒精浓度达3-4‰）可能危及生命。\n\n狂饮，即在极短时间内摄入大量酒精，会导致血液酒精含量迅速且剧烈上升，可能快速引发酒精中毒。后果可能包括：昏迷状态、记忆缺失（片段性失忆）、重要反射功能丧失（呕吐时窒息风险、寒冷时冻死风险）以及癫痫发作。此外，血栓形成、高血压或低血压、呼吸抑制和心源性猝死的风险也会增加。",
  "longtermRisks": "由于酒精是一种细胞毒素，长期大量饮用会对身体各器官造成损害，引发营养缺乏症状，导致神经系统、运动协调能力和记忆功能紊乱，甚至诱发酒精性痴呆。酒精是辅助致癌物，即它会显著增强其他物质（如尼古丁）的致癌作用。  \n酒精可导致心理和生理双重依赖。典型的戒断症状包括震颤、出汗、恶心呕吐，严重时甚至出现癫痫发作。在心理层面，可能出现易怒、焦虑障碍、抑郁情绪和幻觉。长期饮酒还会产生耐受性。",
  "saferUse": [
    "不要因为无聊或心情不好而饮酒。",
    "饮酒尽兴，且从容。",
    "请勿空腹饮酒。",
    "避免混合饮用不同种类的酒精饮料，饮酒时搭配喝水（例如每喝完一杯酒精饮料后喝一杯水）。",
    "注意混合饮品（如酒精汽水）或自调饮品！这些甜味饮料几乎尝不出酒精味，但一瓶三升装的饮品中约含两杯烈酒的酒精量。无意中过量饮用的风险很高。",
    "一般来说，若服用其他精神活性物质，应避免饮酒；酒精会改变其药效，有时甚至引发危及生命的副作用（例如酒精与GHB同服=窒息危险！）。",
    "喝酒不开车。请使用公共交通、打车或步行。",
    "孕期饮酒对胎儿有风险，可能导致孩子遭受严重伤害。",
    "即使在酒精影响下，也要遵守安全性行为规则。"
  ],
  "localizedName": "酒精"
}
```
### interactions
there are three interactions type here, `dangerous`, `unsafe` and `uncertain`
### roas
there are roa types here
```java
    ORAL
    SUBLINGUAL
    BUCCAL
    INSUFFLATED
    RECTAL
    TRANSDERMAL
    SUBCUTANEOUS
    INTRAMUSCULAR
    INTRAVENOUS
    SMOKED 
    INHALED
```
and roa dose
```java
data class RoaDose(
    val units: String,
    val lightMin: Double?,
    val commonMin: Double?,
    val strongMin: Double?,
    val heavyMin: Double?,
) 
```

```java
data class RoaDuration(
    val onset: DurationRange?,
    val comeup: DurationRange?,
    val peak: DurationRange?,
    val offset: DurationRange?,
    val total: DurationRange?,
    val afterglow: DurationRange?
)
```

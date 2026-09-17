# Who's Your Dad?

接住爹地灑下來的小費，但小心那盒適尿通。

線上遊玩：https://aether-tek.github.io/whos-your-dad/

## 檔案結構

```
index.html        遊戲本體（HTML + CSS + JS）
assets/
  background.png  麵包店背景
  boss1~9.png     爹地的九種髮量狀態
  bill1~100.png   七種面額鈔票
  pill.png        適尿通藥盒
  win.mp4         三關全過的慶祝影片
```

## 常見修改

關卡難度全部集中在 `index.html` 的 `LEVELS` 陣列（第 393 行）：

| 參數 | 意義 |
|---|---|
| `time` | 關卡秒數 |
| `target` | 過關所需金額 |
| `pill` | 適尿通出現機率（0~1） |
| `spawn` | 掉落物生成間隔（毫秒，越小越密） |
| `bossMove` | 爹地移動間隔（毫秒，越小越跳） |
| `speedBase` | 基礎落下速度 |
| `drift` | 斜線幅度，0 為垂直 |
| `speedMul` | 速度倍率 |
| `junk` | 是否出現小面額干擾鈔 |

`WIN_AFTER_LEVEL` 控制第幾關過關後播放影片，測試時可改成 `0`（第一關就播）。

## 遊戲規則

- 接到 $10 / $50 / $100 加對應分數
- 接到適尿通扣 50 分，爹地髮量 +1（分數可扣成負數）
- 髮量整場累積，不因過關或重玩而重置
- 髮量 9/9 時再接到適尿通 → 直接結束
- 沒達標則該關分數歸零重來，髮量不還

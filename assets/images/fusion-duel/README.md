# Fusion Duel：Classic 重用與同風格擴充

2026-11-08（Asia/Hong_Kong）。Classic 既有素材僅機械裁切／縮放；新增九個素材來自 Root 另行生成的 Higgsfield GPT Image 2.5 Atlas。本匯出不呼叫生成服務，不重畫、鏡像或重新染色。

| Fusion bitmap | 類型 | 來源 | 加工 |
| --- | --- | --- | --- |
| fire-1.webp | Classic 重用 | public/assets/images/first-lesson-polish/fire-i-v001.webp | Alpha crop + normalization |
| fire-2.webp | Classic 重用 | public/assets/images/first-lesson-polish/fire-ii-v001.webp | Alpha crop + normalization |
| wind-1.webp | Classic 重用 | public/assets/images/duel-concepts/wind-i-v001.webp | Alpha crop + normalization |
| wind-2.webp | Classic 重用 | public/assets/images/duel-concepts/wind-ii-v001.webp | Alpha crop + normalization |
| water-1.webp | Classic 重用 | public/assets/images/levels-4-to-8/water-i-v001.webp | Alpha crop + normalization |
| water-2.webp | Classic 重用 | public/assets/images/levels-4-to-8/water-ii-v001.webp | Alpha crop + normalization |
| fire-producer.webp | Classic 重用 | public/assets/images/first-lesson-polish/training-wand-v001.webp | Alpha crop + normalization |
| wind-producer.webp | Classic 重用 | public/assets/images/first-lesson-polish/training-wand-v001.webp | Alpha crop + normalization |
| water-producer.webp | Classic 重用 | public/assets/images/first-lesson-polish/training-wand-v001.webp | Alpha crop + normalization |
| spellbook.webp | Classic 重用 | public/assets/images/first-lesson-polish/incendio-spellbook-v001.webp | Alpha crop + normalization |
| hogwarts-crest.webp | Classic 重用 | public/assets/images/first-lesson-polish/hogwarts-crest-official-v001.webp | Alpha crop + normalization |
| gryffindor-lion.webp | Classic 重用 | public/assets/images/first-lesson-polish/gryffindor-lion-official-v001.webp | Alpha crop + normalization |
| recovery-potion.webp | Classic 重用 | public/assets/images/first-lesson-polish/recovery-potion-v001.webp | Alpha crop + normalization |
| enemy-1.webp | Classic 重用 | public/assets/images/duel-concepts/practice-automaton-v001.webp | Alpha crop + normalization |
| enemy-2.webp | Classic 重用 | public/assets/images/duel-concepts/enchanted-armour-v001.webp | Alpha crop + normalization |
| enemy-3.webp | Classic 重用 | public/assets/images/levels-4-to-8/armour-captain-v001.webp | Alpha crop + normalization |
| fire-3.webp | 新增同風格 Atlas | assets/generated/images/fusion-duel/advanced-elements-atlas-v001.png | Alpha crop + normalization |
| fire-4.webp | 新增同風格 Atlas | assets/generated/images/fusion-duel/advanced-elements-atlas-v001.png | Alpha crop + normalization |
| wind-3.webp | 新增同風格 Atlas | assets/generated/images/fusion-duel/advanced-elements-atlas-v001.png | Alpha crop + normalization |
| wind-4.webp | 新增同風格 Atlas | assets/generated/images/fusion-duel/advanced-elements-atlas-v001.png | Alpha crop + normalization |
| water-3.webp | 新增同風格 Atlas | assets/generated/images/fusion-duel/advanced-elements-atlas-v001.png | Alpha crop + normalization |
| water-4.webp | 新增同風格 Atlas | assets/generated/images/fusion-duel/advanced-elements-atlas-v001.png | Alpha crop + normalization |
| shield.webp | 新增同風格 Atlas | assets/generated/images/fusion-duel/advanced-elements-atlas-v001.png | Alpha crop + normalization |
| spellbook-advanced.webp | 新增同風格 Atlas | assets/generated/images/fusion-duel/advanced-elements-atlas-v001.png | Alpha crop + normalization |
| coins.webp | 新增同風格 Atlas | assets/generated/images/fusion-duel/advanced-elements-atlas-v001.png | Alpha crop + normalization |
| stage.webp | Classic 重用 | public/assets/images/first-lesson-polish/charms-classroom-stage-v001.webp | Byte-for-byte copy; no crop or resize |

三個 Producer 使用完全相同的 Training Wand，Element 標籤／底座由 UI 區分。原 `spellbook.webp` 保留已核可 Fire 封面；新增 `spellbook-advanced.webp` 是獨立進階書籍，沒有覆寫原書籍。

新增 Atlas 順序：第一列 Fire III／Fire IV／Wind III；第二列 Wind IV／Water III／Water IV；第三列 Shield／Advanced Spellbook／Coins。Wind III 實際伸至 y687，首列 crop 高度710px；其下 Water IV 從 y710 開始，避免鄰格殘片。其餘按3×3格分割。原圖保留 genuine Alpha。

新增圖 Prompt／參數：`assets/prompts/fusion-duel/advanced-elements-v001.json`；Job `98e3d4a7-1e93-4204-9f73-948bdb3e8437`。

Harry 直接使用原 `HarryActor` 與 S11 `harry-extended-casting-atlas-v007.webp`，右手序列0／1／5／4／4／5；Wand tip97.136%／31.115%，本匯出不改角色 Atlas。

裁切、Alpha 實際 bounds 及所有 Classic 來源前後 SHA256 見 `output/reports/2026-11-08-s13-art-export.json`。固定6%外圍留白配合8px原圖保護邊，使主要內容約80–87%；改善 Fire 的內縮，原本已很滿的 Wind II／Water II 略縮。薄 Wand 面積本來較小，請用清楚 Producer 底座及 Element badge 輔助辨識。

已目視九張新增輸出：主體輪廓完整，沒有鄰格實體碎片；九張正式圖最外緣 alpha>95 像素數皆0。生成的低Alpha光暈／淺色抗鋸齒邊在黑底放大仍可見，Shield／Advanced Book亦有matte邊；沒有重畫或去光暈。遊戲內parchment實際尺寸需另行複核，不能把素材裁切檢查視為完美美術驗收。

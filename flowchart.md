graph TD
    Start[機水電設備安裝<br>配管、配線施工] --> Check1{施工檢驗}
    
    %% 右側文件
    Doc1[自主檢查表] -.-> Check1
    
    %% 主流程
    Check1 -- 合格 --> Test[測試調整 單體試車]
    Test --> OwnerCheck{業主/監造單位檢驗}
    OwnerCheck -- 合格 --> Docs[測試、試運轉、檢查記錄、教育訓練<br>竣工圖及操作維修手冊製作]
    Docs --> FinalCheck[完工驗收]
    FinalCheck --> Handover[移交接管]

    %% 右側文件連接
    Doc2[自主檢查表] -.-> Test
    Doc3[測試記錄表] -.-> Test
    Doc4[設備數量清單] -.-> FinalCheck
    Doc5[移交清冊] -.-> Handover

    %% 左側修正迴圈
    Check1 -- 不合格 --> Fix[修改/重作]
    OwnerCheck -- 不合格 --> Fix
    Fix --> ReCheck{複檢}
    ReCheck -- 不合格 --> Fix
    ReCheck -- 合格 --> Test

    %% 樣式標記
    style Check1 stroke-width:4px,stroke:blue
    style OwnerCheck stroke-width:4px,stroke:blue

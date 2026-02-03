graph TD
    %% --- 主流程節點 ---
    Start[機水電設備安裝<br>配管、配線施工] --> Check1{施工檢驗}
    
    %% --- 檢驗與測試 ---
    Check1 -- 合格 --> Test[測試調整 <br>單體試車]
    Test --> OwnerCheck{業主／監造單位檢驗}
    
    %% --- 後續文件與移交 ---
    OwnerCheck -- 合格 --> Docs[測試、試運轉、檢查記錄、教育訓練<br>竣工圖及操作維修手冊製作]
    Docs --> FinalCheck[完工驗收]
    FinalCheck --> Handover[移交接管]

    %% --- 右側對應文件 (虛線連接) ---
    Doc1[自主檢查表] -.-> Check1
    Doc2[自主檢查表] -.-> Test
    Doc3[測試記錄表] -.-> Test
    Doc4[設備數量清單] -.-> FinalCheck
    Doc5[移交清冊] -.-> Handover

    %% --- 左側不合格修正迴圈 ---
    Check1 -- 不合格 --> Fix[修改／重作]
    OwnerCheck -- 不合格 --> Fix
    Fix --> ReCheck{複檢}
    
    ReCheck -- 不合格 --> Fix
    ReCheck -- 合格 --> Test

    %% --- 樣式設定 ---
    %% 標記重點檢驗點 (原圖的星號處) 為藍色粗框
    style Check1 stroke-width:4px,stroke:#0000FF
    style OwnerCheck stroke-width:4px,stroke:#0000FF
    
    %% 設定文件框為虛線樣式
    style Doc1 stroke-dasharray: 5 5
    style Doc2 stroke-dasharray: 5 5
    style Doc3 stroke-dasharray: 5 5
    style Doc4 stroke-dasharray: 5 5
    style Doc5 stroke-dasharray: 5 5

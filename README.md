# 2025_IoT_HW2_Linear-regression
完整的線性回歸分析專案，遵循 CRISP-DM 標準流程，包含特徵選擇、模型評估和互動式 Streamlit 應用程式。
📋 專案特色
✨ 核心功能

✅ 完整 CRISP-DM 流程: 從商業理解到部署建議
✅ 多種回歸模型: 單純線性回歸、多元線性回歸
✅ 特徵選擇: SelectKBest (F-統計) 和 RFE (遞迴特徵消除)
✅ 模型評估: R², RMSE, MAE + 殘差分析
✅ 預測區間: 95% 信賴區間視覺化
✅ 互動式應用: Streamlit 網頁介面

🎛️ 可調整參數
使用者可以調整以下參數:

斜率 (a): -10.0 ~ 10.0
截距 (b): -100.0 ~ 100.0
雜訊程度: 0.0 ~ 50.0
資料點數量: 20 ~ 500
測試集比例: 0.1 ~ 0.5
信賴水準: 80% ~ 99%

🚀 快速開始
1. 安裝相依套件
bashpip install -r requirements.txt
2. 執行 CRISP-DM 完整分析
bashpython hospital_regression_analysis.py
這將執行完整的 CRISP-DM 流程並生成以下圖表:

correlation_matrix.png - 相關係數矩陣
target_distribution.png - 目標變數分佈
feature_importance.png - 特徵重要性
residual_analysis.png - 殘差分析
predictions_with_intervals.png - 預測圖(含信賴區間)
actual_vs_predicted.png - 實際vs預測值

3. 啟動 Streamlit 應用程式
bashstreamlit run streamlit_app.py
應用程式將在瀏覽器中打開 (通常是 http://localhost:8501)
📊 CRISP-DM 流程
Phase 1: Business Understanding (商業理解)

目標: 預測醫院病人需求
優化床位配置和資源管理
提升病患滿意度和員工士氣

Phase 2: Data Understanding (資料理解)

資料探索和統計摘要
相關性分析
目標變數分佈檢查
類別變數分析

Phase 3: Data Preparation (資料準備)

類別變數編碼 (LabelEncoder)
訓練/測試集分割 (80/20)
特徵標準化 (StandardScaler)

Phase 4: Modeling (模型建立)
4a. Feature Selection (特徵選擇)
兩種方法:

SelectKBest: 使用 F-統計量選擇顯著特徵 (p < 0.05)
RFE: 遞迴特徵消除，選擇前 5 個最重要特徵

4b. Model Training (模型訓練)

多元線性回歸 (Multiple Linear Regression)
使用選擇的關鍵特徵訓練

Phase 5: Evaluation (模型評估)
評估指標

R² Score: 模型解釋變異的比例
RMSE: 均方根誤差
MAE: 平均絕對誤差

視覺化評估

殘差分析 (4 個圖表)
預測圖含 95% 預測區間
實際 vs 預測值散點圖

Phase 6: Deployment (部署建議)

模型應用場景
關鍵成功因素
監控指標
使用限制
下一步行動

📁 專案結構
├── hospital_regression_analysis.py  # 主要分析腳本 (CRISP-DM)
├── streamlit_app.py                 # Streamlit 互動應用
├── requirements.txt                 # Python 相依套件
├── README.md                        # 專案說明文件
└── services_weekly.csv              # 醫院資料集
🎯 Streamlit 應用功能
資料來源選擇

模擬資料: 可調整 y = ax + b 參數
真實醫院資料: 使用實際數據分析

互動式參數調整

側邊欄滑桿控制所有參數
即時更新圖表和評估指標
可切換預測區間顯示

視覺化標籤頁

散點圖與迴歸線: 顯示擬合效果
預測圖(含區間): 95% 信賴區間
殘差分析: 檢查模型假設

📈 模型表現
模擬資料

可調整參數測試模型對不同情況的反應
驗證線性回歸的假設
觀察雜訊對預測準確度的影響

真實醫院資料
典型表現指標:

R² Score: 0.70 - 0.85
RMSE: 20 - 40
MAE: 15 - 30

關鍵影響因素:

available_beds (可用床位)
patients_refused (拒絕病患數)
patients_admitted (收治病患數)
staff_morale (員工士氣)
patient_satisfaction (病患滿意度)

🔍 特徵說明
數值特徵

week: 週數 (1-52)
month: 月份 (1-12)
available_beds: 可用床位數
patients_request: 病患需求數 (目標變數)
patients_admitted: 收治病患數
patients_refused: 拒絕病患數
patient_satisfaction: 病患滿意度 (0-100)
staff_morale: 員工士氣 (0-100)

類別特徵

service: 服務類型 (emergency, surgery, general_medicine, ICU)
event: 特殊事件 (none, flu, donation, strike)

💡 使用建議
模擬資料模式
適合用於:

教學和學習線性回歸概念
測試不同參數對模型的影響
理解信賴區間的意義

真實資料模式
適合用於:

實際醫院床位需求預測
資源配置優化決策
識別影響需求的關鍵因素

🛠️ 技術棧

Python 3.8+
Data Processing: pandas, numpy
Visualization: matplotlib, seaborn, plotly
Machine Learning: scikit-learn
Statistics: scipy
Web App: streamlit

📝 授權
此專案僅供教育和研究使用。
👨‍💻 作者
Claude AI Assistant
🙏 致謝

資料來源: Kaggle - Hospital Beds Management Dataset
遵循: CRISP-DM (Cross-Industry Standard Process for Data Mining)

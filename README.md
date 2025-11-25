# Kaggle - Digit Recognizer (MNIST Classification)

此專案為 Kaggle 「Digit Recognizer」競賽參賽作品，透過多層感知器分類器（MLPClassifier）對 **MNIST 手寫數字影像（28×28 灰階）進行多分類辨識**，成功達到 **Kaggle Public LB 97.935% 準確率**。

---

## 專案內容概述

- **輸入資料**：MNIST 手寫數字圖片（每張 28×28，共 784 個像素值）  
- **任務類型**：0–9 共 10 類分類問題  
- **目標**：透過深度神經網路進行影像辨識並提升分類準確率  
- **核心模型**：`MLPClassifier (scikit-learn)`

---

## 方法與模型設計

###  1. 特徵處理
- 將影像像素由 `0~255` **標準化至 `[0, 1]` 區間**
- 去除無用欄位後直接餵入神經網路模型

###  2. 模型架構（MLPClassifier）
| 設定項目 | 內容 |
|----------|------|
| 隱藏層架構 | (256, 128) |
| 激活函數 | ReLU |
| 最佳化器 | Adam Optimizer |
| 正則化 | L2 (`alpha=1e-4`) |
| batch size | 256 |
| 訓練策略 | Early Stopping（避免 overfitting） |

### 3. 模型驗證
- 使用 `classification_report` 與 `confusion matrix` 分析不同數字分類效果  
- 指標包含 **precision、recall、f1-score**

---

##  模型成果

| 指標 | 表現 |
|------|------|
| **Validation Accuracy** | **≈ 97.9%** |
| **Precision / Recall** | 多數數字均 ≥ 0.95 |
| **Kaggle Public Leaderboard** | **97.935%** |

---


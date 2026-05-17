# SKILL.md - Phân tích Tác động AI lên Hiệu suất Doanh nghiệp Công nghệ

## 📋 Mô tả Nhiệm vụ
Phân tích sự phân hóa thống kê giữa các công ty công nghệ tập trung vào AI và công ty công nghệ truyền thống, sử dụng dữ liệu S&P500 và chỉ số vốn hóa thị trường.

## 🎯 Mục tiêu Phân tích
1. Xác định phân nhóm: AI-focused vs Traditional Tech
2. So sánh hiệu suất lợi nhuận giữa 2 nhóm
3. Đo lường độ biến động thị trường
4. Xây dựng mô hình định lượng giải thích tác động AI

---

## 📊 Yêu cầu Dữ liệu

### File CSV cần thiết:
- `SnP_daily_update.csv` - Dữ liệu giá lịch sử S&P500
- `scatter-data.csv` - Chỉ số tăng trưởng vốn hóa
- `Top 50 US Tech Companies 2022 - 2023.csv` - Phân loại AI vs Traditional
- `constituents-financials.csv` - Chỉ số tài chính (ROE, P/E, Revenue Growth,...)

### Cột dữ liệu mong đợi:
- `date`, `ticker`, `sector`, `ai_focus_score`
- `daily_return`, `market_cap`, `volume`
- `rnd_spending_ratio`, `ai_patents_count`

---

## 🔧 Thiết lập Môi trường

```python
# Import thư viện cốt lõi
import pandas as pd
import numpy as np
from datascience import *
import matplotlib.pyplot as plt
import seaborn as sns
from scipy import stats
from sklearn.linear_model import LinearRegression
from sklearn.preprocessing import StandardScaler
import warnings
warnings.filterwarnings('ignore')

# Cấu hình hiển thị
pd.set_option('display.max_columns', None)
plt.style.use('seaborn-v0_8-darkgrid')
%matplotlib inline
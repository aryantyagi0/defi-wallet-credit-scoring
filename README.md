# defi-wallet-credit-scoring
# 💼 DeFi Wallet Credit Scoring Engine (Aave V2)

## 📌 Project Overview
This project analyzes Aave V2 wallet behavior using historical transaction data and assigns a credit score to each wallet. The score ranges from **0 to 1000**, where:
- **Higher scores** indicate reliable, consistent, and responsible DeFi usage
- **Lower scores** reflect risky, exploitative, or bot-like behavior

---

## 🧰 Tech Stack
- Python 3
- Pandas for data processing
- Seaborn & Matplotlib for visualization
- Google Colab

---

## 📊 Features Extracted
For each wallet, we calculated the following features:
- ✅ Total Deposits
- ✅ Total Borrows
- ✅ Total Repaid
- ✅ Repay Ratio (total repaid / total borrowed)
- ✅ Borrow-to-Deposit Ratio
- ✅ Number of Liquidations
- ✅ Total Actions (activity level)
- ✅ Active Days

---

## ⚙️ Scoring Logic

We used a custom rule-based scoring function with this formula:

core = 500

200 × repay_ratio
– 100 × borrow_to_deposit_ratio
– 50 × num_liquidations

0.000000001 × total_deposits

0.000000001 × total_repaid

2 × active_days
- Scores are **capped between 0 and 1000**.
- This model prioritizes **repayment behavior**, **liquidation avoidance**, and **long-term activity**.

---

## 📈 Score Distribution

We generated a histogram using Seaborn and Matplotlib.  
Key insights:
- Most wallets fall between **500 and 1000**.
- High scores typically belong to users who repay loans consistently and stay active.
- Lower scores are linked to users with high liquidation rates or one-sided borrowing behavior.

👉 Full analysis is in `analysis.md`.

---

## 📂 How to Run

1. Open the `wallet_credit_score.ipynb` notebook in **Google Colab**
2. Upload `user-wallet-transactions.json` when prompted
3. Run all cells to:
   - Extract wallet-level features
   - Calculate credit scores
   - Save results to `wallet_scores.csv`
   - Generate a credit score distribution graph

📌 **Note:** Colab resets runtime. Re-upload the JSON file before running if needed.

---

## 📄 Output

The final output file:
- `wallet_scores.csv`: contains two columns:
  - `userWallet`
  - `credit_score` (between 0 and 1000)

---

## 📌 Dataset

Source: [Aave V2 user transactions - JSON](https://drive.google.com/file/d/1ISFbAXxadMrt7Zl96rmzzZmEKZnyW7FS/view?usp=sharing)

---

## 📬 Author

**Aryan Tyagi**  
B.Tech CSE (AI & ML), SRM Institute of Science and Technology  
GitHub: [github.com/aryantyagi](https://github.com/aryantyagi)

---


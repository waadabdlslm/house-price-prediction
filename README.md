# 🏠 Predicting Home Prices with Linear Regression

## 📌 Introduction
When buying or selling a home, one question always arises: "How much should this house cost based on its size?" While the location, condition, and amenities matter, square footage provides the fundamental starting point for valuation. 

To answer the question, I built a simple linear regression model that predicts house prices based on their size. 

---

## 🎯 Project Goals

I wanted to answer one simple question: **How much does size alone tell us about a house's price?**

Through this project, I:
- ✅ Learned to implement linear regression from scratch
- ✅ Discovered how to evaluate model performance
- ✅ Understood the limitations of single-feature prediction
- ✅ Gained practical experience with Python's data science stack

---

## 🛠️ Tools I Used 

🔢 NumPy – numerical operations and data handling

📖 Pandas – to load, clean, and explore the data

📈 Matplotlib – data visualizations

🤖 Scikit-learn – to build the regression model

---

## 📈 How I Approached the Data 

### 1. Initial Look at the Data
After a simple sweep of the data, I started with a scatter plot and  observed an obvious relationship: **bigger houses generally cost more**. In addition, the correlation I calculated at **~(0.88)** was strong and positive, meaning I could proceed with linear regression. 

### 2. Building the Model 
I used Python's Scikit-learn library to: 
- Split my data (80% for training, 20% for testing)
- Train a linear regression model
- Find the magic numbers: **β₀ = $236,000** (base price) and **β₁ = $1,285** (price per sq.ft.). These form the linear equation of:

<div align="center">

  <table>
    <tr>
      <td style="border:2px solid #ccc; padding:10px; border-radius:10px; text-align:center;">
        $$\text{price} = 236{,}000 + 1{,}285\times\text{size}$$
      </td>
    </tr>
  </table>

</div>

### 3. Results I Discovered  

**Estimated Home Values**
| Size | My Model's Prediction |
| :--- | :--- |
| **1,000 sq.ft.** | ~$1.52 million |
| **2,000 sq.ft.** | ~$2.80 million |
| **3,000 sq.ft.** | ~$4.09 million |

**Understanding the Error Metrics** 
| Metric | Result | Interpretation |
| :--- | :--- | :--- |
| **R² Score** | `0.71` | The model explains **71%** of price variation |
| **RMSE** | `~$384,966` | Average prediction error |
| **MAE** | `~239,373` | Mean absolute error |

So what does this indicate? 

**R² Score** 
- 71% of the variation in prices can be explained by house size, while 29% is due to other factors (location, condition, amenities, etc.). However, the single feature (size) has a significant predictive power 

**RMSE (Root Mean Squared Error) ~$384,966**
- This is used to summarize "how far off" our predictions are from the true prices. In this case, it's ~$384k, with larger mistakes further skewing this value upward.  

**MAE (Mean Absolute Error) ~239,373**
- This means that a "typical" prediction is about $240K from the actual price of the house.

The gap between the RMSE and the MAE (1.6x) tells us that there are some substantial prediction errors in the dataset. This can signal several things: the presence of outliers, house prices cannot be predicted on size alone, and other factors can impact the price of certain properties. 

---
## 💻 Implications 
- The model is excellent for understanding market patterns and giving a ballpark estimate (relative pricing) — but that's all there is to it. The predictions have a substantial margin of error, which is too large for a precise valuation. Although size alone provides a reasonable starting point for valuation at ~71%, the error metrics highlight the need for additional factors in professional appraisals. 
 



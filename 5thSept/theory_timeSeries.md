# AI/ML Session - 5th September 2024
### By - Heta Rahul Patel
---
# Time Series ML Techniques
Welcome to the fascinating world of Time Series Machine Learning! 
This guide will take you on a journey through the key concepts and techniques that make time series data unique and powerful. Whether you're a complete beginner or just need a refresher, this comprehensive guide will help you understand and enjoy the intricacies of time series ML.
<br><br>
## ⏰ Introduction to Time Series
- Time series is a sequence of data points collected over time, usually at consistent intervals.
- It’s all about observing how things change over time.
- Think of tracking your daily steps with a fitness tracker, recording stock prices every hour, or noting down daily temperatures.
- Unlike regular data, time series data is ordered in time, making the sequence itself important and unique because each point is related to the previous one.
<br><br>
## 🤔 Why Time Series is Important
- Time-dependent data is everywhere: in finance, weather forecasting, sales analysis, and even in your own life (like monitoring your daily screen time, etc). Understanding patterns in this data helps make informed decisions, predict future outcomes, and optimize processes.
---
# ❗️ Key Concepts of Time Series
## 1. Trend
- **Definition**: A trend is the overall direction in which the data is moving over time. It could be upward, downward, or flat.
- **Example**: Imagine you’re monitoring your social media followers over time. You notice that, on average, you’re gaining more followers every month. This consistent increase is a trend. It tells you that your content is becoming more popular, even if some days show a drop in followers. The trend gives you the bigger picture.
<br><br>
## 2. Seasonality
- **Definition**: Seasonality refers to regular, repeating patterns or cycles in data that occur at specific intervals, such as daily, monthly, or yearly. It's something you can almost set your watch to because it happens at the same time every year, month, or week.
- **Example**: Think about an ice cream shop. Sales naturally spike during the summer and drop in the winter. This up-and-down pattern is seasonality. Even if overall sales are increasing (trend), the seasonal pattern shows up year after year. Understanding seasonality helps the shop prepare for busy times and manage stock.
<br><br>
## 3. Noise
- **Definition**: Noise is the random, irregular, unwanted and unpredictable variations (ups and downs) in data that don't follow any pattern. It's the "background static" that can make it hard to see the real signals in your data.
- Think of it as background chatter in a busy room - sometimes louder, sometimes quieter, but always there.
- **Example**: Suppose you’re tracking your daily study hours. One day, you studied for just 10 minutes because of a sudden power outage. This day is an outlier, a noise in your data. Noise doesn’t reflect your typical study behavior and can sometimes obscure the real trends and patterns.
<br><br>
## 4. Stationarity
- **Definition**: A time series is stationary if its statistical properties (like mean and variance) are constant over time. Stationarity is crucial for many ML models to work properly.
- **Example**: Picture a car driving on a perfectly flat road. The car's speed (time series) remains constant—this is stationarity. Now, imagine the road starts sloping upward or downward, causing the car’s speed to change—this breaks stationarity. In time series analysis, we often need to adjust our data to make it stationary before applying certain models.
- Importance: Many machine learning models work best when data is stationary. It's like trying to solve a puzzle where the pieces keep changing shape - much easier if they stay the same!
<br><br>
---
## 🧩 Putting It All Together: A Comprehensive Example

Let’s say you’re studying the number of visitors to a theme park over several years. Here's how trend, seasonality, noise, and stationarity might work together:

- **Trend**: Over the years, the theme park adds new attractions, leading to a gradual increase in visitors—this is the trend.
- **Seasonality**: Every summer, there's a big jump in visitors because kids are on vacation—this is seasonality.
- **Noise**: Some days, it rains, leading to fewer visitors, or there's a special event that draws extra crowds—these irregular events are noise. Great for the business but not very helpful in predicting regular footfall.
- **Stationarity**: If we remove the trend and seasonality, what's left is a stationary series—maybe the number of visitors on random weekdays when no special events are happening.

Together, these components make up the rich and complex patterns we see in time series data. Understanding them helps us model and predict future values more accurately.

---
<br>

| Aspect                | Classic ML Prediction                                      | Time Series ML Prediction                              |
|-----------------------|-------------------------------------------------------------|--------------------------------------------------------|
| **Goal**        | To predict a future outcome based on features or attributes in a dataset.   | To forecast future values based on past trends and patterns over time.   |
| **Example Situation** | Predicting house prices based on features like the number of bedrooms, size of the house, and location. | Forecasting future sales based on past monthly sales data. |
| **Data Dependency**   | Assumes data points are independent of each other.         | Depends on the order and time intervals of data points. |
| **Patterns**          | Focuses on relationships between features.                | Looks for trends, seasonality, and noise in data over time. |

---
## 🏛️ Classic ML Techniques for Time Series

### 1. Moving Average
- **Explanation**: The moving average smooths out short-term fluctuations and highlights longer-term trends or cycles. It calculates the average of the data points within a specific window that moves across the time series.
- **Use Case**: Suppose you want to smooth out daily stock prices to see the underlying trend. By applying a 7-day moving average, you get a clearer picture of the stock’s overall direction, ignoring daily ups and downs.

### 2. ARIMA (AutoRegressive Integrated Moving Average)
- **Explanation**: ARIMA is a powerful tool for forecasting. It combines three components:
  - AR (AutoRegressive): Uses past values to predict future ones.
  - I (Integrated): Differencing the data to make it stationary.
  - MA (Moving Average): Uses past forecast errors in a regression model.
- **Use Case**: If you’re trying to forecast monthly sales for the next year, ARIMA can help by considering past sales data, adjusting for trends, and smoothing out noise.

### 3. Exponential Smoothing
- **Explanation**: Exponential smoothing gives more weight to recent observations, making it responsive to changes in the data. There are simple, double, and triple exponential smoothing methods, depending on whether you want to account for trend and seasonality.
- **Use Case**: Imagine you’re managing inventory for an online store. Using exponential smoothing, you can more accurately predict demand, allowing you to adjust stock levels accordingly.

---

## ⚠️ Challenges and Considerations
- Data Quality: Time series data can be messy. Missing values, outliers, and noise can make analysis challenging.
- Choosing the Right Model: Different time series require different models. What works for one dataset might not work for another.
- Overfitting: Be careful not to make your model too complex, as it might fit the noise rather than the actual pattern.

---

### Common Pitfalls
- Ignoring Stationarity: Many time series models assume the data is stationary. Ignoring this can lead to inaccurate predictions.
- Overlooking Seasonality: Not accounting for seasonality can skew your results, especially in industries with strong seasonal patterns.
- Misinterpreting Noise: Random fluctuations might be mistaken for real patterns, leading to poor decisions.

---
### ⏭️ What next?
While classic ML techniques are powerful, deep learning models like RNNs (Recurrent Neural Networks), LSTMs (Long Short-Term Memory networks) and Prophet by Facebook, etc. are advancing the field by handling complex patterns in time series data. The future of time series analysis lies in these more advanced techniques. While we won't dive into these here, they represent the cutting edge of what can be done with time series data. However, mastering the basics is essential before diving into these advanced models.

## Conclusion

Time series data is everywhere, from the stock market to weather forecasts. By understanding key concepts like trend, seasonality, noise, and stationarity, and by using models like Moving Average and ARIMA, you can make sense of complex data and make informed predictions. The journey doesn't stop here—there's always more to explore, including advanced techniques like deep learning. But for now, hope you have a solid foundation to build on.

## Happy learning! 🚀





# AI/ML Session - 5th September 2024
### By - Heta Rahul Patel

# Classic ML Techniques for Time Series

## 1️⃣ Moving Average

### What It Is:

- A moving average is a way to smooth out the ups and downs in a set of data points to see the overall pattern more clearly. Imagine if you track how much time you spend on homework every day. Some days are really long, and some are short, but you want to know your average time over a week.

### How It Works:

- Step 1: Choose a window size, say 3 days.
- Step 2: Calculate the average of your first 3 days of homework time.
- Step 3: Move one day forward and calculate the average for the next 3 days.
- Step 4: Keep doing this, moving day by day, until you’ve covered all days.

The result is a smoother line that shows how your homework time changes over time without focusing on daily ups and downs.

### Example:

Let’s say you spent the following times on homework over 7 days:

- Day 1: 2 hours
- Day 2: 3 hours
- Day 3: 4 hours
- Day 4: 3 hours
- Day 5: 5 hours
- Day 6: 6 hours
- Day 7: 4 hours

To calculate a 3-day moving average:

- For Days 1 to 3: (2 + 3 + 4) / 3 = 3 hours
- For Days 2 to 4: (3 + 4 + 3) / 3 = 3.33 hours
- For Days 3 to 5: (4 + 3 + 5) / 3 = 4 hours

The moving average smooths out the daily fluctuations, making it easier to see the trend in your homework time.

---
## 2️⃣ ARIMA (AutoRegressive Integrated Moving Average)

### What It Is:

- ARIMA is a more advanced technique used to predict future values in a time series. It’s like a supercharged version of the moving average that also considers how the data changes over time.

### Breaking Down the Name:

- **AutoRegressive (AR)**: This part uses past values to predict future ones. It’s like saying, “If I spent 2 hours on homework yesterday and 3 hours the day before, I might spend around 2.5 hours today.”
- **Integrated (I)**: This step helps make the data stable by removing trends or seasonality. If your homework time is steadily increasing, this part helps level it out.
- **Moving Average (MA)**: This part looks at past errors to make better predictions. If you guessed wrong in the past, it adjusts to improve future guesses.

### How It Works:

- AR (AutoRegressive): Imagine you’re predicting tomorrow’s homework time. ARIMA looks at your homework times from the past few days and finds a pattern to guess tomorrow’s time.

- I (Integrated): Sometimes your data might be increasing or decreasing over time (a trend). This step removes that trend so the model can focus on predicting the pattern, not just following the trend.

- MA (Moving Average): This part looks at how off your previous predictions were and adjusts to improve. If you guessed too high last time, it’ll guess a bit lower this time.

### Example:

Let’s say over the past 5 days, you spent 2, 3, 2.5, 3.5, and 4 hours on homework. ARIMA would use this history to predict how much time you’ll spend on homework tomorrow. It considers the overall trend, the changes from one day to the next, and how accurate past predictions were.

---
## 3️⃣ Exponential Smoothing

### What It Is:

Exponential smoothing is another way to smooth out data, like the moving average, but it gives more importance to recent data points. It’s like saying, “What I did yesterday is more relevant than what I did a week ago.”

### How It Works:

- Smoothing: Instead of just averaging, exponential smoothing multiplies recent data points by a bigger factor (giving them more weight) and older data points by a smaller factor (giving them less weight).

- Forecasting: By giving more weight to recent data, the model can quickly adjust to changes. For example, if you suddenly start spending more time on homework, exponential smoothing will notice this quickly and adjust predictions.

### Example:

Imagine you’re again tracking your homework time:

- Day 1: 2 hours
- Day 2: 3 hours
- Day 3: 4 hours

In exponential smoothing, Day 3 (4 hours) will be more important in predicting Day 4’s homework time than Day 1’s 2 hours. If your recent homework time is going up, the model will predict that you’ll spend even more time on Day 4.

### Why Use Exponential Smoothing?

This method is especially useful when you expect recent events to be more indicative of the future. For example, if you’re studying for an upcoming exam, your recent study time is more relevant than what you did at the start of the semester.

---
## ⚠️❗️ a bit advance stuff ahead

## 4️⃣ LSTM (Long Short-Term Memory)

### What It Is:

LSTM is a type of neural network that’s really good at understanding sequences of data over time. It’s like having a memory that can remember important things from the past while also focusing on what’s happening now. This makes it very powerful for predicting things like stock prices, weather, or even the next word in a sentence.

### Why It’s Special:

Unlike simpler models that might forget what happened earlier, LSTM can remember important patterns over a long period, making it great for time series data where past events can influence the future.

### How It Works (The Super Simple Version):

- **Memory Cells**: Imagine you’re reading a book and trying to predict what happens next. Some details are crucial (like a plot twist), and some are not (like what color the sky was on page 3). LSTM has “memory cells” that help it decide what to remember and what to forget.

- **Gates**: LSTM uses something called “gates” to control the flow of information. Think of gates like doors that decide whether information should be kept, updated, or forgotten:
  - Forget Gate: Decides what old information to throw away.
  - Input Gate: Decides what new information to add to the memory.
  - Output Gate: Decides what part of the memory to use to make a prediction.

### Example:

Let’s say you’re predicting how much time you’ll spend on homework based on the past week’s data. Some days were busy with extra activities, and some were normal. LSTM can “remember” the busy days as important events that might repeat and use that information when predicting the future.

- Day 1: 2 hours (normal)
- Day 2: 3 hours (normal)
- Day 3: 1 hour (you had a sports event)
- Day 4: 4 hours (you were cramming for a test)
- Day 5: 2 hours (normal)
- Day 6: 5 hours (another cramming session)
- Day 7: 2 hours (normal)

LSTM will recognize that Days 4 and 6 were special (cramming sessions) and might use that information to predict future spikes in study time if another test is coming up. It remembers important things like cramming for tests and understands that those days are different from regular study days.

### Why LSTM?

If you’re trying to predict something where the past really matters (like in the example of studying before a test), LSTM can be incredibly accurate because it doesn’t just look at the last few days—it looks at the big picture, remembering important events that happened earlier.

LSTM is complex, but when you think of it as a model with a really good memory, it becomes easier to understand how it can be useful for time series data. The key is that it knows what to remember and what to forget, making it super powerful for predicting things that depend on past events.

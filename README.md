# The World Tour of '99: Predicting Crowd Energy

In this project, I acted as the data scientist for the legendary rock band *Electric Omen*. The band is planning a massive comeback tour, and my job was to help them ensure every show is a hit. The goal? Predict the **Crowd Energy** (a score from 0-100) for future gigs so the manager can optimize setlists and pricing.

## The Challenge

The band provided me with historical tour logs, but there was a catch: the roadies were terrible at record-keeping. The data was messy, inconsistent, and full of errors (like mixed currencies and "late night" instead of actual times). I also had some scribbled notes from the Lead Singer, which were mostly rumors that I had to prove or disprove.

## My Approach

### 1. Cleaning the Mess

Before building any models, I had to fix the data.

* **Dates:** Converted vague terms like "Evening" or "Late Night" into actual timestamps.
* **Prices:** Standardized everything to a single currency (handling symbols like £ and €).
* **Outliers:** Fixed impossible values, like negative crowd sizes or volume levels that didn't make sense.

### 2. Feature Engineering

I created new features to help the model learn better:

* `Relative_Price`: Is the ticket cheaper or more expensive than usual for this specific venue?
* `Venue_Outfit`: How does the band's outfit match the vibe of the venue?
* `Days_Elapsed`: To see if the tour momentum affected energy over time.

### 3. Exploratory Data Analysis (EDA)

I analyzed the four unique venues to understand their "personality":

* **Venue Alpha (Holy Grounds):** A converted monastery. I found it has a strict volume limit; playing too loud actually kills the vibe here.
* **Venue Beta (Vampire's Den):** A gothic nightclub. As expected, it performs way better late at night and on weekends. Spandex outfits work best here!
* **Venue Gamma (Snob Pit):** An exclusive venue. Surprisingly, the crowd energy stays high even when tickets are expensive.
* **Venue Delta (Mosh Pit):** Pure chaos. Lower prices and massive crowds drive the energy up.

### 4. The Model

I chose a **Random Forest Regressor** for the final predictions.

* **Why?** Linear models couldn't handle the weird relationships (like how high prices are bad for Delta but good for Gamma). The Random Forest was great at capturing these complex, non-linear patterns and interactions between venues and outfits.

## Bonus: Revenue Optimization

I was also tasked with setting the optimal ticket price for **Venue Gamma**.

* **Discovery:** The demand at Gamma is "inelastic," meaning these fans are rich snobs who don't care about price hikes.
* **Strategy:** I ran a simulation testing prices from $20 to $400.
* **Recommendation:** I recommended raising the price to **$291**. While this slightly drops attendance, the massive increase in ticket revenue (plus stable merch sales) maximizes the total profit.

## Files in this Repository

* `CC_ML_Task1.ipynb`: The Jupyter Notebook containing all my code for cleaning, EDA, and modeling.
* `findings_report.pdf`: A detailed report explaining what I discovered about each venue and the singer's theories.
* `revenue_optimization.pdf`: The bonus report showing the math behind the $291 ticket price strategy.
* `predictions.csv`: The final predicted Crowd Energy scores for the test dataset.

*Rock on!*

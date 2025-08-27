# Data Visualization Results

![](https://github.com/jmferreirab/GPUAnalysis/blob/master/output/figures/iterations-per-second-higher-is-better-512x512-gens.png?raw=true)
![](https://github.com/jmferreirab/GPUAnalysis/blob/master/output/figures/seconds-per-image-lower-is-better-512x512-gens.png?raw=true)

# Contents

### 1. A1111 Webui Benchmark data preparation and analysis

- Load Automatic1111 webui benchmark data
- Narrow down relevant columns
- Visualize the distribution of the dates of the benchmarks (histogram)
- Extract individual scores from scores column
- Extract GPU model and RAM
- Remove worst performing GPUs by selecting bottom 20, then dropping them to narrow scope.
- Remove specific GPU references with str.contains to narrow scope to AMD and Nvidia consumer GPUs.
- Remove additional GPUs using a manually generated blacklist (remove non-consumer grade GPUs).

### 2. A1111 Webui Benchmark data visualization

- Data visualizations for

  - Average performance across benchmarks from the maximum score per benchmark
  - Maximum performance across benchmarks from the maximum score per benchmark

### 3. Analysis for performance vs price

- Load price data and visualize price per GPU
- Merge price and benchmarks to get performance / price ratio.
- Visualize performance to price ratio per GPU with color scale based off price.
- Visualize iterations per second per GPU with color scale based off price.
- Visualize seconds to generate an 512x512 image with 25 steps with color scale based off price.

### 4. References to work by other authors

### 5. Conclusions

In this analysis, we examined data collected by the SD WebUI Extension from users of the A1111 WebUI, which is gathered automatically through **crowdsourcing**.

We calculated a ratio of performance (measured in iterations per second) to price to represent the value of each GPU card. This metric, often referred to as “value,” takes into account both the performance and cost of each card.

Our goal was to identify the optimal GPU card for stable diffusion that offers the most value per dollar. However, it’s important to note that value is a relative measure and depends on how the card will be used. For example, even older cards like the GTX 1060 can successfully run A1111 WebUI. The main advantage of newer cards is the time saved to generate content.

For those considering purchasing a GPU card, we suggest considering **two purchase criteria**:

- How much is your time worth? Does the time saved with a faster card justify the cost?
- How much are you willing to pay per month for the features offered by the card? If you plan to use the card for 5 years, does the GPU cost cancels out with the amount you would otherwise spend on a third service that provides those features?

---

**Disclaimer.** Please note that price data was gathered manually by using Amazon prices as reference on July 16, 2023. These prices are constantly changing, therefore, other analysis may show slightly different results.

**Runtime requirements.** Please see requirements.txt. Install via `pip install -r requirements.txt`

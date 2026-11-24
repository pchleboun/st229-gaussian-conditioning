# st229-gaussian-conditioning
Reversal of correlation 

# Reversal of correlation in a Gaussian model

How can exercise and bone density be positively correlated at **every fixed weight**, yet negatively correlated in the population as a whole? This interactive visualisation for Warwick’s **ST229 Probability for Mathematical Statistics** uses an illustrative trivariate Gaussian model. In the default example, the correlation is **+0.60** at each weight and **−0.60** overall.

## Run the demo

Download the HTML file and open it in a browser. The plots and controls work offline. All the code is in one file.

To publish your own copy on GitHub Pages, save the demo as `index.html` alongside this README in the repository root. Under **Settings → Pages**, select **Deploy from a branch**, choose the branch containing the file and the **/ (root)** folder, then save. Once published, **Visit site** opens the interactive demo. That address can also be shared as a URL resource in Moodle.

## Try it in class

1. Choose **Clear reversal**, click **Centre**, and set **Variance explained by weight** to **0%**. The dashed blue marginal contours and solid orange conditional contours coincide. Ask students to predict which regression line will change as weight explains more of the variation.
2. Keeping **Within-weight correlation** at **0.60**, increase **Variance explained by weight**. At **37.5%** the blue contours are circular and the blue regression line is horizontal. At **75%** the blue line slopes down and the orange line still slopes up.
3. Now increase **Fixed weight**. Follow the centre of the orange ellipses. It moves **up and left**, even though the regression line through each ellipse slopes **up and right**. How does that movement explain the negative association when all weights are pooled?

## Reading the plots

**Left — projection and slice.** The grey ellipsoids are surfaces of constant joint density. Their dashed blue footprints give contours for exercise and bone density across all weights. The orange plane fixes weight, and its intersections with the shells give the solid orange curves. Drag to rotate, or choose **Top · X₁X₂** to compare the orientations directly.

**Right — density contours.** Each ellipse joins points of equal density. By default the three curves enclose **25%, 50% and 90%** of the probability under their respective distributions. Use **Contours − / +** to show one to five levels. Turn on **Sample points** to see observations beyond the outer ellipse.

Moving away from mean weight can shrink a section of a fixed 3D shell until it disappears. On the right, the orange curves always enclose the selected probabilities. They move with the conditional mean and retain their size because the Gaussian conditional covariance is independent of the value of weight.

## The mathematics

Write $r$ for the within-weight correlation and $h$ for the fraction of the variance of each variable explained by weight. In this model the two conditional means move in opposite directions as weight increases. By the law of total covariance, the within-weight contribution to the marginal correlation is $(1-h)r$ and the contribution from the conditional means is $-h$. Hence

$$
\rho_{\mathrm{marginal}}=(1-h)r-h.
$$

For $r>0$, the marginal correlation changes sign at $h=r/(1+r)$. The three presets give the following correlations.

| Preset | Marginal | Conditional on weight |
| --- | ---: | ---: |
| Clear reversal | −0.60 | +0.60 |
| Exercise-class notes | −1/7 | +2/11 |
| Python example | −1/7 | +17/43 |

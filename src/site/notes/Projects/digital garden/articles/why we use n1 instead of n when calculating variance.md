---
{"title":"Why we use n-1 instead of n when calculating variance","dg-permalink":"why-do-we-use-n1-instead-of-n-when-calculating-variance","project":[["noobthink.com"]],"created":"2025-05-04T11:49","dg-publish":true,"tags":["article"],"permalink":"/why-do-we-use-n1-instead-of-n-when-calculating-variance/","dgPassFrontmatter":true,"updated":"2025-05-04T12:49:06.278+02:00"}
---

# Why We Use n-1 Instead of n When Calculating Variance

When you calculate variance, you take the squared differences from the mean, and average them out. But, unlike how we've been taught in school, when dealing with a sample, you divide the total by $(n-1)$ elements, not $n$. Also known as Bessel's Correction, it is known for providing a more accurate result of your mean deviation, by reducing *the bias in the data*. I don't know for you, but I found it puzzling, so rather than just taking it at face value, I wanted to make sure I understood the reasoning for this particularity.

## The Intuition
When you calculate the **sample mean deviation** (variance), you’re using the data itself to define the center. This creates a bias—your sample mean is _tailor-made_ to be as close as possible to your data points. Thus, it inherently makes deviations look smaller than they truly are.

Think of it this way:  
Your sample mean is a compromiser. It's the value **closest to every element of your sample, but not of the true population**. It sits where it does to minimize the drama (i.e., squared differences). If you had the **true population mean** (which you never do), deviations from it would be larger. 

So if you divide by $n-1$ instead of $n$, your result will be bigger, thus closer to the population mean.

## Example Time
You’re estimating Pokémon card counts in a school. You sample three kids:
- Friend A: 50 cards  
- Friend B: 60 cards  
- Friend C: 70 cards  

Sample mean = 60. Deviations: -10, 0, +10. Squared: 100, 0, 100.  

If you divide by $n$ (3):  
$$\text{Variance} = \frac{100 + 0 + 100}{3} \approx 66.67 $$

But this represents only the variance for your sample, i.e. three friends. In reality, say the total population is the entire school. There may be a kid with 40 cards, another with 75 cards.
Inevitably, the **true population variance** (if you could measure everyone) will always be higher. In this case, if you add the two other kids:

Deviations: -20, -10, 0, +10, +15. Squared: 400, 100, 0, 100, 225.
$$\text{Variance} = \frac{400+100+0+100+225}{5} = 165$$

You can see that it's quite different from the result you get when dividing the sample mean by $n$. 
Now, if you divide by $n-1$ (2):  
$$\text{Variance} = \frac{200}{2} = 100$$

Sure, it's not the real variance either, but it's definitely closer to it than the initial result.

## The Takeaway
Use $n-1$ because your sample mean is biased. It’s not about being fancy—it’s about correcting for the fact that when you’re making an estimation using a sample from a population, your mean deviation will always be smaller than the one for the entire population.


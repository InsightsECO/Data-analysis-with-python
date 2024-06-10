<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exploratory Data Analysis and Visualization with Python Libraries (Kaggle Automotive Dataset)</title>
</head>

<body>
    <h1>Exploratory Data Analysis and Visualization with Python Libraries (Kaggle Automotive Dataset)</h1>

    <h2>Importing Required Libraries</h2>
    <pre><code>import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.set(color_codes=True)
%matplotlib inline</code></pre>

    <h2>Creating the DataFrame</h2>
    <pre><code>mydata = pd.read_csv("Automobile.csv")</code></pre>

    <h2>Checking the Head of DataFrame</h2>
    <pre><code>mydata.head()</code></pre>

    <h2>Getting Info about DataFrame</h2>
    <pre><code>mydata.info()</code></pre>

    <h2>Average Price of Automobile</h2>
    <pre><code>mydata['price'].mean()</code></pre>

    <h2>Cheapest and Costliest Cars</h2>
    <pre><code>mydata[mydata['price'] == mydata['price'].max()]
mydata[mydata['price'] == mydata['price'].min()]</code></pre>

    <h2>Cars with Horsepower Greater Than 100</h2>
    <pre><code>mydata[mydata['horsepower'] &gt; 100].count()</code></pre>

    <h2>Number of Hatchback Cars</h2>
    <pre><code>mydata[mydata['body_style'] == 'hatchback'].info()</code></pre>

    <h2>Most Commonly Found Cars</h2>
    <pre><code>mydata['make'].value_counts()</code></pre>

    <h2>Finding Make of Car Priced at 7099</h2>
    <pre><code>mydata[mydata["price"] == 7099]['make']</code></pre>

    <h2>Cars Priced Greater Than 40000</h2>
    <pre><code>mydata[mydata['price'] &gt; 40000]</code></pre>

    <h2>Sedan Cars Priced Less Than 7000</h2>
    <pre><code>mydata[(mydata['body_style'] == 'sedan') &amp; (mydata['price'] &lt; 7000)]</code></pre>

    <h2>Univariate Plots</h2>
    <pre><code>plt.hist(mydata['normalized_losses'])
plt.title('Normalized losses from vehicle engines')
plt.show()

sns.distplot(mydata['city_mpg'])
plt.show()</code></pre>

    <h2>Bivariate Plots</h2>
    <pre><code>sns.jointplot(mydata['engine_size'], mydata['horsepower'], kind='scatter')
plt.show()

sns.pairplot(mydata[['normalized_losses', 'horsepower', 'engine_size']])
plt.show()

sns.stripplot(mydata['fuel_type'], mydata['horsepower'])
plt.show()</code></pre>

    <h2>Creating Box Plot</h2>
    <pre><code>sns.boxplot(mydata['number_of_doors'], mydata['horsepower'])
plt.show()

sns.barplot(mydata['body_style'], mydata['horsepower'])
plt.show()</code></pre>

    <h2>Relating Horsepower to Stroke of Engine</h2>
    <pre><code>sns.jointplot(mydata['stroke'], mydata['horsepower'], kind='hex')
plt.show()

sns.jointplot(mydata['stroke'], mydata['horsepower'], kind='scatter')
plt.show()</code></pre>

    <p>This notebook provides a comprehensive analysis of the Kaggle Automotive Dataset, including data exploration and
        visualization using various Python libraries.</p>
</body>

</html>

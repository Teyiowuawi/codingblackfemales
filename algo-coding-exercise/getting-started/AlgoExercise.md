# My Algo Exercise Documentation 

This trading algorithm creates child orders orders on the BUY side of the book at the average price of the market prices available. 

To make it more reflective of a real life market, if the quantity desired exceeds a certain percentage of the overall market volume, no action occurs and no child order is created. 

##### *NOTE*: When trading, you want to be as descrete as possible, causing minimal impact to the market. 

### [MyAlgoLogic][https://www.youtube.com/watch?v=eJojC3lSkwg]

*Add the actual link please!*

A for loop is used to iterated through the tick()'s using the `getBidLevels()` method on the state to get the number of bid levels available:

```java
long totalTickPrice 
```

Holds the total price of the tick() after iteration 

```java
long totalTickQuantity 
```
Holds the total volume quantity of the tick() after iteration


Following the loop, `averageTickPrice` is calculated using the `totalTickQuantity` and `state.getBidLevels()` method.

```java
long quantity 
```
Holds the quantity desired

```java 
long percentageOfMarketolumeNotToExceed
```

Threshold of percentage of market volume to stay below. In this algo it is 20% however, fiures in real life may be significantly lower.  

If `quantity` doesn't exceed the `percentageOfMarketVolumeNotToExceed`, three child orders are created. 

### [MyAlgoTest][https://www.link.com] 

In this file, there are various tick()'s created to test my algorithms against, depending on the quantity and the percentage of market volume threshold, 3 child orders at the average price are created or no action occurs. 

**Example** 

```java 
.next().price(97L).size(5000L)
.next().price(99L).size(10000L)
.next().price(101L).size(15000L)
.next().price(103L).size(20000L);
```

2000 is not above 20% of the market volume of the tick() therefore, 3 child orders (quantity 2000 @ 100) are created and added to the Bid side of the book. 
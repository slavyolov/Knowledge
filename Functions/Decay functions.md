
# Information
Linear fuction : Y = b_0 + b_1 * x  
  
if b_1 is positive, then we have linear growth  
if b_1 is negative, then we have linear decay

# Code snippet
```python
def linear_curve(x: float, b_0: float, b_1: float):  
    """  
    Linear fuction (Equation of a straight line) : Y = b_0 + b_1 * x  
    
    if b_1 is positive, then we have linear growth    
    if b_1 is negative, then we have linear decay 
     
    Args:        
	    x: The explanatory variable x ('price')        
	    b_0: The intercept is the Y value when x equals zero        
	    b_1: The slope of the regression line; how much Y changes for each one-unit change in x.  
	    
    Returns:        
	    The value of Y given the explanatory variable x ('price'), the intercept and the slope of the regression  
	    
    Examples:        
	    # let's assume that b_0 and b_1 are estimated to be : 
	    >>> b_0 = 395; b_1 = -4.66        
	    >>> x = 0; print(f"The quantity sold when x (the price) == {x} is {round((b_0 + b_1 * x),1)}")
        The quantity sold when x (the price) == 0 is 395.0        
        >>> x = 10; print(f"The quantity sold when x (the price) == {x} is {round((b_0 + b_1 * x),1)}")  
        The quantity sold when x (the price) == 10 is 348.4        
        >>> x = 100; print(f"The quantity sold when x (the price) == {x} is {round((b_0 + b_1 * x),1)}")  
        The quantity sold when x (the price) == 100 is -71.0    
    """    
    return b_0 + b_1 * x
```


**Resources :**
- [Linear Growth and Decay (onlinemath4all.com)](https://www.onlinemath4all.com/linear-growth-and-decay.html)

# Tags

#LinearRegression, #curves, #curve_fitting, #linear_growth, #linear_decay

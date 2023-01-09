# Surfing Up IceCream on Oahu

## Project Overview:
The project focuses on lookig at weather trends on the island of Oahu.  This data will be used to convince investors to invest in an ice cream and surf shop.   The investors want to see weather data to suppor the business model.   The investors want to see weather data from June and December to determine if the shop will have sustainability year-round.  

### Resources
-Jupyter Notebook 6.4.12
-SQLAlchemy
-Numpy
-Pandas
-Weather data: hawaii.sqlite

### Results:
## June
1. The average temperature in the month of June is 75 degrees with a standard deviation of 3 degrees. 
2. The minimum temperature in June was 64 degrees.
3. The maximum temprerature in June was 85 degrees.
## December
1. The average temperature in the month of December is 71 degrees with a standard deviation of 4 degrees. 
2. The minimum terperature in December was 56 degrees to 85 degrees.
3. The maximum temprerature in December was 83 degrees.

### Summary
The minimum temperatures during the month of December could indicate days of slow buiness.  However, December would still be a great month for ice cream sales with an average temperature of 71 and highs in the 80s.  The difference between the average temperatures between summer and winter is only 4 degrees, suggesting that business would be sustainable year-round.  
In addition to considering the temperatures during the summer and winter, the precidpitation is another parameter that could be analyzed.  Below are queries that retrieve this data:

june_rain = []
june_rain = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date)==6).all()
june_rain_df = pd.DataFrame(june_prcp, columns=['date','Precipitation'])
june_rain_df.describe()

dec_rain = []
dec_rain = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date)==12).all()
dec_rain_df = pd.DataFrame(dec_prcp, columns=['date','Precipitation'])
dec_rain_df.describe()

**1. % Domestic visitors**



% Domestic visitors = SUMX(main\_data, main\_data\[domestic\_visitors] / \[Total Visitors] \* 100)





**2. % International visitors**



% International visitors = SUMX(main\_data, main\_data\[international\_visitors] / \[Total Visitors] \* 100)



**3. Avg Accessibility Score**



Avg Accessibility Score = AVERAGE(main\_data\[accessibility\_score])



**4. Avg Visitors per Season**



Avg Visitors per Season = 

AVERAGEX(

&#x20;   VALUES('main\_data'\[season]),

&#x20;   CALCULATE(SUM('main\_data'\[visitor\_count]))

)



**5. Most Used Transport Mode**



Most Used Transport Mode = 

CALCULATE (

&#x20;   MAX('main\_data'\[transport\_mode]),

&#x20;   TOPN (

&#x20;       1,

&#x20;       ADDCOLUMNS (

&#x20;           VALUES('main\_data'\[transport\_mode]),

&#x20;           "ModeCount", CALCULATE(COUNTROWS('main\_data'))

&#x20;       ),

&#x20;       \[ModeCount], DESC

&#x20;   )

)





**6. Most Visited Age Group**



Most Visited Age Group = 

CALCULATE (

&#x20;   MAX('main\_data'\[age\_group]),

&#x20;   TOPN (

&#x20;       1,

&#x20;       ADDCOLUMNS (

&#x20;           VALUES('main\_data'\[age\_group]),

&#x20;           "AgeGroupCount", CALCULATE(COUNTROWS('main\_data'))

&#x20;       ),

&#x20;       \[AgeGroupCount], DESC

&#x20;   )

)





**7. Percent Domestic Visitors** 





Percent Domestic Visitors = 

DIVIDE(\[Total Domestic Visitors], \[Total Visitors]) \* 100





**8. Sum of Domestic Visitors**





Sum of Domestic Visitors = SUM(main\_data\[domestic\_visitors])





**9. Total Domestic Visitors**



Total Domestic Visitors = 

CALCULATE(

&#x20;   SUM('main\_data'\[visitor\_count]),

&#x20;   'main\_data'\[domestic\_visitors] = "Domestic"

)





**10. Total International Visitors**





Total International Visitors = SUM(main\_data\[international\_visitors]) 





**11. Total Revenue**



Total Revenue = SUM(main\_data\[revenue\_inr\_lakhs])





**12. Total Visitors**



Total Visitors = SUM(main\_data\[visitor\_count])





**13.Unique Destinations**



Unique Destinations = DISTINCTCOUNT(main\_data\[destination\_name])






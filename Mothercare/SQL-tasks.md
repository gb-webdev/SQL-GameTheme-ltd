Go to sql server desktop
Then the sql engine
Run the engine through security
Cd into Mothercare

Extract from table tblebestsellers, there are 3 fields: Level4, Salesvalueincvat, Myweekno:

**
    SELECT Level4, Salesvalueincvat, Myweekno from tblbestsellers
**

Extract the same data but the most recent week, with the biggest nu7mber of sales:

**
    SELECT Level4, Salesvalueincvat, Myweekno from tblbestsellers
    WHERE Level4 = 'gk00968'
    ORDER BY Myweekno DESC, Salesvalueincvat DESC
**

'gk00968' is selling well, we we want to buy more, what is it?
Add a link to the query and a new field, the new field is descr.
A join is needed, join the last successful select to a a new table via join.

** 
    SELECT
        b.Level4,
        l.descr,
        b.Salesvalueincvat,
        b.Myweekno
    FROM
        blebestsellers b
    INNER JOIN
        tbllevel4 1 ON b.Level4 = l.Level4 AND b.Level4 = 'gk00968'
**
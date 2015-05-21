[Back to Table of Contents](TableOfContents.md)

## Decision Tables ##

This component contains a table, where each row represent a rule. The rules in this table are boolean conditions. If the condition is met, then the rule action which is set in the java script section is executed.
This is a standalone component, which can be directly constructed in BPM and associated with any related processes.

The following example shows how decision tables are used to construct boolean conditional rules.
Step 1:
Navigate to Process Designer. Open the project in which you want to create decision table, which can then be attached to a process.
In the designer, Create a new decision service as shown in the below 2 screenshots.

![http://i.imgur.com/Xo4t7Rj.jpg](http://i.imgur.com/Xo4t7Rj.jpg)
![http://i.imgur.com/YyZFaPe.jpg](http://i.imgur.com/YyZFaPe.jpg)

Step 2:
In the Diagram section, drag and drop 'Decision table' from the selections seen on the right hand side of the designer screen.

![http://i.imgur.com/p3TbKX5.jpg](http://i.imgur.com/p3TbKX5.jpg)

Step 3:
This decision table is used to compute the discount for the customers based on the product they purchase from a computer store. So declare the variables suitably as shown in the below screenshot:

![http://i.imgur.com/6UgwYJb.jpg](http://i.imgur.com/6UgwYJb.jpg)

Step 4:
Under the decision table, write the decision rules and actions for the purchase.

![http://i.imgur.com/jkW8cBd.jpg](http://i.imgur.com/jkW8cBd.jpg)
As seen here, a customer gets a discount of 10% if he purchases lenovo laptop alone, 5% of discount if mac book alone is purchased and 25% discount is given if he purchases all three-lenovo,mac and acer laptops at once.
So, each of these rules have the action defined, which is written under javascript section as seen in the screenshot.

Step 5:
On Debugging this decision table, we see the following results:
Here, Lenovo=true,acer=true and mac=true. ie, we assume the customer has purchased all three laptops and find out how much discount should be given to him.

![http://i.imgur.com/Gpts1xY.jpg](http://i.imgur.com/Gpts1xY.jpg)

By observing the decision table rules, it is seen that the customer should be give 25% discount if he purchases all three laptops at once. The result is successfully seen in the below screenshot.

![http://i.imgur.com/hYWaoky.jpg](http://i.imgur.com/hYWaoky.jpg)

Case2: We try to tweak the hardcoded boolean values for the laptop types that flag if that type laptop is purchased or not to observe the output.
By setting lenovo=true, mac=acer=false, we should see 10% discount in the output.

![http://i.imgur.com/tJlwntJ.jpg](http://i.imgur.com/tJlwntJ.jpg)

![http://i.imgur.com/LlFF3mm.jpg](http://i.imgur.com/LlFF3mm.jpg)

![http://i.imgur.com/L8HDnDz.jpg](http://i.imgur.com/L8HDnDz.jpg)

Output:
![http://i.imgur.com/7cve5oG.jpg](http://i.imgur.com/7cve5oG.jpg)

Note: Decision Services can also be integrated with WODM( Websphere Operation Decision Manager)
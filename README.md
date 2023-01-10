# Console-Finances
JavaScript challenge console finances
var firstIncrease = finances[1][1] - finances[0][1];
var greatestIncrease = ["", firstIncrease];
var greatestLoss = ["", firstIncrease];

for (var i = 1; i < totalMonths; i++) {
   var currentProfit = finances[i][1];
   var priorProfit = finances[i-1][1];
   var currentIncrease = currentProfit - priorProfit;
   if (currentIncrease > greatestIncrease[1]) {
      //console.log(greatestIncrease);
      greatestIncrease = [finances[i][0], currentIncrease];
   }
   else if (currentIncrease < greatestLoss[1]) {
      //console.log(greatestLoss);
      greatestLoss = [finances[i][0], currentIncrease];
   }
}

 
//  When you open your code in the browser your resulting analysis should look similar to the following

console.log("Financial Analysis\n"+
"----------------------------\n"+
"Total Months: " + totalMonths + "\n"+
"Total: $" + netProfitLosses + "\n" +
"Average  Change: $" + roundedAverage + "\n" +
"Greatest Increase in Profits: " + greatestIncrease[0] + " ($" + greatestIncrease[1] + ")\n" +
"Greatest Decrease in Profits: " + greatestLoss[0] + " ($" + greatestLoss[1] + ") ");

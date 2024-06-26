# calculate-Man-Month
### Here is your JavaScript code converted into a bookmarklet format in alculate-Man-Month

```javascript
javascript:(function(){function calculateManMonth(hours,rule){const hoursPerDay=8;const daysPerPeriod=rule==="week"?5:20;const hoursPerPeriod=hoursPerDay*daysPerPeriod;return hours/hoursPerPeriod;}const rule=prompt("Choose the rule: 'week' or 'month'");if(rule!=="week"&&rule!=="month"){alert("Invalid rule! Please choose 'week' or 'month'.");return;}const tasks=[];let moreTasks=true;let totalHours=0;while(moreTasks){const taskName=prompt("Enter the task name (or press Cancel to finish):");if(taskName===null||taskName===""){moreTasks=false;}else{const taskHours=prompt("Enter the number of hours for the task:");const hours=parseFloat(taskHours);if(!isNaN(hours)){const manMonths=calculateManMonth(hours,rule);tasks.push({name:taskName,hours:hours,manMonths:manMonths});totalHours+=hours;}else{alert("Please enter a valid number.");}}}const totalManMonths=calculateManMonth(totalHours,rule);const status=(rule==="week"?totalManMonths>=0.25:totalManMonths>=1)?"PASS":"MISS";let resultMessage=`Task Summary:\nTotal Man-Months: ${totalManMonths.toFixed(2)}, Status: ${status}\n`;tasks.forEach(task=>{resultMessage+=`Task: ${task.name}, Hours: ${task.hours}, Man-Months: ${task.manMonths.toFixed(2)}\n`;});alert(resultMessage);navigator.clipboard.writeText(resultMessage).then(()=>alert("Results copied to clipboard"),()=>alert("Failed to copy results to clipboard"));})();
```

### Instructions for use this code as a bookmarklet:
- Copy the entire code above (including the javascript: prefix).
- Open your browser and create a new bookmark.
- Name the bookmark (e.g., "Calculate Man-Month").
- Paste the code into the URL field of the bookmark.
- Save the bookmark.

When you click this bookmark, it will first prompt you to choose the rule ("**week**" or "**month**"). It will then prompt you to enter the task name and the number of hours for each task. The results will include the total hours, corresponding man-months, and status (**PASS or MISS**) based on the chosen rule. The results will be copied to the clipboard.

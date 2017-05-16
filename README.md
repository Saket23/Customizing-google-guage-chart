# Customizing-google-guage-chart
I came across a requirement where I needed a meter chart,so i used google guage chart accordingly

One of the biggest challenge in my requirement was that i needed to use four different colors on the guage but google guage visualization supported to use only three colors.

        var options = {
		redColor:"#ff0000",
		yellowColor: "#e6e600",
          width: 1000, height: 220,
          redFrom: 48, redTo: 64,		  
          yellowFrom:16, yellowTo:32,
		  greenFrom:0,greenTo:16,
		  max: 64,
		  min: 0}
      
Google has defined only three variable colors red,green and yellow we can overrite only these three colors.

So to add another color i used google chrome inspect to find out the path needed under svg in the other color.
And then used jquery to add the id to the html tag from javascript and add to that ID using DOM. 

```javascript
$('g').each(function(index, elem) {
  $(this).attr('id', 'g' + index);
});
var a=document.getElementById("g0").innerHTML;
a=a+'<path d="M109.99999999999999,26A84,84,0,0,1,187.6058807309481,77.85459168133247L168.20441054821106,85.89094376099936A63,63,0,0,0,110,47Z" stroke="none" stroke-width="0" fill="orange"></path>';
var b=document.getElementById("g2").innerHTML;
b=b+'<path d="M109.99999999999999,26A84,84,0,0,1,187.6058807309481,77.85459168133247L168.20441054821106,85.89094376099936A63,63,0,0,0,110,47Z" stroke="none" stroke-width="0" fill="orange"></path>';

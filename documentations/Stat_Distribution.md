# <li>Skillpointpool ver. 1.0.0</li>
# Installation
To install this Macro, simply create a `startup` tagged passage and copy and paste [this content](https://github.com/GwenTastic/Custom-Macros-for-Harlowe/blob/main/src/StatDistribution.ruby) into the passage.

## Description:
This Macro creates a table with a row for all provided stats, in addition it also creates two arrows for adding points to the stat or subtracting them away.

<br>

## Usage:

~~~ruby
($statDistribution: (a: "Stat-1"[, "Stat-2", "Stat-n"]), "Stat-Point-Pool")
~~~

The first argument is an array containing all variable names, eg.: if you have the variables `$charisma` and `$strength` you provide an array like this `(a: "charisma", "strength")` as the macros first argument, the spelling has to be identical since variable names are case sensitive and you cannot include the `$` in the array, the macro will automatically turn the first letter into an uppercase letter so `charisma` will be displayed like this: `Charisma`.
The second argument is the variable name of the shared point pool and also needs to be written identical and without the `$`, eg.: if your skillpool variable is called `$skillpool` then you use it like this: `($statDistribution: (a: "charisma", "strength"), "skillpool")`
 
 <br>

 ## Styling / Structure
 The macro created table and child elements do come with their own IDs and Classes, which can be used to style it further in the Story's Stylesheet.
 The general structure for one stat is this:
 ~~~html
<div id='stats-container'>
    <table id='stats-table'>
        <tr id='stat-row-(Stat-Name)' class='stats-rows'>
            <td id='stat-cell-name-(Stat-Name)' class='stats-cell-names stats-cells'>(Stat-Name)</td>
            <td id='stat-cell-arrow-left-(Stat-Name)' class='stats-cells stats-arrows stats-arrows-left'>«</td>
            <td id='stat-cell-value-(Stat-Name)' class='stats-cell-values stats-cells'>(Stat-Value)</td>
            <td>»</td>
        </tr>
        <tr id='stats-row-statpointpool-value' class='stats-rows'>
            <td id='stat-cell-statpointpool-value' class='stats-cells stats-cell-points' colspan='4'>(Point-Pool-Remainder)</td>
        </tr>
        <tr id='stats-row-statpointpool-text' class='stats-rows'>
            <td id='stat-cell-statpointpool-text' class='stats-cells stats-cell-points' colspan='4'>Points Available</td>
        </tr>
    <table>
</div>
 ~~~
 (The `(Stat-Name)` or `(Point-Pool-Remainder)` are placeholders text to demonstrate that at those places the actual stat name will be inserted)
 <br><br>
 
### Styling Examples
This is the CSS (Story's Stylesheet) used for the preview image:
<table><tr><td>

~~~css
#stats-table, .stats-cells tw-link {
  color: green;
  text-shadow: 2px 2px #00aa00;
}
.stats-cell-names {
	width: 220px;
}
.stats-cell-values {
  width: 40px;
  text-align: center;
}
.stats-cell-points{
  text-align: center;
}
#stat-cell-statpointpool-value{
  font-size: 2em;
}
~~~

</td><td>

![Imgur](https://i.imgur.com/bspIKNi.png)
</td></tr>
<tr><td>
Example with targeting a specific stat

~~~css
#stats-table, .stats-cells tw-link {
  color: green;
  text-shadow: 2px 2px #00aa00;
}
.stats-cell-names {
	width: 220px;
}
.stats-cell-values {
  width: 40px;
  text-align: center;
}
.stats-cell-points{
  text-align: center;
}
#stat-cell-statpointpool-value{
  font-size: 2em;
}
#stat-cell-name-charisma{
  color: hotpink;
  text-shadow: 2px 2px purple;
}
~~~
</td><td>

![Imgur](https://i.imgur.com/FwCVrnp.png)
</td></tr></table>
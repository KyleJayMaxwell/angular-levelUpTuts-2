# Angular Tutorial #2

### Using Ng-Repeat
In my example, I use **ng-repeat** and **ng-init**. In most cases of angular a controller is needed, but to begin with angular I am leaving it out to not complicate things. Now just like initializing angular with **ng-app** on the html, **ng-init** can be put on any html attribute. In the first example I just attach it to the body tag of the html, don't dwell on it too much I could've also just made a div and attached **ng-init** to it.

First Code Sample:  
```html
<body ng-init="soccerTeams = ['Arsenal FC', 'Real Madrid', 'Bayern Munich', 'PSG']">
  <ul>
    <li ng-repeat="team in soccerTeams">
      <p>{{team}}</p>
    </li>
  </ul>
</body>
```
If you copy and paste this code inside your angular app, a list of soccer teams should be on your browser. If not, check that yours is an **ng-app** and requiring angular.

In the body tag I just used **ng-init** to create soccerTeams and make it equal an array of soccer teams. When using **ng-repeat** there is a couple things that make it a bit tricky. With **ng-app** whatever it this directive is attached to will be html tag we will want repeating. In this is attached it to the list item because I wanted an unordered list of items. Then inside of **ng-repeat** I am calling the index value, team inside the array of soccerTeams. So after the `<p>{{team}}</p>` is now referring to each value inside the array and is repeating the list item with a p tag of the teams' name. 
Angular's way of syntax for **ng-repeat** `<div ng-repeat="(key, value) in myObj>"`
How I like to remember it **ng-repeat** `<div ng-repeat="item in array">`

The other tricky part of **ng-repeat** is that it's made for appending data to the page. So try to copy and paste the following inside your array, or make two values the same inside the array and refresh the page.
```html
<body ng-init="soccerTeams = ['Arsenal FC', 'Real Madrid', 'Bayern Munich', 'PSG', 'Arsenal FC']">
```

Now when you refreshed the page nothing showed, right? This is because **ng-repeat** uses $watchCollection, which monitors for changes in a collection. I'm not going to go more into $watchCollection, but it basically makes it so that there is a built in tracking function to make sure there isn't any duplicates items in the array. To get around this simply use `track by $index` after the array. 
In the example use this:
```html
<li ng-repeat="team in soccerTeams track by $index">
```

Last Example: 
```html
<body ng-init="soccerTeams = [{name:'Arsenal FC', league:'English Premier League'}, {name:'Real Madrid', league:'La Liga'}]">
  <ul>
    <li ng-repeat="team in soccerTeams">
      <p>Team: {{team.name}}, League: {{team.league}}</p>
    </li>
  </ul>
```

In my last example I use an array of objects instead of a typical array. Everything is the same as it was before except calling the key value, which is just like dot notation of javascript. So each of them have a name and a league which i refer to in the p tag. 




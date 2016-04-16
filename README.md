# Angular Tutorial #2

### Understanding Ng-Repeat
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


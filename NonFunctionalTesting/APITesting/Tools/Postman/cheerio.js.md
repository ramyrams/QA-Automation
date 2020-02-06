

[cheerio](https://cheerio.js.org/) - Fast, flexible & lean implementation of core jQuery designed specifically for the server.
	
	
	
	
```html
<div id="case-details">
	<h2>Case Details</h2>
	<ul>
		<li><span class="case-overview-label">Claim Number:</span> PMtest4172</li>
		<li><span class="case-overview-label">Patient ID:</span> 108762</li>
		<li><span class="case-overview-label">Contract ID:</span> 118734</li>
	</ul>
</div>
```

```javascript
//get number of li element in ul 
console.log($('div[id="case-details"]').find('ul > li').length);
=> 3
```

```javascript
//Loop through the all theli  elements in UL

const contInfo = [];

$('div[id="case-details"]').find('ul > li').each(function(i, elem) {
  console.log($(this).text());
  contInfo[i] = $(this).text();
});
=>
Claim Number: PMtest4172C
Patient ID: 108762
Contract ID: 118734
```

```javascript
//Loop though the list in the UL and access the value
console.log($('div[id="case-details"]').find('ul > li').slice(1).eq(0).text());
console.log($('div[id="case-details"]').find('ul > li').slice(2).eq(0).text());
console.log($('div[id="case-details"]').find('ul > li').slice(3).eq(0).text());
=>Claim Number: PMtest4172
Patient ID: 108762
Contract ID: 118734
```

```javascript
//First li element in the ul
console.log($('div[id="case-details"]').find('ul > li').first().text());
=> Claim Number: PMtest4172C
```

```javascript
//Last li element in the ul
console.log($('div[id="case-details"]').find('ul > li').last().text());
=> Contract ID: 118734
```

```javascript
// Get the title from HTML  
$('title')
```

```javascript
//Cheerio get parent element, title is child of head
let h1El = $('title');
let parentEl = h1El.parent();
console.log(parentEl.get(0).tagName)
=> head
```




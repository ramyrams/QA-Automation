

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


```javascript
$('span.comhead').each(function(i, element){
      // Select the previous element
      var a = $(this).prev();
      // Get the rank by parsing the element two levels above the "a" element
      var rank = a.parent().parent().text();
      // Parse the link title
      var title = a.text();
      // Parse the href attribute from the "a" element
      var url = a.attr('href');
      // Get the subtext children from the next row in the HTML table.
      var subtext = a.parent().parent().next().children('.subtext').children();
      // Extract the relevant data from the children
      var points = $(subtext).eq(0).text();
      var username = $(subtext).eq(1).text();
      var comments = $(subtext).eq(2).text();
      // Our parsed meta data object
      var metadata = {
        rank: parseInt(rank),
        title: title,
        url: url,
        points: parseInt(points),
        username: username,
        comments: parseInt(comments)
      };
      // Push meta-data into parsedResults array
      parsedResults.push(metadata);
    });
    // Log our finished parse results in the terminal
    console.log(parsedResults);
}
```

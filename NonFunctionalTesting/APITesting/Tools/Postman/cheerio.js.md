

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


```javascript
//Cheerio filter elements
let allEls = $('*');

let filteredEls = allEls.filter(function (i, el) {
    // this === el
    return $(this).children().length > 3;
});

let items = filteredEls.get();

items.forEach(e => {
    console.log(e.name);
});
```

```javascript
$("*") — selects all elements
$("#first") — selects the element with id="first"
$(".intro") — selects all elements with class="intro"
$("div") — selects all <div> elements
$("h2, div, p") — selects all <h2>, <div>, <p> elements
$("li:first") — selects the first <li> element
$("li:last") — selects the last <li> element
$("li:even") — selects all even <li> elements
$("li:odd") — selects all odd <li> elements
$(":empty") — selects all elements that are empty
$(":focus") — selects the element that currently has focus
```

```javascript
//Cheerio add element
let ulEl = $('ul');

ulEl.append('<li>Travel</li>');

let lis = $('ul').html();
let items = lis.split('\n');

items.forEach((e) => {
	if (e) {
		console.log(e.replace(/(\s+)/g, ''));
	}
});
```


```javascript
$("div.inline:nth-child(3) > p:nth-child(1) > span:nth-child(1)")
.text()
.trim()
		
		
$("#titleStoryLine > div:nth-child(10)")
.find("a")
.text()
.trim()
.split(" ")
//=>[ 'Action', 'Adventure', 'Crime', 'Drama', 'Mystery', 'Sci-Fi']


$(".poster >a:nth-child(1) >img:nth-child(1)")[0].attribs.src.split("@._")[0] + "@._V1_QL50.jpg"
```





const html = cheerio.load(text);

html("h2").each((index, element) => {
	headers.push(element.firstChild.nodeValue);
});

	
	
	



http://zetcode.com/javascript/cheerio/




  $('head + meta')
  







var data = [];
$('table tr td table tr').each(function(i, td){
	var children = $(this).children();
	var itemNum = children.eq(0);
	var itemName = children.eq(1);
}
	
	
console.log($('head title').html());




<body>
<a href="google.fr" class="test"></a>
<a href="yahoo.com" class="test"></a>
<a href="amazon.fr" class="test"></a>
<a href="linux.org" class="test"></a>
<a href="facebook.com" class="no_select"></a>
<a href="twitter.com" class="no_select"></a>
</body>

const links = $('.test').each( (index, elem) =>{
	console.log(elem.attribs.href);
});



//How do get script content using cheerio
console.log( $('script').get()[0] ); 
console.log( $('script').get()[0].attribs['src'] );
$('script').length;


// Get and print all attrubutes of all the link tags

<link href="/EDDG-Web/Images/favicon.ico" rel="icon" type="image/x-icon" />

$('link').each( (index, elem) =>{
	console.log(elem.attribs.href);
	console.log(elem.attribs.rel);
	console.log(elem.attribs.type);
});



<div class="info">
      <p>132 Purple Grove</p>
      <p>Albany, Texas 76801</p>
      <p class="phone">
          <span>Phone: (111) 111-1111</span>
      </p>
      <p class="fax">Fax: (111) 111-1111</p>
</div>

var addresslines=$('.info').children('p').filter(function(n, el){ 
  if(!$(el).hasClass('phone') && !$(el).hasClass('fax')){
    return el;
  }
});



<body>
  <a class="my_class" href="/" title="link"/>
</body>

$('.my_class').css('color')



try {
  const $ = cheerio.load(html)
} catch (e) {
  console.log(e) // handle error
}



//How do you clone a cheerio object

cheerio.load($.html())



//Get the 3 script detail 
var text = $('script');
console.log(text[3]);
console.log(text[3].type);
console.log(text[3].attribs.type);
console.log(text[3].attribs.src);


//Cheerio Get Image Src With No Class

<div class="container_c89a5 lazyLoadContainer_b1038">
	<img height="80" src="https://stuff.com" srcset="https://stuff.com" width="80">
</div>


a.find('.container_c89a5').find('img').attr('src');
a.find('.container_c89a5').children('img').eq(0).attr('src');



<select class="list_items">
  <option value="1">1</option>
  <option value="2">2</option>
  <option value="3">3</option>
  <option value="4">4</option>
</select>

$('.list_items').find('option').each((i,op) => {
   console.log($(op).text())
})

$(".list_items option").each(() => {
    console.log($(this).val());
});

//how to filter cheerio objects in `each` with selector?

<tr class="human">
    <td class="event"><a>event1</a></td>
    <td class="name">name1</td>
    <td class="surname"><a>surname1</a></td>
    <td class="date">2011</td>
</tr>


var results = $('tr.human')

    results.each(function(i, result){

       var date = result.children[3]
       var name = result.children[1]
       var surname = result.children[2]

       var object = {"name":name,"date":date,"surname":surname}
   })
   
   

<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.0/jquery.min.js"></script>
<div class="gallery-carousel">
<ul>
<li class="slide selected">
<button><img src="https://i.stack.imgur.com/rC97H.png" alt="hello" /> </button>
</li>
<li class="slide">
<button><img src="https://i.stack.imgur.com/1.png" alt="hello" /> </button>
</li>
<li class="slide">
<button><img src="https://i.stack.imgur.com/2.png" alt="hello" /> </button>
</li>
</ul>
</div>
 


let firstElem = $('.product-name a[href]').get()[0]
console.log($(firstElem).attr('href'));



//Apply selector on sub elements with cheerio
$('table').each((i, table) => { if ($(table).find("td:contains('Foo')").length > 0) {$('tr', table).each((i, tr)=>{console.log($(tr).text())})} })
 

var listItems = $(".gallery-carousel ul li");
listItems.each(function(idx, li) {
    let image=  $(li).find('img').attr('src'); 
    console.log(image);
    // and the rest of your code
});

const result = $('p[id="target-content"]').text();



//How to get immediate child in cheerio
$('html > body > font > table > tbody > tr').html()
console.log($('html > head').html());
console.log($('html > head > title').html());



//Getting hrefs under <li> from <ul> using Cheerio

<ul id="nav-products">
  <li><a class="" href="/shop/hats/">yellow good looking hat</a></li>
  <li><a class="" href="/shop/shoes/">cat feet holders</a></li>
</ul>


$('#nav-products LI A').each((i, el) => {
  console.log($(el).text());
  console.log($(el).attr('href'));
});

//How to loop through cheerio object in reverse?
const li = $('li');

for (let i = li.length - 1; i >= 0; i--) {
  $(li[i]).text();
}


//How do I get an element name in cheerio with node.js

   $ = cheerio.load('<input id="one" type="input" /><input id="two" name="some_name" />');

console.log( $('#one').attr('name') ); // undefined
console.log( $('#two').attr('name') ); // some_name

//How do I access table elements in cheerio?
var table = $('.g  table td')
var deptime = table.eq(5).text()
var city = table.eq(8).text()
var terminal = table.eq(6).text()




const list = $('div.titles li')

list.each((index, li) => {
  const title = $(li).find('p.title').text()

  console.log(title)
})


//Getting div text inside nested table td with Cheerio

<div class="ux-section-other">
  <h3 class="itemdetails-section-header right">More Info</h3>
  <div>
    <table class="ux-table-metadata">
      <tbody>
        <tr>
          <td>
            <div>Version</div>
          </td>
          <td>
            <div>1.7.0</div>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</div>

$(".ux-table-metadata > tbody > tr > td").each(function() {
    console.log($(this).children().html());
});

$(".ux-table-metadata > tbody > tr > td").each(function() {
    console.log($(this).find("div").html());
});



//Parse text from HTML form inside table cell with Cheerio
<tr class="row-class" role="row">
    <td>Text1</td>
    <td>
        <form method='get' action='http://example.php'> 

            <input type='hidden' name='id_num' value='ABCD123'> <!-- < I NEED THIS VALUE -->

            <button type='submit' class='btn' title='Check' ></button> 
        </form>
    </td>  
</tr>


$('tr').each(function(i, tr){
      var children = $(this).children('td');
      var x        = $(children[0]);
      var id_num   = $(children[1]).find("input[name='id_num']");
      var row = {
          "x":        x.text(),
          "id_num":   id_num.val()
      };
}



//How to write cheerio query for HTML structure?
var arr = [];
$(".content tr a").each(function (i, elem) {
  var a = $(elem);
  var text = a.text().trim().toLowerCase();
  arr.push(text);
});





<table class="content">
    <tbody>
        <tr>
            <th>head1</th>
            <td>value1</td>
        </tr>
        <tr>
            <th>head2</th>
            <td>value2</td>
        </tr>
    </tbody>
</table>
<table class="content">
    <tbody>
        <tr>
            <th>alpha1</th>
            <td>value4</td>
        </tr>
        <tr>
            <th>alpha2</th>
            <td>value5</td>
        </tr>
        <tr>
            <th>alpha3</th>
            <td>value6</td>
        </tr>
    </tbody>
</table>



var self = this;
    self.thejson = {};
    $('.content tr').each(function(index, value){
        var k = $('th', this).text(), v = $('td', this).text();
        self.thejson[k] = v;
    });
    return self.thejson;
	
	
//Getting text from Table Cheerio

$('#table-id > tbody > tr > td.data').toArray().map(item => {
  console.log($(item).text());
});

$('#table-id > tbody > tr > td.data').each(() => {
   console.log($(this).text());
});
	


Parsing a specific table in a html page that has multiple tables using cheerio

<table class = "one">
  <thead>..</thead>
  <tbody>
    <tr>
      <td>"Element 1<td>
    </tr>
  </tbody>
</table>
<table class = "one">
  <thead>..</thead>
  <tbody>
    <tr>
      <td>"Element 2<td>
      <td>"Element 3<td>          
    </tr>
  </tbody>
</table>



1) Use a :first-of-type, :last-of-type, :nth-of-type(n), :first-child, :last-child, or nth-child(n) selector. Some examples:

// to select rows in table 1:
$('table:first-of-type tr')
$('table:nth-child(1) tr')

// to select rows in table 2:
$('table:nth-of-type(2) tr')
$('table:last-child tr')
2) Use the built-in .first(), .last(), or .eq(n) filtering methods (or .filter() itself). With these, you'd select all tables, filter down to the table you want, then find all trs in that table.

// to select rows in table 1:
$('table').first().find('tr')
$('table').eq(0).find('tr')

// to select rows in table 2:
$('table').last().find('tr')
$('table').filter(i => i === 1).find('tr')




//selecting certain elements that ARE present in HTML string

$('table').eq(0).find('tr').eq(i+2).find('td').eq(2).find('font')

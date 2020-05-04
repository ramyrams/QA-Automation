## iterationData
https://postman-echo.com/get?city={{City}}&ramen={{Ramen}}


```javascript
pm.test("Body contains City", function () {
    
    pm.expect(pm.response.text()).to.include(pm.iterationData.get("City"));
    
    // older syntax still works too: with dot or bracket notation
    pm.expect(pm.response.text()).to.include(data.City); 
    console.log("City to be sent: " + data["City"]); 
});

pm.test("Body contains number of ramen searches", function () {
    
    pm.expect(pm.response.text()).to.include(pm.iterationData.get("Ramen"));
    pm.expect(pm.response.json())
        .to.have.property("args")
        .that.is.an("object")
        .to.include.keys("ramen");
        
    console.log("Number of ramen searches to be sent: " + pm.iterationData.get("Ramen"));
    
});

pm.test("Another way to check if Body contains number of ramen searches", function () {
    
    pm.expect(pm.response.json())
        .to.nested.include({
            'args.ramen': JSON.stringify(pm.iterationData.get('Ramen'))
        });
        
});
```


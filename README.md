# Weatherapp_frontend

## Description

The challenge is to build a weather dashboard that will run in the browser and feature dynamically updated HTML and CSS.
This web is built for users that likes to travel and checkout the weather outlook for multiple cities so users can plan a trip accordingly. 


## API Usage
 the 5 Day Weather Forecast Links to an external site.to retrieve weather data for cities. The base URL should look like the following: https://api.openweathermap.org/data/2.5/forecast?lat={lat}&lon={lon}&appid={API key}. After registering for a new API key, you may need to wait up to 2 hours for that API key to activate.

 ## Code Snippet: 
 ```
 jQuery( document ).ready(function() {
    parentElem= jQuery('.future-forcasts').find('.future-forcasts-blocks') 

    fetchApi=function(city){
        var coordinates = 'https://api.openweathermap.org/geo/1.0/direct?q=' + city + '&limit=1&appid=637d3ef92eb55ef9240a3ef3795ee168';

        fetch(coordinates)
            .then(response => response.json())
            .then(function (data) {
                var weather = 'https://api.openweathermap.org/data/2.5/forecast?lat=' + data[0].lat + '&lon=' + data[0].lon + '&units=imperial&appid=637d3ef92eb55ef9240a3ef3795ee168';

                fetch(weather)
                    .then(response => response.json())
                    .then(function (data) {
                        jQuery('.current-forcasts').find('.city').html(data.city.name)
                        displayInfo(data);
                        addButton(data.city.name);
                    })
            })
    }
```
## Demo 
![Untitled_ Nov 30, 2022 5_21 PM](https://user-images.githubusercontent.com/112473624/204944657-98467c18-0f80-4c76-b27f-908b1f632898.gif)


## Deployed link 

https://ginalguerrero.github.io/Weatherapp_frontend/ 

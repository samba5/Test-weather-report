# Test-weather-report
Github test weather report
1.	The application displays the 5 day weather for a given location.

Var app=angular.module(‘myapp’,[]);


app.controller('DemoCtrl', function($http) {

    var ctrl = this;

    var URL = 'http://api.openweathermap.org/data/2.5/forecast/daily';
    var city = document.getElementById("Seach key").value;
    var request = {
        method: 'GET',
        url: URL,
        params: {
            q: Edinburgh,
            mode: 'json',
            units: 'imperial',
            cnt: '7',
            appid: 'd20b7e069e7858118979c0ed0b36f8b5'
        }
    }

    function enterkey() {
        var enterk = event.keyCode || event.which;

        if (enterk == 13) {



    $http(request)
        .then(function (response) {
            ctrl.data = response.data;

            console.log(ctrl.data);
        })

}}
})

2. Select day, get 3 hourly forecast
    "Resource": {
        "dataDate": "2012-02-22T16:00:00Z",
        "res": "3hourly",
        "type": "wxfcs",
        "TimeSteps": {
            "TS": ["2018-07-02T06:00:00Z", "2018-07-02T09:00:00Z", "2018-07-02T12:00:00Z", 
}
    }
}
3. Daily forecast should summarise the 3 hour data:
•	Most dominant (or current) condition
•	Most dominant (or current) wind speed and direction
•	Aggregate rainfall
•	Minimum and maximum temperatures


•	Most dominant (or current) condition
$(document).ready(function () {
    $.getJSON("https://query.yahooapis.com/v1/public/yql?q=select%20item.condition%20from%20weather.forecast%20where%20woeid%20%3D%202487889&format=json&env=store%3A%2F%2Fdatatables.org%2Falltableswithkeys/", function (data) {
        console.log(data);
        console.log(query)
        $('#output').append( 'The temperature in' + result.location.["location = Edinburgh"] + 'is' + result.condition.["temp"] );
    })
})


•	Most dominant (or current) wind speed and direction
{"coord":
{"lon":145.77,"lat":-16.92},
"weather":[{"id":803,"main":"Clouds","description":"broken clouds","icon":"04n"}],
"base":"cmc stations",
"main":{"temp":293.25,"pressure":1019,"humidity":83,"temp_min":289.82,"temp_max":295.37},
"wind":{"speed":5.1,"deg":150},
"clouds":{"all":75},
"rain":{"3h":3},
"dt":1435658272,
"sys":{"type":1,"id":8166,"message":0.0166,"country":"AU","sunrise":1435610796,"sunset":1435650870},
"id":2172797,
"name":"Cairns",
"cod":200}

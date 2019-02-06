# Object.map-Modifier

Object.keys(images).map((key) => images[key] = 'url(' + '"' + images[key] + '"' + ')');

The purpose of the function is to take an object and modify the original contents of the object using a method available to all objects (objects and arrays alike) without returning an array. 

The reason that this works is due to the .map functions returning an array REQUIRING that you provide an explicit or implicit RETURN an array instead of simply modifying an existing object. You essentially trick the program into thinking the object is an array by using Object.keys which will allow you to use the map function with its acting on the values the individual keys are associated with. As long as there isn't a return, there will be no array created with the original object stil intact and modified as programmed. 

This particular program takes an object called images and takes the values of its keys and appends url tags for use within another function. Original is this:

var images = {
                snow: 'https://www.trbimg.com/img-5aa059f5/turbine/bs-md-weather-20180305',
                sunny: 'http://www.cubaweather.org/images/weather-photos/large/Sunny-morning-east-Matanzas-city-
                Cuba-20170131-1080.jpg',
                rain: 'https://i.pinimg.com/originals/23/d8/ab/23d8ab1eebc72a123cebc80ce32b43d8.jpg'
            };
            
...and modified is this:
var images = {
                snow: url('https://www.trbimg.com/img-5aa059f5/turbine/bs-md-weather-20180305'),
                sunny: url('http://www.cubaweather.org/images/weather-photos/large/Sunny-morning-east-Matanzas-city-
                Cuba-20170131-1080.jpg'),
                rain: url('https://i.pinimg.com/originals/23/d8/ab/23d8ab1eebc72a123cebc80ce32b43d8.jpg')
            };
            
The object's original structure is left intact allowing for normal property access as long as there isn't a return.

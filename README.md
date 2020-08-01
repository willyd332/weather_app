# Weather Object Lab


Title: **Let's talk about the weather**<br>
Type: Lab<br>
Creator: Reuben Ayres<br>
Competencies: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Objects, Mixed datatypes.**<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Reading documentation.**<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Breaking bigger problems into smaller ones.**<br>
             
<hr>

## Let's talk about the weather

Notice that at the bottom of this file under ["The Data"](#the-data) is an enormous object. It describes the weather in Evanston over a period from 3/16/2018 to 3/21/2018. It's simply too large for a human to read in any reasonable amount of time. Therefore, visit this link: [OpenWeatherMap.org API Documentation](http://openweathermap.org/forecast5#JSON). 

It contains an explanation of how to use this data. Focus on the bulleted list with the red property names under "Parameters," under "JSON," under "Weather parameters in API respond"—the above link should take you pretty close to there on the page. **Remember**: JavaScript objects do not guarantee that properties will be in any particular order. Also pay attention to what the notation/brackets/parentheses tell you about what data types you're working with. 

Read each question closely, and don't worry about anything other than what you're being asked to do. There is more information on this API documentation page than you need, including stuff we have not talked about.  This is common when using outside resources.  You should practice finding just the information you need in more complex contexts.

### Questions

#### For this assignment, and every assignment, read **all** of each question carefully before you start doing any work.

1. Access the city information using some kind of object notation.
    * print the name of the city in the console.
    * by pulling the city name and the latitude and longitude out of the object and interpolating them, print a sentence in the console that reads: `"The coordinates of Evanston are 42.0447 latitude and -87.6931 longitude."`
    * put all of the above logic in a function called `getCity` that takes the entire object as a parameter and uses that parameter to get the data, and additionally uses it to return the city name (and call the function within your code).

2. Write logic to console.log the weather description for 3-20 at 6pm. Make the output a nice English sentence.

3. Write logic to print out the forecasted temperature for 3-20 at 9am.  Make the output a nice English sentence, and code any conversion necessary (Temp is given in Kelvin)

4. Write logic to find wind speed and direction on St. Patrick's day at 3pm.  Do some googling to figure out how to convert meters/second to mph, and how to convert the meteorological description of wind direction into human-understandable format. Write logic to do the conversions (don't just plug 3m/s in mph into Google or some other online converter).  When you get it all figured out, you will use all of it to console.log a sentence that reads "The wind will be blowing (some cardinal direction that you will figure out--N, NE, E, SE, S, SW, W, NW are the choices) at (whatever mph you calculated from the given m/s).  There is a pretty substantial amount of research and calculation required to do this, plus thinking outside the box.

5. Write logic to print the humidity each day at noon.  If it's over 75%, also print the word "gross" in parentheses like this:

```
2014-06-19: 60%
2014-06-20: 77% (gross)
etc
```

6. So, by now you've noticed that you're given the weather data for 3 hour time increments. For this question, write logic to figure out the high and low temp for each day, as well as a description of the weather overall for the day. You will create an object that stores all of it, as follows:<br>
• the date in a human-friendly format (like "Tue, Jan 30, 1997"--research JavaScript date stuff on MDN to see how to convert)<br>
• the high temp for that day (use the highest of the 8 values for a given day, don't forget to convert Kelvin to F -- again write logic to do this)<br>
• low temp (again, use the lowest of the 8 values for a given day, converted)<br>
• the weather description for that day -- this will be the weather description that occurs the 'most frequently.'  if multiple descriptions occur an equal number of times in a day, you can use whichever you like. <br><br>
After each object is built, push it into an array called `myWeather`.<br><br>
This will take some thinking. Plan out the steps required for each step carefully before you start writing code. You can use pencil and paper for this, or write on the desks/glass walls with dry erase marker.  You may end up writing temporary code that you later replace with different code--that is a very common practice for developers.<br><br>
I'd suggest just getting it working for one piece of data for one day, then all the data for a day, before writing the final code to do all the days.

7. Put all of the logic (but don't delete your question 6 answer) from the previous question into a function called `getWeatherArray` that again takes the entire huge `evanstonWeather` object in as a parameter called `data`, and works with that parameter (instead of with the original object) to build and return an array like the `myWeather` one from the previous question. Refactor the logic as necessary to use the parameter to generate the objects/array of objects. <br><br>So your function might start out like this: 

    ```javascript
    const getWeatherArray = (data) => {
      // logic similar to question 6
    }
    ```
    You should then be able to use your function like this:

    ```javascript
    const myWeatherArray = getWeatherArray(evanstonWeather);
    ```

    **Refactoring**

    Changing/improving the organization of code without really changing the functionality is called **refactoring**. You just refactored code. Nice job.  That's something developers do all the time.

8. Write _another_ function `printForecast` that iterates over the array returned by `getWeatherArray` and console.logs the 5-day forecast data like this:<br>

    ```
    -------------------
    Date: Tue, Jan 30, 1997
    Weather: clear
    High Temp: 13°F
    Low Temp: 2°F
    -------------------

    -------------------
    Date: Wed, Jan 31, 1997
    Weather: heavy snow
    High Temp: 23°F
    Low Temp: 12°F
    -------------------

    etc....
    ```

<hr>

Thanks OpenWeatherMap for an awesome learning tool. This data came from an API call to one of their endpoints. Material reused acccording to the [Creative Commons License](https://creativecommons.org/licenses/by-sa/4.0/) as described in the [OpenWeatherMap Terms of Service](https://openweathermap.org/terms).


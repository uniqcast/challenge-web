# Challenge: Web

The goal of this challenge is to build a single page web application for weather forecast. Application should be built with vanilla HTML, CSS and JS technologies, and should work in all major browsers.

## Application Behaviour

This application should display 7 day weather forecast for the desired city in Croatia.

1. Page consists of header and body.
2. Body consists of form for city selection and 7 day weather forecast for selected city.
    * If there is no city selected, usage text should be displayed instead of weather forecast, e.g. "Enter a city name and press the button to retrieve 7 day weather forecast."
    * If there is no data for the requested city or any other API error, appropriate message should be displayed instead of weather forecast.
3. Form for the city selection consists of text input field and submit button.
    * It should be possible to submit form by pressing the enter key.
    * Form submission should be prevented if the input field is empty.
4. Weather forecast consists of city name and 7 boxes where each box contains weather information for the specific day.
    * First box shows information about current day.
    * Each box consists of title, minimum, maximum and average temperature (in Celsius).
    * The title should contain week day and date, e.g. `Monday, 17.06.19`.

## Design

Design and graphical assets are located in the `assets` folder.

Fonts used are *Roboto* and *Roboto Condensed*, where base font size is 16pt and line height is 24pt.

Elements of the application which are not provided in the design can be implemented in any desired way.

## Application Requirements

1. The application should have a favicon and title, where favicon should be created from the provided logo image.
2. The application should be responsive, i.e. the user should be able to use application on a mobile phone without zoom actions. It's up to the developer how the design is going to be transformed on smaller screens.
3. Weather forecast data should be retrieved with HTTP GET request (HTTP REST API). See *Appendix A*.
4. The application should work in modern browsers, i.e. Chrome 70+, Edge 18+, Firefox 70+ and Safari 12.1+.

## Technical Requirements

1. Image files should be optimized (minified).
2. Minified CSS and JS files should be placed alongside source files. For example, alongside `style.css` should be `style.min.css` which contains the minified source of the original file.
3. All files should have Unix line endings and should be encoded in UTF-8.

## Code Requirements

1. Clean and consistent coding style.
2. Semantic HTML without CSS and JS.
3. Each selector should appear only once in the CSS source file.
4. JS code should be organized into functions.

## Appendix A

One should register on [Weatherbit](https://www.weatherbit.io/) to get a free API key.

Weather forecast for 7 days should be extracted from the endpoint which provides a 16 day forecast for the requested city. The official documentation for the endpoint can be found at the [Weatherbit website](https://www.weatherbit.io/api/weather-forecast-16-day).

```
# Get 16 day weather forecast for Zagreb in JSON format
GET http://api.weatherbit.io/v2.0/forecast/daily?city=Zagreb,HR&key=API_KEY

Relevant properties:
- city_name
- data[i].valid_date
- data[i].temp
- data[i].max_temp
- data[i].min_temp
```

---

*This project is licensed under the terms of the MIT license.*

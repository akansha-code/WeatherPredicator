# Weather Service

## Overview
This project implements a microservice to show the weather forecast for a given city, including high and low temperatures for the next 3 days. It also provides additional advisories such as carrying an umbrella for rain, using sunscreen lotion for high temperatures, and warnings for high winds and thunderstorms.
## Flowchart

![Weather Flow Chart](https://github.com/swathithota/weather/blob/main/src/main/resources/static/weatherFlowChart.png)

## Design Patterns:
1. **Layered Architecture**: Presentation -> Validation -> Service
2. **Singleton Pattern**: RestTemplate to be singleton to be shared across application
3. **DTO(Data  Transfer Object)** : Transferring data between service and client
4. **Error Handling**: Specific custom exceptions are thrown
5. **Dependency Injection**: @Autowire, @Component used to ensure loose coupling and enhance testing
6. **Strategy**: Weather Processing based on parameter using Strategy Pattern
## Approach Used
1. **Fetching Weather Data**: Utilized the OpenWeatherMap API to fetch weather forecast data for the specified city.
2. **Parsing and Processing Data**: Parsed the JSON response from the API to extract relevant weather information, including temperatures, weather conditions, and timestamps.
3. **Applying Additional Conditions**: Analyzed the weather data to apply additional conditions specified in the requirements, such as rain, high temperatures, high winds, and thunderstorms.
4. **Preparing Output**: Formatted the extracted information into a human-readable output, including dates, high and low temperatures, and any advisories.
5. **Using RestTemplate**: Utilized Spring's `RestTemplate` to make HTTP requests to the OpenWeatherMap API, providing flexibility in request handling and response parsing.
6. **Error Handling**: Implemented error handling to gracefully handle exceptions and provide meaningful error messages to the user.

## Dependencies
- Java: 17
- Spring Framework: 5.x
- org.json: Used for parsing JSON responses from the OpenWeatherMap API.
- Spring Boot: Used for bootstrapping the application.

## Installation
1. Clone the repository: `git clone <repository-url>`
2. Build the project: `mvn clean install`
3. Run the application: `java -war target/weather-service.war`

## Usage
- Endpoint: POST Request `http://localhost:8080/weather/api/weather-prediction/v1/forecast`
- Example: `http://localhost:8080/weather/api/weather-prediction/v1/forecast`
- PayLoad : Replace {city} with value, {maxCount} with maxCount
{
  "data": {
  "serviceAttributes": {
  "location": "{city}"
  },
  "maxRecordsDetails": {
  "maxCount": {maxCount}
  }
  }
  }

- Web App URL: `http://localhost:8080/weather/`
 Enter City name in Text Box and click on Get Weather Forecast button
## Configuration
- API Key:  `{api.key}` in the `WeatherService.java` file  configured via application.yaml
- API_URI: `{api.uri}` in the `WeatherService.java` file configured via application.yaml

## Contributing
Contributions are welcome! Please open a pull request or issue to suggest improvements or report bugs.


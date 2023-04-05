# Historical-Flight-Schedules-API
Historical airport timetable data with delays and cancellations for airports globally.

<div id="header" align="center">
  <img src="https://media.giphy.com/media/LRZc4dV2kf787nbOB3/giphy.gif" width="100"/>
</div>

[Aviyair’s Historical Flight Schedules API](https://aviyair.com/historical-flight-schedules-api/) provides past airport timetable data that goes as early as 1 year from the current date. The global coverage allows the integration of historical flight schedule data by businesses in any market. The REST structure returns JSON data with GET requests and other formats may be added in the future. Let us know if you have demand for a specific format!

The API provides past airport schedule data with static data such as the flight number, airline, departure and arrival airports etc. as well as changeable flight schedule data such as the latest recorded flight schedule (landed, cancelled, etc.), total delay measured in minutes, baggage belt, and more.

Get complete past airport schedule data for an airport in a single call or narrow down the data to flights of a certain airline, flight number, status and others.

--------

## Main Endpoint and Filters with Description

**GET** `https://data.aviyair.com/data/v1/historicalschedule?key=[APIKEY]&airport_iata=IAD&type=departure&date_from=2022-05-24`


Airport IATA code and schedule type (can be either departure or arrival) are obligatory fields. You can add the below filters to narrow down the flights within the schedule.

| Request Parameter  | Description |
| ------------- | ------------- |
| airport_iata  | The IATA code of the requested airport |
| type  | Schedule type (can be departure or arrival) |
| date_from | The start of the date range for which you search for flight schedules |
| date_to | The end of the date range for which you search for flight schedules. The maximum date range is around 5 days but may be shorter if the size of the output is on a larger scale, such as in big airports with high air traffic |
| departure_iata | Three-letter IATA code for the departure airport|
| arrival_iata | Three-letter IATA code for arrival airport|
| airline_iata  | Filter the flights in the schedule down to a certain airline’s flights  |
| flight_number  | Use this filter to track individual flights based on its flight number |

------

## 200 OK Response Example

```
{
  "status": {
    "message": "Success"
  },
  "results": {
    "departure": {
      "iataCode": "iad",
      "icaoCode": "kiad",
      "delay": "21",
      "scheduledTime": "2022-05-23t20:40:00.000",
      "estimatedTime": "2022-05-23t20:40:00.000",
      "actualTime": "2022-05-23t21:00:00.000",
      "estimatedRunway": "2022-05-23t21:00:00.000",
      "actualRunway": "2022-05-23t21:00:00.000"
    },
    "arrival": {
      "iataCode": "doh",
      "icaoCode": "othh",
      "baggage": "3",
      "scheduledTime": "2022-05-24t16:35:00.000",
      "estimatedTime": "2022-05-24t16:24:00.000"
    },
    "airline": {
      "name": "american airlines",
      "iataCode": "aa",
      "icaoCode": "aal"
    },
    "flight": {
      "iataCode": "aa8120",
      "icaoNumber": "aal8120",
      "number": "8120"
    },
    "codeshared": {
      "name": "qatar airways",
      "iataCode": "qr",
      "icaoCode": "qtr"
    }
  }
}
```

-------


## Full Documentation

Please visit our [website]( https://aviyair.com/documentation/).

-------

## Most Popular Use Cases

These are the most common use cases for the Historical Flight Schedules API but there are no limitations regarding how the API can be useful for you. If you have any concerns about the Terms and Conditions for the global flight schedule data, you may visit the hyperlink below or contact us to ask about it.

-	Historical interactive timetables where people can track the latest recorded status and delay information of a flight
-	Historical flight schedule data source for flight delay and compensation claims
-	Analysis for the operational efficiency of airports or airlines based on historical data and building data-driven solutions to increase this
-	Machine learning and analysis projects, powered by historical flight data to predict future average delays and cancellations
- 	Flight schedule tracking for booking or travel websites and apps
-	Flight status tracking for travel agencies and airport greeting services
-	Academic or commercial projects that focus on analyzing air traffic before or after a certain major event, such as COVID-19
- 	Airport operation and staff planning and improvements based on air traffic data per terminal or the whole airport
- 	Route efficiency comparison

---------

## License

[Terms and Conditions of Use](https://aviyair.com/terms-and-conditions/) apply. If you have any questions or concerns about your use case of the Flight Tracker and Status API, please [contact us](https://aviyair.com/contact-aviyair/). 

--------

## How to Access

The API key to access historical flight schedule data is possible by creating an API subscription. The subscriptions do not require any commitments. It is possible to cancel anytime or make changes to your subscription level.

[View the prices and get an API key here.](https://aviyair.com/pricing-subscription-plans/)

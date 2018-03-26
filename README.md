# Geohashing Exercise

Implement a geohashing restful service, as described in XKCD:

![XKCD](https://cloud.githubusercontent.com/assets/68388/14025469/9e271cbc-f1c4-11e5-90f7-0166892454f4.png)

Given the following request:

```shell
$ curl -i http://localhost:9292/geohash?lat=37.421542&lon=-122.085589
```

Then a response similar to the following is expected:

```shell
HTTP/1.1 200 OK
Content-Type: application/json;charset=utf-8
Content-Length: 35

{"lat":37.857713,"lon":-122.544543}
```

#### Query to obtain opening value:

```
curl "https://www.alphavantage.co/query?function=TIME_SERIES_DAILY&symbol=NDX&apikey=$key"
```

*Due to Yahoo/Dow Jones Index restrictions you can no longer get DOW opening this way. Instead use ^NDX* (NASDAQ-100)

#### Extra credit items to consider

- Accept lat/lon as POST body parameters
- Cache the DOW opening API call to occur once per day (in memory)
- Implement a in memory cache to store already processed coordinates and their results
- Fetch place name for destination coordinates
- Fetch place name for origin coordinates
- Return the calculated distance between the pair of coordinates

# 💾 soar-db

---

## 📖 Overview

**soar-db** provides a reliable, developer-friendly REST API that aggregates and normalizes comprehensive flight information for the Jade Wings airline. From real-time schedules to historical performance analytics, this service powers data-driven aviation applications.

> 💡 **Primary Use Case**: Currently serving as the core data infrastructure for [JadeWings](https://www.jadewings.com).

## ✨ Features

[//]: # (- 🔄 **Real-time Updates** - Live flight schedules and status tracking)
- 📊 **Historical Data** - Complete flight histor
- 🌏 **Route Data** - Comprehensive network coverage and frequency data
- ✈️ **Fleet Data** - Detailed aircraft information and configurations
- 📈 **Analytics Metrics** - On-time rates, delays, and cancellation statistics
- 📅 **Schedule Update** - Update flight schedule based on latest official news

## 🗂️ Data Sources

Our data is aggregated from multiple authoritative sources to ensure accuracy and completeness:

| Source              | Type               | Update Frequency |
|---------------------|--------------------|------------------|
| **FlightRadar24**   | Historical data    | Monthly          |
| **Flightera**       | Historical data    | Weekly           |
| **The JadeWings**   | Official data      | Monthly          |
| **Aviation Forums** | Community insights | As available     |

> ⚠️ **Note**: Data availability and freshness may vary by source.
 
## 📡 API Endpoints

| Endpoint                                      | Description                                    | Parameters                                       |
|-----------------------------------------------|------------------------------------------------|--------------------------------------------------|
| **GET** `/api/v1/flights/schedule`            | Fetch flight schedules                         | `airline`, `origin`, `destination`, `from`, `to` |
| **GET** `/api/v1/flights/{flightNum}/history` | Get historical data for specific flight        | `limit` (default: 50)                            |
| **GET** `/api/v1/routes/example/{flightNum}`  | Get an actual route example in CSV format      | -                                                |
| **GET** `/api/v1/performance`                 | Performance metrics                            | (developing)                                     |
| **GET** `/api/v1/aircraft/{registration}`     | Get aircraft details and last 10 flown records | limit (default: 10)                              |

### Example:

Get Schedule Request >
```bash
curl -X GET "https://{doimain}.com/api/v1/flights/schedule?origin=HKG&destination=LHR&from=2025-01-01&to=2025-01-31"
```

Get Schedule Response >
```json
{
  "data": [
    {
      "JWs251": {
        "origin": "HKG",
        "destination": "LHR",
        "operated_weekdays_count": 7,
        "operated_weekdays": {
          "Sun": true, "Mon": true, "Tue": true,
          "Wed": true, "Thu": true, "Fri": true, "Sat": true
        },
        "distance": {
          "km": 9641,
          "mi": 5951
        },
        "average_flight_time": "14:00"
      }
    }
  ],
  "meta": {
    "total": {
      "pax": 6,
      "frtr": 2
    },
    "last_updated": "CX548-9-20T00:00:00Z"
  }
}
```
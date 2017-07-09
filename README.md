# Bookwhen Open Data

## Open Data Endpoint
https://bookwhen.com/api/openactive/event_types - a feed of the event data from participating bookwhen customers
https://bookwhen.com/api/openactive/events - a feed of the event booking data from participating bookwhen customers

## Standards
The data is published to conform to [Openactive Realtime Paged Data Exchange 0.2.3](https://www.openactive.io/realtime-paged-data-exchange/0.2.3/).

## Issues, Questions and Comments
Please raise any issues, questions or comments as a [new issue in this repository](https://github.com/bookwhen/opendata/issues).

## Event Type Data Fields

| Data Field | Example Value | Description |
| ---------- | ------------- | ----------- |
| identifiers | entry-43434 | Entry ID with prefix |
| name | Insanity - Marylebone Mon 6:30pm | Entry.Title |
| description | Insanity - Marylebone Mon 6:30pm | Entry.Details converted to plane text |
| beta:formattedDescription | `Insanity - Marylebone Mon 6:30pm<br/>` | Entry.Details raw HTML / Markdown |
| maximumAttendeeCapacity | 20 | Maximum attendees (include if set) |
| category | [Tag1, Tag2] | Tags |
| location.identifier | location-105 | Location ID with prefix |
| location.address | St Marylebone Church of England School 64 Marylebone High Street W1U 5BA | Address/location (Present if map is shown) |
| location.geo.latitude | 51.4961 | Latitude from map marker (Present if map is shown) |
| location.geo.longitude | -0.024559 | Longitude from map marker (Present if map is shown) |
| location.description | All members must sign in at school reception | Additional location information |
| location.name | Tiller Leisure Centre | Address/location (Present if map is not shown) |
| subEvent[].eventSchedule.startDate | 2017-07-11 | Start date of schedule (Present on recurring occurrences) |
| subEvent[].eventSchedule.endDate | 2017-12-31 | Repeat until this date, do not include this key if forever (Present on recurring occurrences). |
| subEvent[].eventSchedule.count | 10 | Use instaed of endDate if For a number of events (Present on recurring occurrences) |
| subEvent[].eventSchedule.frequency | weekly | One of minutes, hourly, daily, weekly, monthly, yearly (Present on recurring occurrences) |
| subEvent[].eventSchedule.byDay | [http://schema.org/Sunday] | Array of days of week with 'http://schema.org/' prepended (Present on recurring occurrences) |
| subEvent[].eventSchedule.byMonthDay | 2 | For monthly, same day every month - day of the month. positive integer, 1-31 (Present on recurring occurrences) |
| subEvent[].eventSchedule.startTime | 19:00 | Start time (Present on recurring occurrences and if not all-day event) |
| subEvent[].eventSchedule.endTime | 20:00 | Start time + duration (Present on recurring occurrences and if not all-day event) |
| subEvent[].eventSchedule.exceptDate | [2017-07-18T19:00:00Z, 2017-07-25T19:00:00Z] | Exception dates for this schedule (Present on recurring occurrences) |
| subEvent[].eventSchedule.interval | 2 | Every X weeks, years etc  (Present on recurring occurrences) |
| subEvent[].startDate | 2017-07-25T19:00:00Z | Start date/time of event (Present on non-recurring occurrences) |
| subEvent[].endDate | 2017-07-25T20:00:00Z | Start date/time of event + duration (Present on non-recurring occurrences) |
| subEvent[].duration | PT60M | Duration converted to ISO spec. (Present on non-recurring occurrences) |
| offer[].name | Single Class Membership | Booking/ticket type title |
| offer[].description | One off ticket for sale! | Additional booking/ticket information |
| offer[].price | 33.00 | Price |
| offer[].priceCurrency | GDP | Currency price is in. |
| offer[].validFrom | 2017-07-25 | Absolute date from when the ticket/booking is available from. |
| offer[].validThrough | 2017-07-25 | Absolute date from when the ticket/booking is available to. |
| offer[].beta:groupTicket.beta:minPeople | 2 | Minimum people required for group booking. |
| offer[].beta:groupTicket.beta:maxPeople | 5 | Maximum people required for group booking. |
| offer[].beta:groupTicket.beta:course | true | Is the ticket/booking a course booking. |

## Event Type Data Fields

| Data Field | Example Value | Description |
| ---------- | ------------- | ----------- |
| superEvent.identifier | entry-43434 | Entry id of event booking belongs to |
| identifier | bookedOccurrence-73 | identifier of the booking |
| startDate | 2017-07-25T19:00:00Z | Start date of booking |
| endDate | 2017-07-25T20:00:00Z | End date of booking |
| remainingAttendeeCapacity | 4 | Number of spaces remaining |
| beta:attendanceCount | 3 | Number of spaces taken |

## Changelog

| Date | Changes |
|---|---|
| 9/7/2017 | Added Event Data Fields |
| 9/7/2017 | Added Event Type Data Fields |
| 5/7/2017 | Initial version published |

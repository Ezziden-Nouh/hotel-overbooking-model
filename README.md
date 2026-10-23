# Hotel-overbooking-model
Excel model recommending an overbooking policy for a city hotel, built on 79k bookings

## Recommendation
Blended across all bookings, the hotel would need to accept about 72% more bookings than it has rooms to expect a full house. But that single rate is misleading — show-up rates range from 36% on bookings made six months ahead to 88% on bookings made within a week, so a flat policy would either leave rooms empty or walk guests. The recommendation is to set the rate per arrival date based on the booking mix.

## The question
How many bookings the hotel should accept above capacity, and what that policy is worth. The decision belongs to a revenue manager setting booking policy.

## Data
Hotel Booking Demand, Antonio/Almeida/Nunes 2019.
Jul 2015 - Aug 2017. 119,390 rows, filtered to City Hotel: 79,330

## What the data shows
Cancellation rate by lead band: 10% / 29% / 39% / 47% / 64%.
Cancellations and no-shows are kept separate throughout. A cancellation gives notice and a chance to resell the room; a no-show gives neither.

## Decisions and assumptions
Duplicates kept - 35% of rows, 72% in Groups and Offline TA/TO,
consistent with block bookings. Removing them drops the rate
from 41% to 29%.
Capacity 124 rooms = 99th percentile of daily arrivals.
Average daily rate 105.30 euros , margin 70%, walk cost 315.


## Limitations
- Capacity is a proxy, not a measurement — the dataset has no room inventory.
- Arrival-date grain undercounts occupied rooms: a guest arriving
  Monday for three nights occupies a room Tuesday and Wednesday
  without appearing in those days' counts.
- The blended 58% show-up rate hides a 36%-88% spread across lead bands.
- Walk cost is a judgement input and was not tested for sensitivity.

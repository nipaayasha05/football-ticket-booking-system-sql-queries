# Football Ticket Booking System -SQL Queries

### 1. Users Table

This table tracks all administrative staff and customers who use the platform.

| **Field Name** | **What the Field Does**                                          |
| -------------- | ---------------------------------------------------------------- |
| `user_id`      | Unique identification number for each registered user.           |
| `full_name`    | Stores the first and last name of the user.                      |
| `email`        | Stores the user's mail address used for login.                   |
| `role`         | Defines access permissions (`Ticket Manager` or `Football Fan`). |
| `phone_number` | Stores the contact mobile number of the fan.                     |

### 2. Matches Table

This table catalogs the tournament events, stadium logistics, and baseline ticket inventory pricing.

| **Field Name**        | **What the Field Does**                                                                   |
| --------------------- | ----------------------------------------------------------------------------------------- |
| `match_id`            | Unique identification number for each football match.                                     |
| `fixture`             | Tracks the two competing teams (e.g., _Real Madrid vs Barcelona_).                        |
| `tournament_category` | The league or cup title (e.g., _Champions League_, _Premier League_).                     |
| `base_ticket_price`   | The foundational price for a single standard entry seat.                                  |
| `match_status`        | Current ticket availability state (`Available`, `Selling Fast`, `Sold Out`, `Postponed`). |

### 3. Bookings Table

This transactional table records individual ticket purchases by linking users to their chosen matches.

| **Field Name**   | **What the Field Does**                                                        |
| ---------------- | ------------------------------------------------------------------------------ |
| `booking_id`     | Unique tracking transaction number for the ticket purchase.                    |
| `user_id`        | Links the booking directly to the user who made the purchase.                  |
| `match_id`       | Links the booking directly to the specific match being attended.               |
| `seat_number`    | The specific allocated seat identifier in the stadium (e.g., `A-12`).          |
| `payment_status` | Tracks financial resolution (`Pending`, `Confirmed`, `Cancelled`, `Refunded`). |
| `total_cost`     | The calculated final invoice price based on the base price and seat quantity.  |

- Query 1: Retrieve all upcoming football matches belonging to the 'Champions League' where the match status is 'Available'.

- Query 2: Search for all users whose full names start with 'Tanvir' or contain the phrase 'Haque' (case-insensitive).

- Query 3: Retrieve all booking records where the payment status is missing (`NULL`), replacing the empty result with 'Action Required'.

- Query 4: Retrieve match booking details along with the User's full name and the scheduled Match fixture teams.

- Query 5: Display a comprehensive list of all users and their booking IDs, ensuring that fans who have _never_ bought a ticket are still listed.

- Query 6: Find all ticket bookings where the total cost is strictly higher than the average cost of all ticket bookings.

- Query 7: Retrieve the top 2 most expensive matches sorted by base ticket price, skipping the absolute highest premium match.

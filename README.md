# swiggy_data
# Swiggy Scraped Dataset – Data Cleaning Report

Key Cleaning Steps

1. Split `rating_and_delivery_time`
- Original column combined values like `"4.3 • 30 mins"` or `"NEW"`.
- Created two new columns:
  - `rating`: Extracted numeric rating (or "NEW"/blank where applicable).
  - `time_minutes`: Extracted delivery time as a number (e.g., 30).

2. **Extract Offer Details**
- Original column contained complex strings like:
  - `"30% OFF UPTO ₹75 ABOVE ₹150"`
- Extracted into two new structured columns:
  - `offer_percentage`: Discount percentage (e.g., `30`)
  - `offer_above`: Minimum order value (e.g., `150`)
- If offer was not applicable, filled with `"not_available"`.

3. **Standardized `food_type` (Cuisines)**
 Removed inconsistent casing and whitespace.
 Ensured cuisines are comma-separated and properly capitalized (e.g., `"Fast Food, Beverages"`).

4. Formatted `location`
 Removed leading/trailing spaces.
 Standardized naming conventions across locations.

5. Cleaned `hotel_name`
 Removed unwanted whitespace and ensured consistent capitalization for brand names.

6. Handled Missing Values
 Delivery time (`time_minutes`) is not available for all entries.
 Explicitly retained missing or unavailable data to allow flexible handling in future analyses.




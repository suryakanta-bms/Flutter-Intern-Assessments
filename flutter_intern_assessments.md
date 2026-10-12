# Flutter Intern Assessments

## Overview

Choose **one** of the three app options below and build it using Flutter and Dart.

- **Goal:** Demonstrate your Flutter fundamentals and ability to integrate a public REST API.
- **API access:** Use the public APIs listed for the selected option. No paid API subscription or API key is required for the suggested endpoints.
- **UI:** Create a clean, usable interface. A reference design is not required.
- **Packages:** You may use `http` or Dio, and any reasonable state-management approach.

Please build only **one** app. Focus on correct functionality, readable code, and handling API states rather than adding lots of features.

---

## Option 1: Product Catalog App

### API

- Base endpoint: `https://dummyjson.com/products`
- Documentation: https://dummyjson.com/docs/products

### Required features

1. Fetch products from the API and display them in a list or grid.
2. Show at least the product image, title, price, and rating.
3. Open a product details screen when a product is selected.
4. Include search by product title.
5. Include category filtering. You may use the API's category endpoints or filter the fetched data locally.
6. Display a loading indicator while fetching data.
7. Display a useful error message and a retry action if the request fails.
8. Handle an empty result set gracefully.

### Optional bonus

- Add pagination or a “Load more” action using the API's `limit` and `skip` parameters.
- Add pull-to-refresh.
- Show additional details such as description, category, discount, or stock.

---

## Option 2: Blog Reader App

### API

- Posts: `https://jsonplaceholder.typicode.com/posts`
- Comments for a post: `https://jsonplaceholder.typicode.com/posts/{postId}/comments`
- Documentation: https://jsonplaceholder.typicode.com/guide/

### Required features

1. Fetch posts and display them in a scrollable list.
2. Show each post's title and a short preview of its body.
3. Open a post details screen showing the full title and body.
4. Fetch and display comments for the selected post.
5. Include search by post title.
6. Display loading and error states for API requests.
7. Provide a retry action when a request fails.
8. Handle an empty posts list or a post with no comments gracefully.

### Optional bonus

- Add pull-to-refresh.
- Show the number of comments for a post.
- Add a simple way to sort posts, such as by ID.

**Note:** JSONPlaceholder is a testing API. Write operations, if attempted, are simulated and are not persisted. Creating or editing posts is not required.

---

## Option 3: Weather App

### API

- API documentation: https://open-meteo.com/en/docs
- Geocoding API: `https://geocoding-api.open-meteo.com/v1/search?name={city}&count=5&language=en&format=json`
- Current weather example (Bengaluru): `https://api.open-meteo.com/v1/forecast?latitude=12.9716&longitude=77.5946&current=temperature_2m,relative_humidity_2m,apparent_temperature,is_day,precipitation,weather_code,wind_speed_10m&timezone=auto`

Open-Meteo provides free access without an API key for non-commercial use. Follow the provider's current terms if using the API beyond this assessment.

### Required features

1. Allow the user to search for a city by name.
2. Fetch matching locations using the geocoding API.
3. Allow the user to select a location from the search results.
4. Fetch current weather using the selected location's latitude and longitude.
5. Display the city name, temperature, feels-like temperature, humidity, wind speed, and a readable weather condition.
6. Include a refresh action to fetch the latest weather data.
7. Display loading and error states, with a retry action.
8. Handle invalid city names and empty search results gracefully.

### Weather condition labels

Use the API's `weather_code` field to display a readable condition. You may map the WMO weather codes to labels using the Open-Meteo documentation. Do not display the numeric code as the only description.

### Optional bonus

- Display whether it is day or night.
- Show precipitation.
- Save the last searched city locally.
- Add a small forecast section.

---

## Technical expectations (all options)

1. **API integration:** Use HTTP requests correctly and parse the response safely.
2. **Models:** Create Dart model classes for API data instead of relying on unstructured maps throughout the UI.
3. **Separation of concerns:** Keep network/API logic separate from presentation widgets.
4. **Asynchronous states:** Handle loading, success, empty, and error states appropriately.
5. **User experience:** Show useful error messages and provide retry/refresh where specified.
6. **Code quality:** Use clear names, small focused widgets/functions, and null-safe Dart.
7. **State management:** Choose an approach you can explain. `setState`, Provider, Riverpod, Bloc/Cubit, or another reasonable option is acceptable.
8. **Testing:** Add at least one meaningful test, such as model JSON parsing or a test for a piece of business logic.
9. **No hardcoded response data:** The main content must come from the API. Static labels and UI placeholders are fine.
10. **No secrets:** Do not commit API keys or credentials. The listed endpoints do not require keys for the specified use.

## Submission requirements

Please submit:

- Source code in a Git repository.
- A `README.md` with setup/run instructions and the app option you chose.
- A short screen recording or screenshots showing the main flow.
- A brief note explaining your API approach, state management choice, and any known limitations.

Be ready to explain your code and make one small change during review.

## Evaluation criteria

The reviewer will assess:

- Correct API integration and JSON parsing.
- Appropriate loading, success, empty, and error states.
- Code organization and separation of API logic from UI.
- Flutter layout, navigation, and usability.
- Search/filter behavior where required.
- Testing and edge-case handling.
- Ability to explain the implementation.

**Important:** You are expected to understand the code you submit. External references and AI-assisted tools may be used, but you should be able to explain the implementation and make changes independently.

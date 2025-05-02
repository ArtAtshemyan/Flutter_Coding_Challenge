# Flutter_Coding_Challenge
Flutter Coding Challenge
Flutter Coding Challenge: Product List App Using BLoC
Overview
Objective:
Build a Flutter mobile application that displays a list of products loaded from a local JSON file and utilizes the BLoC pattern for handling asynchronous data and state changes. When a user taps a product, the app should navigate to a detail screen that shows more information about the selected product.

Time Allowed:
Approximately 1 hour

Task Details
1. Project Setup
Local JSON File:
Create a local JSON file (e.g., assets/products.json) that contains an array of products with properties like id, name, description, price, and image URL.
Example JSON structure:
Add the JSON file to your assets and update the pubspec.yaml accordingly.
Dependency Management:
Include the flutter_bloc package in your pubspec.yaml for state management.
2. Implement BLoC for Data Handling
Creating BLoC Components:
Events:
Create an event class (e.g., ProductEvent) that defines events such as LoadProducts.
States:
Define states like ProductInitial, ProductsLoading, ProductsLoaded, and ProductsError to represent various data loading states.
ProductBloc:
Create a ProductBloc class that extends Bloc<ProductEvent, ProductState>.
On the LoadProducts event, asynchronously read and parse the local JSON file.
On a successful load, emit a ProductsLoaded state with the list of products; on failure, emit a ProductsError state.
3. Main Screen: Product List
UI Implementation using BLoC:
Wrap your main screen in a BlocProvider that provides an instance of ProductBloc.
In the widget tree, dispatch the LoadProducts event once the screen is built.
Use BlocBuilder<ProductBloc, ProductState> to update the UI based on the state:
ProductsLoading: Display a loading indicator.
ProductsLoaded: Display a ListView showing each product’s image, name, and price.
ProductsError: Display an error message.
Interaction:
Each list item should be tappable to navigate to the product detail screen.
Consider separating the list item into its own widget for modularity.
4. Detail Screen: Product Information
Navigation:
Use Flutter’s navigation (e.g., Navigator.push) to route from the list screen to the detail screen.
Display Details:
The detail screen should show the selected product’s image, name, detailed description, and price.
Use standard Flutter widgets like Image, Text, and layout widgets such as Column and Padding to create a clean design.
5. Optional Bonus
Search Functionality (Bonus):
Add a search bar on the main screen that allows filtering the product list based on product names.
You may handle the search filtering within the BLoC by dispatching a new event (e.g., FilterProducts) and updating the state accordingly.
Error Handling Improvements:
Enhance error handling in the BLoC or within your widgets to manage any issues with JSON parsing or asset loading.
Evaluation Criteria
When reviewing the candidate's submission, consider the following aspects:

State Management Using BLoC:
Proper implementation and separation of events, states, and the BLoC itself.
Effective use of BlocProvider, BlocBuilder, and dispatching events.
Code Structure and Quality:
Logical file and folder organization.
Clear separation of concerns (e.g., splitting UI into widgets, business logic in the BLoC, and models for the product data).
Adequate comments and documentation where necessary.
UI/UX:
A clean and responsive user interface.
Intuitive navigation between the product list and detail screens.
Data Handling:
Accurate loading, parsing, and error handling for the local JSON data.
Bonus Implementation (if applicable):
Smooth and functional search filtering.
Additional improvements in error handling.
Deliverables
Source Code:
Provide the complete source code of the Flutter application.
README File:
Include a brief README that explains:
How to run the project.
Any assumptions made or additional features implemented.
A summary of design decisions, particularly regarding the use of BLoC for state management.
[
  {
    "id": 1,
    "name": "Apple iPhone 13",
    "description": "Latest iPhone with advanced features",
    "price": 999.99,
    "image_url": "https://via.placeholder.com/150"
  },
  {
    "id": 2,
    "name": "Samsung Galaxy S21",
    "description": "Newest Galaxy model with innovative design",
    "price": 899.99,
    "image_url": "https://via.placeholder.com/150"
  }
]


## Quote Generator

This is a simple Quote Generator web application that retrieves and displays quotes based on a selected category. The project utilizes the API Ninjas Quotes API to fetch quotes. Users can select a category (e.g., love, friendship, motivation) to receive a relevant quote.

# Table of Contents
Features
Project Structure
Setup
API Integration
Usage
License

# Features
Select from various quote categories such as love, motivation, success, etc.
Fetches quotes in real-time using AJAX requests.
Displays the quote along with the author’s name.


# Project Structure

├── index.html        # Main HTML file with UI layout and quote display
├── style.css         # Optional CSS for styling
├── script.js         # JavaScript file for handling API requests
└── README.md         # Project documentation


# Setup
1. Clone the repository:
git clone https://github.com/your-username/quote-generator.git
cd quote-generator

2. Open index.html in your browser to run the application locally.

3. Replace the API Key:

4. This project includes a sample API key for demonstration purposes. Replace the key in script.js if using your own.
You can obtain an API key from API Ninjas.


# API Integration
The application makes use of API Ninjas Quotes API to fetch quotes for different categories.

# API Endpoint
URL: https://api.api-ninjas.com/v1/quotes?category={category}
Method: GET
Headers: Add your API key in the header as X-Api-Key.

# Example API Request
The following example fetches quotes based on the selected category:

# javascript

const API = "https://api.api-ninjas.com/v1/quotes?category=";
const key = "YOUR_API_KEY";  // Replace with your API key
const apiUrl = `${API}${category}`; // Append the selected category

$.ajax({
    type: "GET",
    url: apiUrl,
    headers: { 'X-Api-Key': key },
    contentType: 'application/json',
    success: function(data) {
        if (data && data.length > 0) {
            document.querySelector('#quote').innerHTML = `<h1>${data[0].quote}</h1>`;
            document.querySelector('#author').innerHTML = `<cite>~${data[0].author}</cite>`;
        } else {
            document.querySelector('#quote').innerHTML = `<h1>No quotes found for this category.</h1>`;
        }
    },
    error: function(jqXHR) {
        console.error('Error: ', jqXHR.responseText);
    }
});

# Usage
Open the HTML file in a browser.
Select a category from the dropdown.
Click on Get Quote to display a new quote.

# License
This project is licensed under the MIT License.

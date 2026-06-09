 Currency Converter Web App

A sleek, responsive, and real-time Currency Converter web application built using HTML5, CSS3, and modern JavaScript (ES6+). This application allows users to instantly convert values between different global currencies with up-to-date exchange rates.

## 🚀 Live Demo
*(Optional: Add your GitHub Pages link here)*
`https://yourusername.github.io/your-repository-name/`

## ✨ Features
* **Real-Time Conversion:** Fetches live, accurate exchange rates using a reliable public API.
* **Dynamic Flag Updates:** Automatically updates country flags when a new currency is selected via the [FlagsAPI](https://flagsapi.com/).
* **Smart Input Validation:** Automatically handles empty or invalid currency amounts by defaulting gracefully to `1`.
* **Robust Error Handling:** Features a `try...catch` block network architecture to ensure the UI never freezes during connection drops.

## 🛠️ Tech Stack
* **Frontend:** HTML5, CSS3
* **Scripting:** JavaScript (Async/Await Fetch API, DOM Manipulation)
* **API Dependencies:** * [Currency API](https://github.com/fawazahmed0/currency-api) (Latest Endpoint Structure)
  * [FlagsAPI](https://flagsapi.com/) for flat flag icons

## 🔧 API Reference & Migration Note
This project has been fully updated to support the new schema requirements of the Currency API. 

* **Deprecated Path:** `https://cdn.jsdelivr.net/gh/fawazahmed0/currency-api@1/...` (No longer operational)
* **Current Active Path:** `https://latest.currency-api.pages.dev/v1/currencies/{fromCurrency}.json`

The app fetches data optimized by the base currency file and parses the target conversion nested structure cleanly:
```javascript
const URL = `${BASE_URL}/${fromCode}.json`;
let response = await fetch(URL);
let data = await response.json();
let rate = data[fromCode][toCode];

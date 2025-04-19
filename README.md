REG.NO:212223220103
## AIM:
Build a Weather App using React
## Objective:
Create a simple weather application using React that allows the user to enter a city name and view simulated weather data such as temperature, wind speed, and sky condition.
## Task Description:
Develop a weather app that:

1.Accepts a city name from the user

2.Displays weather information (temperature, wind speed, sky condition) only for predefined cities

3.Shows an error message for cities not in the mock data
## Requirements:
React functional component (WeatherApp)

Text input to enter city name

A button or "Enter" key to trigger search

Display of weather data (if city is valid)

Error message for invalid cities

Basic styling using external or inline CSS
## Program:
App.js
```
import React from 'react';
import WeatherApp from './WeatherApp';

function App() {
  return <WeatherApp />;
}

export default App;

```
weatherApp.jsx
```
import React, { useState } from 'react';
import './WeatherApp.css';

const mockWeatherData = {
  'New York': {
    temperature: '20°C',
    wind: '12 km/h',
    sky: 'Cloudy',
  },
  'London': {
    temperature: '15°C',
    wind: '10 km/h',
    sky: 'Rainy',
  },
  'Tokyo': {
    temperature: '25°C',
    wind: '8 km/h',
    sky: 'Sunny',
  },
  'Delhi': {
    temperature: '30°C',
    wind: '5 km/h',
    sky: 'Hazy',
  },
};

function WeatherApp() {
  const [city, setCity] = useState('');
  const [weather, setWeather] = useState(null);
  const [error, setError] = useState('');

  const handleSearch = () => {
    const cityTrimmed = city.trim();
    if (mockWeatherData[cityTrimmed]) {
      setWeather(mockWeatherData[cityTrimmed]);
      setError('');
    } else {
      setWeather(null);
      setError('City not found. Please try another one.');
    }
  };

  const handleKeyPress = (e) => {
    if (e.key === 'Enter') {
      handleSearch();
    }
  };

  return (
    <div className="weather-container">
      <h2>Weather App</h2>
      <input
        type="text"
        placeholder="Enter city name"
        value={city}
        onChange={(e) => setCity(e.target.value)}
        onKeyPress={handleKeyPress}
      />
      <button onClick={handleSearch}>Search</button>

      {weather && (
        <div className="weather-info">
          <p><strong>Temperature:</strong> {weather.temperature}</p>
          <p><strong>Wind:</strong> {weather.wind}</p>
          <p><strong>Sky:</strong> {weather.sky}</p>
        </div>
      )}

      {error && <p className="error">{error}</p>}
    </div>
  );
}

export default WeatherApp;

```
weatherApp.css
```
/* General container */
.weather-container {
    max-width: 400px;
    margin: 60px auto;
    padding: 30px 25px;
    border-radius: 20px;
    background: linear-gradient(145deg, #e0f7fa, #ffffff);
    box-shadow: 10px 10px 25px #b2dfdb, -10px -10px 25px #ffffff;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    text-align: center;
    transition: all 0.3s ease-in-out;
  }
  
  /* Header */
  .weather-container h2 {
    font-size: 28px;
    margin-bottom: 20px;
    color: #00796b;
  }
  
  /* Input field */
  input {
    padding: 12px;
    width: 80%;
    font-size: 16px;
    margin-bottom: 12px;
    border: 2px solid #b2dfdb;
    border-radius: 10px;
    outline: none;
    transition: 0.2s ease-in-out;
  }
  
  input:focus {
    border-color: #00796b;
    box-shadow: 0 0 5px #00796b44;
  }
  
  /* Search button */
  button {
    padding: 10px 20px;
    background-color: #00796b;
    color: white;
    border: none;
    border-radius: 10px;
    font-weight: bold;
    cursor: pointer;
    transition: 0.2s ease;
    margin-left: 5px;
  }
  
  button:hover {
    background-color: #004d40;
  }
  
  /* Weather info */
  .weather-info {
    margin-top: 25px;
    text-align: left;
    padding: 15px;
    border-radius: 12px;
    background-color: #ffffffcc;
    box-shadow: 0px 4px 10px #c8e6c9;
  }
  
  .weather-info p {
    font-size: 16px;
    margin: 8px 0;
    color: #333;
  }
  
  /* Error message */
  .error {
    color: #d32f2f;
    margin-top: 15px;
    font-weight: bold;
  }
  
```
## Output:

##1)Accepts a city name from the user

![image](https://github.com/user-attachments/assets/fe504396-87d8-42c1-8fb5-679bb89e5c31)

##2)Displays weather information (temperature, wind speed, sky condition) only for predefined cities

![image](https://github.com/user-attachments/assets/1fcdf945-1d2f-4de0-9d42-de9c2ab3c9bb)

##3)Shows an error message for cities not in the mock data

![image](https://github.com/user-attachments/assets/5ddf02de-2654-46c4-87e2-a67281598b70)



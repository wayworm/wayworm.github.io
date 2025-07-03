
<%*
const response = await fetch("https://api.open-meteo.com/v1/forecast?latitude=51.4415&longitude=0.1495&current_weather=true&daily=temperature_2m_max&timezone=auto");
const data = await response.json();

const currentTemp = data.current_weather.temperature;
const maxTemp = data.daily.temperature_2m_max[0];

tR += `Current: ${currentTemp}°C | Max today: ${maxTemp}°C`;
%>

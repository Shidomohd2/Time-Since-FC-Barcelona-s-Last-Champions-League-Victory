# FC Barcelona Timer Web App

This web application displays the time since FC Barcelona's last UEFA Champions League victory, down to the second. 
The app dynamically updates the counter, providing a visually appealing and interactive experience.

## Features

- **Dynamic Counter**: Displays years, months, days, hours, minutes, and seconds since June 6, 2015.
- **Digital Timer Format**: Shows the elapsed time in a clear digital format (e.g., `00:00:00:00:00:00`).
- **Responsive Design**: Looks great on both desktop and mobile devices.
- **Thematic Styling**: Uses FC Barcelona's iconic colors.
- **Social Media Links**: Connect with the creator on Telegram, Instagram, and X (formerly Twitter).

## How It Works

### HTML Structure

The app's structure is divided into three main sections:

1. **Logos Section**: Displays FC Barcelona's crest.
2. **Digital Counter**: A visually appealing digital timer.
3. **Footer**: Contains social media links and attribution.

### CSS Styling

- **Gradient Background**: Incorporates FC Barcelona's primary colors with a gradient effect.
- **Shadow Effects**: Adds depth and makes elements stand out.
- **Responsive Design**: Adjusts fonts and element sizes for smaller screens.

### JavaScript Functionality

- **Victory Date**: Set as `June 6, 2015` (Barcelona's last Champions League victory).
- **Dynamic Updates**: The timer recalculates every second using the `setInterval()` method.
- **Digital Timer Conversion**: Converts the elapsed time into a digital clock format.

## Code Snippets

### HTML
```html
<div class="digital-counter" id="digital-counter">
    00:00:00:00:00:00
</div>
```

### JavaScript
```javascript
function updateCounters() {
    const now = new Date();
    const diff = now - victoryDate;

    const years = Math.floor(diff / (1000 * 60 * 60 * 24 * 365));
    const months = Math.floor(diff / (1000 * 60 * 60 * 24 * 30));
    const days = Math.floor(diff / (1000 * 60 * 60 * 24));
    const hours = Math.floor(diff / (1000 * 60 * 60));
    const minutes = Math.floor(diff / (1000 * 60));
    const seconds = Math.floor(diff / 1000);

    document.getElementById('years').textContent = years;
    document.getElementById('months').textContent = months;
    document.getElementById('days').textContent = days;
    document.getElementById('hours').textContent = hours;
    document.getElementById('minutes').textContent = minutes;
    document.getElementById('seconds').textContent = seconds.toString().padStart(2, '0');

    const digitalYears = years.toString().padStart(2, '0');
    const digitalMonths = (months % 12).toString().padStart(2, '0');
    const digitalDays = (days % 30).toString().padStart(2, '0');
    const digitalHours = (hours % 24).toString().padStart(2, '0');
    const digitalMinutes = (minutes % 60).toString().padStart(2, '0');
    const digitalSeconds = (seconds % 60).toString().padStart(2, '0');
    document.getElementById('digital-counter').textContent = `${digitalYears}:${digitalMonths}:${digitalDays}:${digitalHours}:${digitalMinutes}:${digitalSeconds}`;
}

setInterval(updateCounters, 1000);
```

### CSS
```css
body {
    font-family: 'Roboto', sans-serif;
    background: linear-gradient(135deg, #004B87, #A50044);
    color: #ffffff;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    text-align: center;
}

.digital-counter {
    font-size: 2.5rem;
    margin: 20px 0;
    font-weight: bold;
    color: #FFD700;
    letter-spacing: 5px;
    background: #000000;
    padding: 10px 15px;
    border-radius: 5px;
    box-shadow: 0 0 10px #FFD700;
}
```

## Deployment

1. Clone or download the repository.
2. Open `index.html` in any modern browser.
3. No additional dependencies or servers are required.

## Future Enhancements

- Add animations to the timer.
- Provide additional historical details about FC Barcelona.
- Include a countdown for upcoming matches or events.

## Credits

- Created by: **Shi_d30**
- Social Media: [Telegram](https://telegram.me/shi_d30), [Instagram](https://instagram.com/shi_d30), [X](https://x.com/shi_d30).
- Icons sourced from [Wikipedia Commons](https://commons.wikimedia.org/).

## License

This project is licensed under the [MIT License](LICENSE).

# Travel Buddy✈️

## Overview
The Travel Tours App is a React-based application that dynamically displays a list of travel destinations. Users can explore available tours, remove tours they are not interested in, and refresh the list to restore all tours. This app demonstrates state management, component-based architecture, and interactivity using React.

---

## Features
- **Dynamic Tour Management**: Users can remove tours from the list.
- **Refresh Functionality**: When all tours are removed, a refresh button allows users to reset the list.
- **Reusable Components**: Modular design with a dedicated `Tours` component.
- **State Management**: Uses React's `useState` hook to manage the list of tours.
- **User-Friendly Interface**: Clean and responsive design for seamless interaction.

---

## Usage
### Adding a New Tour
To add a new tour, update the `data.js` file by appending a new object to the `data` array:
```javascript
{
  id: 8,
  name: "New Destination",
  info: "Description of the destination.",
  image: "URL_to_image",
  price: "Price_value",
}
```

### Removing a Tour
Click the remove button on any tour to remove it from the list. The list updates dynamically.

### Refreshing Tours
When all tours are removed, a "Refresh" button will appear. Click it to restore the original list of tours.

---

## Code Highlights
### State Management
The `App` component uses the `useState` hook to manage the list of tours:
```javascript
const [tours, setTours] = useState(data);
```

### Remove Tour Functionality
A function to filter out a specific tour based on its `id`:
```javascript
function removeTour(id) {
  const newTours = tours.filter(tour => tour.id !== id);
  setTours(newTours);
}
```

### Conditional Rendering
Displays a refresh button when the tours list is empty:
```javascript
if (tours.length === 0) {
  return (
    <div className="refresh">
      <h2>No Tours Left</h2>
      <button className="btn-white" onClick={() => setTours(data)}>
        Refresh
      </button>
    </div>
  );
}
```

---
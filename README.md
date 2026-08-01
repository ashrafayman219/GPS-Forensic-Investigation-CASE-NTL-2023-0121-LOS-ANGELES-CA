# GPS Forensic Investigation Map

Interactive web-based GPS data visualization tool for forensic investigation and analysis.

## Overview

This system provides a comprehensive, interactive map interface for analyzing GPS tracking data from forensic investigations. Built with modern web technologies, it offers powerful visualization and analysis tools to help investigators understand movement patterns, timelines, and critical events.

## Key Features

### 📍 **Interactive Map Visualization**
- **Smart Color-Coded Points**: GPS points are color-coded based on temporal proximity to the incident
  - Purple: Within ±2 minutes of incident
  - Green: 0-30 minutes before incident
  - Red/Orange: 0-30 minutes after incident
  - Grey: All other recorded points
- **Dynamic Route Display**: Shows route lines (green for before incident, red for after)
- **Incident Location Marker**: Gold marker highlighting the critical incident location
- **Satellite/Street View Toggle**: Switch between map views
- **Zoom Controls**: Custom zoom in/out and reset view buttons

### ⏱️ **Timeline & Playback**
- **Timeline Animation**: Play through GPS points sequentially with progressive route drawing
- **Speed Controls**: Adjust playback speed (0.5x, 1x, 2x, 4x)
- **Time Filtering**: Filter data points by custom time ranges
- **Interactive Slider**: Scrub through timeline manually
- **Mode Indicators**: Clear visual indication of Timeline vs Fly Tour mode

### ✈️ **Advanced Fly Tour**
- **Google Earth-Style Tour**: Cinematic fly-through of GPS points at street level
- **Smart Navigation**: Automatically adjusts between smooth panning and flying based on distance
- **Pause at Points**: 2-second pause at each location, 5-second pause at incident
- **Progressive Route**: Blue line draws progressively during tour

### 📊 **Data Analysis Panel**
Three-tab interface with comprehensive information:

#### **Overview Tab**
- Case information and statistics
- Total distance traveled
- Average speed
- Points before/after incident breakdown
- Color-coded legend with explanations

#### **Gaps Tab**
- Identifies GPS data gaps (>20 minutes between points)
- Clickable gaps to zoom to location
- Duration and time information for each gap

#### **All Points Tab**
- Complete list of all 148 GPS points
- Real-time search functionality (by point #, time, or coordinates)
- Click any point to zoom to location
- Detailed time and coordinate information

### 📤 **Export & Reporting**
- **CSV Export**: Comprehensive forensic report including:
  - Analysis description and methodology
  - Case information and timeline
  - Detailed statistics by time category
  - Complete point-by-point data with all attributes
  - Key findings summary
  - Legend and metadata
- **Map Capture**: Export current map view as PNG image

### 🎨 **Professional UI/UX**
- **Modern Loading Screen**: Animated GPS location icon with orbiting dots
- **Modal Selection**: Choose between "Explore the Map" or "Start Fly Tour"
- **Floating Controls**: Organized timeline controls at bottom, map tools on right
- **Clear/Reset Options**: 
  - Clear Route: Remove route lines
  - Clear Points: Remove GPS markers
  - Clear All: Reset everything
- **Responsive Design**: Works on various screen sizes
- **Smooth Animations**: Professional transitions and effects

### 🛠️ **Map Tools**
Right-side floating toolbar with:
- Zoom In/Out controls
- Reset View (home button)
- Toggle Satellite/Street view
- Export forensic report (CSV)
- Capture map screenshot
- Toggle heatmap visualization
- Clear route lines
- Clear GPS points

## Technical Specifications

### Technologies Used
- **Leaflet.js**: Interactive mapping library
- **Leaflet MarkerCluster**: Marker clustering for performance
- **Leaflet.heat**: Heatmap visualization
- **HTML2Canvas**: Map screenshot functionality
- **GeoJSON**: GPS data format
- **Pure CSS3**: Modern animations and styling

### Data Format
- Input: GeoJSON format with feature collection
- Point attributes include:
  - Sequence number
  - UTC and local timestamps
  - Unix timestamp
  - Coordinates (latitude, longitude, altitude)
  - Minutes to incident
  - Time display format

### Browser Compatibility
- Chrome (recommended)
- Firefox
- Safari
- Edge
- Modern mobile browsers

## File Structure

```
Locations/
├── index.html                      # Main application file
├── gps_investigation_map.html      # Alternative entry point
├── Locations.geojson               # GPS data (148 points)
├── Locations.kml                   # KML format data
├── Locations_LineString.geojson    # Route line data
├── README.md                       # This file
└── loading_options.html            # Loading animation preview
```

## Usage Instructions

### Getting Started
1. Open `index.html` or `gps_investigation_map.html` in a web browser
2. Wait for the loading screen (3 seconds)
3. Choose your exploration mode:
   - **Explore the Map**: Start with full route visible
   - **Start Fly Tour**: Begin cinematic fly-through

### Timeline Controls
- **Play (▶)**: Start timeline animation with auto-zoom to full extent
- **Pause (⏸)**: Stop any active animation
- **Reset (⟲)**: Return to start of timeline
- **Fly Tour (✈)**: Toggle Google Earth-style tour mode
- **Incident (!!)**: Jump directly to incident location
- **Show All (👁)**: Display complete route
- **Clear All (🗑)**: Remove all elements from map

### Navigation Tips
- Click any GPS point to see detailed information
- Use the slider to manually navigate through time
- Search for specific points in the "All Points" tab
- Click gaps in the "Gaps" tab to investigate data interruptions
- Use time filters to focus on specific time periods

### Exporting Data
1. Click the **Export Report** button (document icon) in map tools
2. CSV file downloads automatically with:
   - Case summary and analysis
   - Complete point-by-point data
   - Statistics and key findings
   - Professional forensic formatting

## Color Legend

| Color | Meaning | Description |
|-------|---------|-------------|
| 🟡 Gold | Incident Location | The exact incident point at 16:27 |
| 🟣 Purple | Within ±2 min | Critical timeframe around incident |
| 🟢 Green | 0-30 min before | Immediate pre-incident context |
| 🔴 Red/Orange | 0-30 min after | Immediate post-incident context |
| ⚪ Grey | Other points | Broader movement context |

## Performance Notes

- Handles 148 GPS points efficiently
- Smooth animations at all speed settings
- Optimized rendering for all devices
- No lag during timeline playback or fly tour

## Future Enhancements (Potential)

- Multi-day data support
- GPX file import
- Real-time data streaming
- Additional map providers
- 3D terrain visualization
- Comparison mode for multiple tracks
- Advanced filtering options

## Support & Maintenance

For issues or questions, refer to the inline code comments or contact the developer.

## Version

Current Version: 1.0.0  
Last Updated: January 2026

---

**Note**: This system is designed for forensic investigation purposes and should be used in accordance with applicable laws and regulations regarding GPS data analysis and privacy.

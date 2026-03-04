# mapqx
MAPQX - Turf, Roofing, Solar and Fencing Quote Calculator

# MAPQX Calculator

MAPQX Calculator is a WordPress plugin that provides a map-based measurement and quote experience for service businesses. Visitors draw polygons/lines on an interactive map to measure area or length, apply tab-specific settings (pitch, gates, etc.), and generate an estimate with an optional quote request submission.

## Features

- Unified multi-tab calculator
  - Turf (polygon area)
  - Roofing (polygon footprint + pitch multiplier)
  - Solar (polygon + PVWatts-based production estimate, if enabled)
  - Length (polyline distance)
  - Fence (polyline segments + gates with admin-configurable pricing)

- Consistent sidebar UI
  - Map on the left, compact sidebar on the right
  - Live measurement stat + controls + calculate + results + quote form

- Roofing pitch workflow (industry-standard)
  - Draw roof footprint polygon
  - Select roof pitch (x:12)
  - Computes roof surface area using:
    - Actual Area = Footprint Area × √(1 + (pitch/12)²)

- Fence gates
  - Gate staging and placement workflow
  - Separate gate cost totals
  - Gate prices managed in plugin settings

## Installation

1. Upload the plugin folder to:
   - wp-content/plugins/mapqx-calculator/
2. Activate MAPQX Calculator in Plugins → Installed Plugins
3. Configure settings (API keys and pricing) in the plugin settings page
4. Add the plugin shortcode/block to a page 

## Requirements

- WordPress (modern version recommended)
- Google Maps JavaScript API access (if your build uses Google Maps)
- Optional: PVWatts access/configuration for Solar tab (if enabled in your build)

## Usage (Visitor Flow)

1. Open the calculator page
2. Choose a tab (Turf / Roofing / Solar / Length / Fence)
3. Draw a polygon or line on the map
4. Adjust tab options (e.g., roof pitch, gate selection)
5. Click Calculate to generate results
6. Optionally submit a quote request

## Notes

- Roofing does not use elevation lines. Google Elevation returns ground elevation, not roof height; pitch-based multipliers provide a more reliable estimating workflow.
- For complex roofs with multiple pitches, draw separate polygons per roof section (or use a dominant pitch for estimating).

## License

“All rights reserved.”

## [v5.0.0] - Major merge + unified UI (Latest)

### Added
- Unified sidebar layout across all tabs (map left, sidebar right with consistent controls/results/quote flow)
- Full multi-tab suite:
  - Turf (polygon area)
  - Roofing (polygon footprint + pitch multiplier)
  - Solar (polygon + PVWatts, if enabled)
  - Length (polyline distance)
  - Fence (line segments + gates)

### Changed
- Roofing workflow rebuilt:
  - Removed elevation-line approach
  - Added pitch-based roof surface area calculation:
    - Actual Area = Footprint Area × √(1 + (pitch/12)²)
  - Live display of footprint area, pitch multiplier, and roof surface area in the sidebar

### Fence
- Integrated fence line drawing with gate staging/placement
- Gate pricing pulled from admin settings
- Gate costs shown separately in results

### Fixed
- AJAX hook typo for non-logged-in users:
  - Corrected wp_ajax_nopriv_... naming so quotes work for visitors

CHANGELOG.md

# Changelog

All notable changes to MAPQX Calculator are documented here.

## [v5.0.0] - Major merge + unified UI 

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

---

## [v3.0.0] - Stabilization + restructure checkpoint

### Added
- Refactoring groundwork to support merging multiple calculator modules
- More consistent tab logic and shared UI behavior across calculators

### Changed
- Internal structure cleaned up to reduce one-off tab behaviors and prepare for a unified layout

### Fixed
- General edge-case reliability improvements (measurement display and tab flow consistency)

---

## [v2.3.1] - Legacy baseline

### Known issues / limitations
- Roofing relied on elevation-line logic (Elevation API ground elevation ≠ roof height)
- Inconsistent UI patterns across tabs/modules
- Logged-out visitor quote submission could fail due to wp_ajax_nopriv hook typo

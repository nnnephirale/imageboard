# Social Grid Visualizer - Development Log

## Version History

### V1.5 - Has Memory Now (Previous)
- Added localStorage persistence for grid state
- Images stored as base64 in localStorage
- Preview mode hides toolbar
- Limited by localStorage size constraints

### V2.0 - Enhanced Memory & Controls (2026-01-17)

### V3.0 - Lazy Loading & Layout Improvements (Current - 2026-01-18)

#### New Features

**1. Lazy Loading**
- First 8 grid cells load immediately
- Remaining cells lazy load as user scrolls down
- Uses Intersection Observer API for smooth performance
- Improves initial page load time for large grids
- Reduces memory usage

**2. MP4 Video Support**
- Drag and drop MP4 files alongside images
- Videos auto-play, loop, and are muted
- Videos respond to all scale/position controls like images
- Works in exported HTML files
- Stored in IndexedDB like images

**3. 2x2 Scale Control**
- New slider for 2x2 cell-specific scaling
- Range: 50-150% (default: 100%)
- Independent control for double-sized cells
- Located after Global Scale slider

**4. 6-Column Slider Layout**
- Toolbar now uses 6 columns instead of 3
- More compact, efficient use of screen space
- Better for wide displays

---

## V2.0 Features (2026-01-17)

**1. IndexedDB Storage**
- Replaced localStorage with IndexedDB for handling large PNG/GIF files
- No more size limitations for images
- Visual save/load indicators:
  - Green "✓ Saved" when state is saved
  - Blue "↻ Loaded from memory" on page load
  - Red "✕ Save failed" on errors

**2. Undo/Redo System**
- Command+Z / Ctrl+Z: Undo last action
- Command+Shift+Z / Ctrl+Shift+Z: Redo action
- Tracks all slider changes, image operations, and deletions
- Restores deleted images with Command+Z

**3. Enhanced Slider Controls**
- Reset button (↻) positioned next to each slider label
- Double-click slider to reset to default
- Cell height limit increased: 80px → 800px

**4. Separate Hover Scale Controls**
- **Hover Scale 1x1**: Controls hover effect for single-unit cells (0-50%, default 5%)
- **Hover Scale 2x2**: Controls hover effect for double-unit cells (0-50%, default 3%)
- Allows different hover intensities for different cell sizes
- Works in conjunction with "Scale by Size" option

#### Technical Changes
- Async/await pattern for database operations
- History stack with 50-state limit (undo/redo)
- Debounced save operations for performance (500ms delay)
- Visual feedback for all user actions

#### Keyboard Shortcuts
- **Command/Ctrl + Z**: Undo
- **Command/Ctrl + Shift + Z**: Redo
- **P**: Toggle preview mode
- **Escape**: Exit preview or deselect cell
- **Delete/Backspace**: Delete selected cell (with undo support)
- **Double-click slider**: Reset to default value

#### UI Improvements
- Reset button (↻) on every slider
- Visual save indicator (bottom-right corner)
- All state changes support undo/redo
- Image deletion can be undone

#### File Structure
```
05_SOCIALMEDIAGRID/
├── Social Grid Visualizer_V1.html (original)
├── Social Grid Visualizer V1_5_Has Memory Now_Preview is not full width anymore.html (previous)
├── Social Grid Visualizer_V2.0.html (current - 69KB)
├── Social Grid PRD.md
├── Social Grid Changelog.md
└── claude.md (this file)
```

---

## Quick Reference - What's New in V2.0

### Reset Controls
Every slider now has a **reset button (↻)** positioned next to the label:
- Columns
- Gap
- Corner Radius
- Cell Height (now goes up to 800px!)
- Grid Width
- Global Scale
- Tilt Intensity
- Shadow Intensity
- Hover Scale 1x1 (NEW!)
- Hover Scale 2x2 (NEW!)

**Two ways to reset:**
1. Click the ↻ button next to the label
2. Double-click the slider

### Undo/Redo System
All actions are now tracked:
- ✓ Slider changes
- ✓ Adding/removing images
- ✓ Deleting cells (Command+Z brings them back!)
- ✓ Resizing cells
- ✓ Swapping cell positions
- ✓ Per-cell adjustments (scale, X, Y)

**Shortcuts:**
- `Command/Ctrl + Z` = Undo
- `Command/Ctrl + Shift + Z` = Redo

### Separate Hover Scale Controls
Fine-tune how much images scale up on hover, with different settings for different cell sizes:

**Hover Scale 1x1** (single-unit cells):
- Range: 0-50%
- Default: 5%
- For smaller, single-grid cells

**Hover Scale 2x2** (double-unit cells):
- Range: 0-50%
- Default: 3%
- For larger, 2x1, 1x2, or 2x2 cells
- Typically set lower since larger cells need less emphasis

**Scale by Size** option:
- When ON: smaller images within cells get additional scale boost multiplier
- When OFF: all images use their cell-size base scale value

### Cell Height Increase
- Previous max: 400px
- New max: **800px**
- Great for tall/vertical images

### IndexedDB Persistence
- Handles large PNG/GIF files
- No more localStorage size limits
- Visual indicators show save/load status

---

## Testing Checklist - V3.0

- [ ] Open index.html in browser
- [ ] Drag and drop MP4 video files
- [ ] Verify videos auto-play and loop
- [ ] Add 10+ items and scroll to test lazy loading
- [ ] Adjust 2x2 Scale slider (50-150%)
- [ ] Verify 6-column toolbar layout
- [ ] Export to HTML and verify videos work in export
- [ ] Test all V2.0 features still work (undo/redo, persistence, etc.)

## Testing Checklist - V2.0

- [ ] Open V2.0 in browser
- [ ] Add some images
- [ ] Try Command+Z to undo
- [ ] Delete an image, then Command+Z to restore it
- [ ] Adjust Hover Scale 1x1 and 2x2 sliders (0-50%)
- [ ] Compare hover effects on 1x1 vs 2x2 cells
- [ ] Double-click a slider to reset it
- [ ] Click reset buttons (↻)
- [ ] Set Cell Height to 800px
- [ ] Refresh page - images should persist
- [ ] Watch for save indicators (bottom-right)

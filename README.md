# ImageBoard

A customizable grid visualizer for displaying images with interactive hover effects.

## Features

- **Drag & Drop**: Add images by dragging them onto cells
- **Flexible Layout**: Adjust columns, gaps, corner radius, cell heights
- **Hover Effects**: Tilt, scale, and shadow effects on hover
- **Responsive Grid**: Cells can span 1x1, 2x1, 1x2, or 2x2 spaces
- **Per-Image Controls**: Fine-tune scale, X, and Y position for each image
- **Undo/Redo**: Command+Z / Ctrl+Z to undo changes
- **Preview Mode**: Hide controls to see final result
- **Export**: Download as standalone HTML webpage
- **Mobile Responsive**: Exported grids adapt to mobile (2 columns < 1100px)

## Usage

1. Open `index.html` in your browser
2. Drag images onto the grid cells
3. Adjust layout and hover effects using the toolbar
4. Click cells to resize them (1x1, 2x1, 1x2, 2x2)
5. Select cells to fine-tune individual image positioning
6. Press "Preview" to see the final result
7. Click "Export as HTML" to download a standalone version

## Keyboard Shortcuts

- **Command/Ctrl + Z**: Undo
- **Command/Ctrl + Shift + Z**: Redo
- **P**: Toggle preview mode
- **Escape**: Exit preview or deselect cell
- **Delete/Backspace**: Delete selected cell

## Version History

### V3.0 (Current)
- Export as standalone HTML feature
- Mobile responsive (< 1100px = 2 columns)
- Export button appears in preview mode

### V2.0
- IndexedDB storage for large images
- Undo/Redo system (50-state history)
- Separate hover scale controls for 1x1 and 2x2 cells
- Reset buttons on all sliders
- Cell height increased to 800px max
- Visual save/load indicators

### V1.5
- localStorage persistence
- Preview mode
- Base64 image storage

### V1.0
- Initial grid visualizer
- Drag & drop images
- Hover effects with tilt and scale

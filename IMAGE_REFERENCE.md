# Image Reference Guide - Synthetic Asset Trading Dashboard

## 🖼️ **Asset Icons System**

### **Component Structure**
```
src/components/
├── AssetIcon.jsx          # Main icon component
└── assetsPanel.jsx        # Uses AssetIcon component
```

### **AssetIcon Component Features**
- **SVG-based icons** for better performance
- **Fallback to text** if SVG fails
- **Consistent sizing** and styling
- **Color-coded backgrounds** for each asset
- **Responsive design** with customizable size

### **Supported Assets**

| Symbol | Company | Icon | Color | SVG Path |
|--------|---------|------|-------|----------|
| `sAAPL` | Apple Inc. | Apple logo | `#A3AAAD` | Custom Apple SVG |
| `sTSLA` | Tesla, Inc. | Tesla logo | `#E82127` | Custom Tesla SVG |
| `sGOOG` | Alphabet Inc. | Google logo | `#4285F4` | Custom Google SVG |
| `sAMZN` | Amazon.com, Inc. | Amazon logo | `#FF9900` | Custom Amazon SVG |
| `sGOLD` | Gold Spot | Gold icon | `#FFD700` | Custom Gold SVG |
| `sBTC` | Bitcoin | Bitcoin symbol | `#f7931a` | Custom Bitcoin SVG |
| `sETH` | Ethereum | Ethereum symbol | `#627eea` | Custom Ethereum SVG |

### **Usage Example**
```jsx
import AssetIcon from "./components/AssetIcon.jsx";

// Basic usage
<AssetIcon symbol="sAAPL" name="Apple Inc." />

// With custom size
<AssetIcon symbol="sTSLA" name="Tesla, Inc." size={48} />

// With custom className
<AssetIcon symbol="sGOOG" name="Google" className="custom-icon" />
```

### **Component Props**
```jsx
AssetIcon.propTypes = {
  symbol: PropTypes.string.isRequired,    // Asset symbol (e.g., "sAAPL")
  name: PropTypes.string.isRequired,      // Asset name (e.g., "Apple Inc.")
  size: PropTypes.number,                 // Icon size in pixels (default: 32)
  className: PropTypes.string             // Additional CSS classes
};
```

## 🎨 **Styling System**

### **CSS Classes**
```css
.asset-icon {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
  color: white;
  font-size: 14px;
  position: relative;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(0,0,0,0.3);
}
```

### **Color Scheme**
- **Primary**: `#00c4ff` (SynthChain accent)
- **Success**: `#10b981` (Positive changes)
- **Danger**: `#ef4444` (Negative changes)
- **Muted**: `#9aa4ad` (Secondary text)

## 📁 **File Structure**
```
public/
├── selina-logo.png           # Main app logo
└── assets/                   # Asset icons directory
    └── icons/               # Individual asset icons
        ├── apple.png        # Apple logo
        ├── tesla.png        # Tesla logo
        ├── google.png       # Google logo
        ├── amazon.png       # Amazon logo
        ├── gold.png         # Gold icon
        ├── bitcoin.png      # Bitcoin logo
        └── ethereum.png     # Ethereum logo
```

## 🔧 **Implementation Details**

### **Fallback System**
1. **Primary**: SVG icons (embedded in component)
2. **Fallback**: Text-based icons (AA, TS, GO, etc.)
3. **Error Handling**: Graceful degradation

### **Performance Optimizations**
- **SVG icons** for crisp rendering at any size
- **No external image requests** for core icons
- **Lazy loading** for optional image assets
- **CSS-based styling** for consistent appearance

### **Accessibility**
- **Alt text** for all icons
- **High contrast** color schemes
- **Keyboard navigation** support
- **Screen reader** friendly

## 🚀 **Adding New Assets**

### **Step 1: Update AssetIcon.jsx**
```jsx
const assetIcons = {
  // ... existing assets
  sNEW: {
    text: "NE",
    color: "#your-color",
    svg: <YourSVGComponent />
  }
};
```

### **Step 2: Update assetsPanel.jsx**
```jsx
const assetData = [
  // ... existing assets
  { 
    symbol: "sNEW", 
    name: "New Company", 
    price: 100.00,
    change: 1.5
  }
];
```

### **Step 3: Add CSS (if needed)**
```css
.asset-icon.sNEW {
  /* Custom styling for new asset */
}
```

## 📱 **Responsive Design**
- **Mobile**: 24px icons
- **Tablet**: 32px icons  
- **Desktop**: 32px icons
- **Large screens**: 40px icons

## 🎯 **Best Practices**
1. **Use SVG** for crisp icons at any size
2. **Provide fallbacks** for reliability
3. **Maintain consistency** in color scheme
4. **Test accessibility** with screen readers
5. **Optimize performance** with minimal external requests

---

**Last Updated**: September 14, 2025
**Status**: ✅ Production Ready
**Version**: 1.0 - Image Reference System Complete

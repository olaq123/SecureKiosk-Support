# Company Branding Guide

SecureKiosk Enterprise allows you to customize the appearance of your kiosk app to match your company's brand identity. This guide explains how to use the branding features and what customization options are available.

## Prerequisites

- Active SecureKiosk Enterprise subscription
- Administrator access to the kiosk device
- Your company's branding assets (logo, colors, etc.)

## Accessing Branding Settings

1. Open SecureKiosk app
2. Go to Settings
3. Select "Company Branding"
4. If prompted, authenticate with your administrator credentials

## Available Customization Options

### 1. Company Information
- **Company Name**: Set your organization's name
- **Company Logo**: 
  - Supported formats: PNG, JPEG
  - Recommended size: 512x512 pixels
  - Maximum file size: 1MB

### 2. Theme Colors
- **Primary Color**: Used for main UI elements (navigation bar, buttons)
- **Secondary Color**: Used for accents and secondary elements
- Color can be set using:
  - RGB values
  - Hex codes
  - Built-in color picker

### 3. Typography
- **Custom Font**: Upload and use your company's font
- Supported font formats:
  - TrueType (.ttf)
  - OpenType (.otf)
- Font weight options:
  - Regular
  - Bold
  - Italic

### 4. Custom CSS
Advanced users can add custom CSS to modify the appearance of web content displayed in the kiosk. Example:

```css
/* Example custom CSS */
.header {
    background-color: #yourColor;
}
.logo {
    width: 150px;
    height: auto;
}
```

## Best Practices

1. **Logo Guidelines**
   - Use transparent PNG for best results
   - Ensure logo is clearly visible on both light and dark backgrounds
   - Maintain aspect ratio when resizing

2. **Color Selection**
   - Test colors for contrast and accessibility
   - Consider dark mode compatibility
   - Use consistent colors across all elements

3. **Font Usage**
   - Ensure fonts are licensed for commercial use
   - Test readability at different sizes
   - Include fallback system fonts

## Applying Changes

1. Make your desired customizations
2. Click "Preview" to see changes before applying
3. Click "Save Changes" to apply the new branding
4. Restart the kiosk app if prompted

## Troubleshooting

### Common Issues

1. **Logo Not Displaying**
   - Verify file format and size
   - Check image resolution
   - Ensure file is not corrupted

2. **Custom Font Not Working**
   - Confirm font file format is supported
   - Check if font is properly licensed
   - Verify file is not corrupted

3. **CSS Not Applying**
   - Validate CSS syntax
   - Check selector specificity
   - Clear app cache and restart

### Support

If you encounter any issues with branding customization:
1. Check the troubleshooting section above
2. Consult our [FAQ](FAQ.md)
3. Contact support at support@securekiosk.com

## Limitations

- Maximum of 5 custom fonts
- CSS modifications limited to web content display
- Some UI elements cannot be customized for security reasons
- Custom animations must be approved by SecureKiosk team

## Version History

| Version | Changes |
|---------|---------|
| 1.0     | Initial branding feature release |
| 1.1     | Added custom CSS support |
| 1.2     | Enhanced font management |

## Security Considerations

- All custom assets are stored securely on the device
- Branding settings are backed up with device configuration
- Custom CSS is sanitized to prevent security issues
- File integrity is verified before applying changes

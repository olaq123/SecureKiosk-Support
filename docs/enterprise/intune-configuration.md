# Microsoft Intune Configuration Guide

This guide provides detailed instructions for configuring SecureKiosk Enterprise with Microsoft Intune.

## Prerequisites

- Microsoft Intune administrator access
- iOS devices (iOS 15.0 or later)
- Devices enrolled in Intune MDM

## Configuration Steps

### 1. Add SecureKiosk to Intune

1. Sign in to the Microsoft Endpoint Manager admin center
2. Navigate to Apps > iOS/iPadOS > Add
3. Select "SecureKiosk Enterprise" from the app store
4. Configure app information:
   - Name: SecureKiosk Enterprise
   - Description: Managed kiosk solution for iOS devices
   - Publisher: Your Organization

### 2. Configure App Configuration Policy

Create a new app configuration policy with these settings:

```json
{
  "urls": {
    "allowedURLs": ["https://example1.com", "https://example2.com"],
    "defaultURL": "https://example1.com"
  },
  "branding": {
    "organizationName": "Your Organization",
    "primaryColor": "#0000FF"
  },
  "security": {
    "autoLockTimeout": 300,
    "requirePIN": true,
    "pinLength": 6
  }
}
```

Key configuration areas:
- URL Management
- Branding Settings
- Security Settings
- Device Restrictions

### 3. Deployment Configuration

1. Create assignment groups
2. Configure deployment settings
3. Set up user groups
4. Define scope tags

### 4. Security Settings

Configure these security settings:
- PIN requirements
- Auto-lock settings
- URL restrictions
- Access controls

## Testing

1. Deploy to test group
2. Verify all settings:
   - URLs are accessible
   - Branding appears correctly
   - Security settings work
3. Document any issues
4. Adjust configuration as needed

## Full Deployment

1. Create deployment schedule
2. Monitor deployment progress
3. Verify device compliance
4. Document configuration

## Troubleshooting

Common issues and solutions:

1. Configuration not applying
   - Check policy assignments
   - Verify device compliance
   - Check Intune sync status

2. App not installing
   - Verify app is properly added to Intune
   - Check deployment assignments
   - Verify device enrollment

3. URL access issues
   - Check URL format
   - Verify URL is in allowed list
   - Check device connectivity

## Best Practices

1. Use test groups before full deployment
2. Document all configurations
3. Regular policy reviews
4. Monitor device compliance
5. Keep app and policies updated

## Additional Resources

- [Setup Guide](setup-guide.md)
- [Deployment Guide](deployment.md)
- [Enterprise FAQ](faq.md)

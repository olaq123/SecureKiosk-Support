# SecureKiosk Enterprise Setup Guide

This guide provides detailed instructions for setting up and configuring SecureKiosk Enterprise in your organization.

## Prerequisites

- Microsoft Intune subscription
- iOS devices (iOS 15.0 or later)
- Enterprise deployment credentials
- Devices enrolled in Intune MDM

## Initial Setup

### 1. Intune Configuration

Before deploying SecureKiosk Enterprise, configure your Intune environment:

1. Add SecureKiosk Enterprise to Intune
2. Configure app configuration policies
3. Set up deployment groups

For detailed Intune setup instructions, see our [Intune Configuration Guide](intune-configuration.md).

### 2. App Configuration

Configure these essential settings:

- URL Management (Multiple URLs)
- Security Settings
- Branding Options
- Device Restrictions

## Deployment

### 1. Device Preparation

1. Ensure devices are enrolled in Intune
2. Verify required policies are assigned
3. Test on a pilot group before full deployment

### 2. App Distribution

Deploy SecureKiosk Enterprise through:
1. Intune Company Portal
2. Managed device deployment

## Features Configuration

### URL Management
- Add multiple allowed URLs
- Configure URL restrictions
- Group URLs for different device groups

### Custom Branding
- Add organization logo
- Set custom colors
- Configure welcome screen

### Security Settings
- Configure PIN requirements
- Set auto-lock timings
- Define access restrictions

### Remote Management
- Configure device groups
- Set up management policies
- Define access controls

## Best Practices

1. Start with a pilot deployment
2. Document your configuration
3. Train IT staff on management
4. Plan regular updates
5. Monitor device compliance

## Additional Resources

- [Intune Configuration Guide](intune-configuration.md)
- [Deployment Guide](deployment.md)
- [Enterprise FAQ](faq.md)

## Support

For enterprise support:
1. Contact your IT administrator
2. Review enterprise documentation
3. Use your organization's support channel

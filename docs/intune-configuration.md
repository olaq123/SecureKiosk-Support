# Microsoft Intune Configuration Guide for SecureKiosk

## Overview

This guide provides detailed instructions for configuring Microsoft Intune to manage SecureKiosk on iOS devices.

## Prerequisites

- Microsoft Intune administrator access
- Enterprise mobility management (EMM) subscription
- Apple APNs certificate configured in Intune
- Apple VPP token configured in Intune

## Configuration Steps

### 1. App Configuration

#### Add SecureKiosk to Intune
1. Sign in to the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/)
2. Navigate to **Apps** > **All apps** > **Add**
3. Select **iOS/iPadOS** as the app type
4. Select **Select app** and search for "SecureKiosk" in the App Store
5. Click **Select** and **Add**

#### Configure App Settings
1. Go to **Apps** > **All apps** > **SecureKiosk**
2. Select **Properties**
3. Configure the following settings:
   - Assignment type: Required
   - VPP token: Select your token
   - App configuration policies: Create new policy

### 2. App Configuration Policy

Create a new app configuration policy:

1. Navigate to **Apps** > **App configuration policies** > **Add** > **Managed devices**
2. Basic settings:
   - Name: "SecureKiosk Configuration"
   - Platform: iOS/iPadOS
   - Profile type: App configuration
   - Targeted app: SecureKiosk

3. Required Configuration Keys:

```json
{
    "intuneMAMUPN": {"type": "string", "description": "User Principal Name"},
    "managedAppConfig": {
        "autoEnrollOnLaunch": true,
        "enableDataProtection": true,
        "allowedDataBackup": false,
        "disableScreenCapture": true
    }
}
```

### 3. Compliance Policies

Configure compliance policies:

1. Go to **Devices** > **Compliance policies** > **Create Policy**
2. Select iOS/iPadOS platform
3. Configure settings:
   - Device Health
   - Device Properties
   - System Security
   - Device Security

Recommended settings:
```json
{
    "securityRequirements": {
        "deviceLockEnabled": true,
        "passcodeRequired": true,
        "passcodeMinimumLength": 6,
        "biometricEnabled": true
    },
    "encryption": {
        "deviceEncryptionEnabled": true
    }
}
```

### 4. Conditional Access

Set up conditional access policies:

1. Navigate to **Azure Active Directory** > **Security** > **Conditional Access**
2. Create new policy:
   - Name: "SecureKiosk Access Policy"
   - Users and groups: Select target groups
   - Cloud apps: SecureKiosk
   - Conditions: iOS devices
   - Grant access: Require device compliance

### 5. App Protection Policies

Configure app protection:

1. Go to **Apps** > **App protection policies**
2. Create new policy for iOS/iPadOS
3. Configure data protection settings:
   ```json
   {
       "dataProtection": {
           "preventBackups": true,
           "preventScreenCapture": true,
           "encryptAppData": true,
           "disableContactSync": true
       },
       "accessRequirements": {
           "pinRequired": true,
           "pinMinLength": 6,
           "fingerprintRequired": false
       }
   }
   ```

### 6. Device Configuration

Create device configuration profile:

1. Navigate to **Devices** > **Configuration profiles**
2. Create new profile for iOS/iPadOS
3. Configure:
   - Device restrictions
   - Device features
   - Endpoint protection

## Deployment

### Assign Policies

1. Assign app configuration policy to user groups
2. Assign compliance policy
3. Assign app protection policy
4. Deploy device configuration profile

### Verification

1. Monitor deployment status in Intune portal
2. Check device compliance reports
3. Verify app installation status
4. Test app functionality on enrolled devices

## Troubleshooting

### Common Issues

1. **App Not Installing**
   - Verify VPP token status
   - Check assignment status
   - Confirm device enrollment

2. **Configuration Not Applying**
   - Check policy assignment
   - Verify device sync
   - Review configuration conflicts

3. **Compliance Issues**
   - Check device status
   - Review compliance reports
   - Verify policy settings

## Best Practices

1. **Security**
   - Implement minimum security requirements
   - Enable encryption
   - Configure access controls

2. **Management**
   - Regular policy reviews
   - Monitor compliance
   - Update configurations as needed

3. **Deployment**
   - Test in pilot group
   - Staged rollout
   - Monitor feedback

## Support

For additional support:
- Contact Microsoft Intune support
- Review [Microsoft Intune documentation](https://docs.microsoft.com/en-us/mem/intune/)
- Submit support ticket through enterprise channel

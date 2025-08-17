# KDService - Experion Service Manager

**Professional tool for managing Honeywell Experion services for FTE Recovery**

## Overview

KDService is a Windows GUI application designed to safely manage Honeywell Experion PKS services. It provides an easy-to-use interface for enabling/disabling Experion services for Honeywell Experion Releases R500 and under where ssservices.exe -disable/enable_all does not work.

## Features

- ✅ **Safe Service Management** - Enable/disable Experion services with safety checks
- ✅ **Automatic Backup & Restore** - Preserves original service configurations including DelayedAutoStart settings
- ✅ **Service Control Panel Integration** - Direct access to Honeywell SSServices utility
- ✅ **Windows Services Access** - Quick access to Windows Services management
- ✅ **Running Service Detection** - Prevents disabling services while they're running
- ✅ **Admin Elevation** - Automatic UAC elevation for service management
- ✅ **Compact Design** - Clean, professional 520x220 window interface

## System Requirements

- Windows 7/8/10/11
- .NET Framework 4.0 or higher
- Administrator privileges (automatic elevation)
- Honeywell Experion PKS (for service management)

## Installation

1. Download `KDService.exe` from the [latest release](https://github.com/USERNAME/KDService/releases)
2. Run the executable - no installation required
3. The application will automatically request administrator privileges

## Usage

### Disabling Services
1. Click **"Disable Services"** to disable all Auto-start Experion services
2. Application automatically creates backup of current service configurations
3. Services must be stopped first using the Service Control Panel

### Enabling Services
1. Click **"Enable Services"** to restore services from backup
2. Restores original startup modes (Auto/Auto Delayed) from backup file
3. Maintains proper DelayedAutoStart registry settings

### Service Control Panel
- Click **"Honeywell Service Control Panel"** to launch SSServices.exe
- Use this to start/stop Experion services before disabling

### Windows Services
- Click **"Windows Services"** to open services.msc
- Provides direct access to Windows service management

## Safety Features

- **Running Service Protection** - Cannot disable services while they're running
- **Deployment Agent Exclusion** - Deployment agent service runs independently
- **Automatic Backups** - Creates timestamped backups in `%ProgramData%\KDService\`
- **Service State Validation** - Verifies service states before operations

## File Locations

- **Backup Directory**: `%ProgramData%\KDService\`
- **Last Backup**: `last_backup.csv` (automatic restore source)
- **Timestamped Backups**: `backup_YYYYMMDD_HHMMSS.csv`

## Version History

See [CHANGELOG.txt](CHANGELOG.txt) for detailed version history.

## Support

**Developed by ReRackIT Software**

For issues or questions:
- Check existing [Issues](https://github.com/USERNAME/KDService/issues)
- Create a new issue with detailed description
- Include Windows version and Experion PKS version

## License

Copyright (C) 2025 ReRackIT Software. All rights reserved.

This software is provided "as is" without warranty of any kind. Use at your own risk.

## Technical Details

- **Language**: C# (.NET Framework 4.0)
- **GUI Framework**: Windows Forms
- **Service Management**: WMI (Win32_Service) and Service Control Manager
- **Registry Access**: For DelayedAutoStart configuration
- **Architecture**: Single executable, no dependencies

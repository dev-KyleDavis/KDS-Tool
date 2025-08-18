# KDService - Experion Service Manager

**Professional tool for managing Honeywell Experion services with Expert Mode capabilities**

## Overview

KDService is a Windows GUI application designed to safely manage Honeywell Experion PKS services. It provides both standard safe operations and advanced Expert Mode with force capabilities for experienced administrators. Built using proven service management methodology for maximum reliability.

## Features

### Standard Mode
- **Safe Service Management** - Enable/disable Experion services with safety checks
- **Automatic Backup & Restore** - Preserves original service configurations including DelayedAutoStart settings
- **Service Control Panel Integration** - Direct access to Honeywell SSServices utility
- **Windows Services Access** - Quick access to Windows Services management
- **Running Service Detection** - Prevents disabling services while they're running
- **Admin Elevation** - Automatic UAC elevation for service management
- **Compact Design** - Clean, professional 520x220 window interface

### Expert Mode (v2.7.0+)
- **Force Operations** - Force start/stop services bypassing safety checks
- **Granular Control** - Target specific service groups individually
- **Service Groups**: ET Services, HSC Services, SQL Services, CC Services, Other Services
- **Dropdown Menus** - Advanced service group selection with dropdown arrows
- **Advanced Timeouts** - 30-second timeout with 3-retry logic per service
- **Process Termination** - Force kill processes when graceful operations fail

## System Requirements

- Windows XP/2003/2008 R2/7/8/10/11
- .NET Framework 4.0 or higher
- Administrator privileges (automatic elevation)
- Honeywell Experion PKS (for service management)

## Installation

1. Download `KDService.exe` from the [latest release](https://github.com/dev-KyleDavis/KDS-Tool/releases)
2. Run the executable - no installation required
3. The application will automatically request administrator privileges

## Usage

### Standard Operations

#### Disabling Services
1. Click **"Disable Services"** to disable all Auto-start Experion services
2. Application automatically creates backup of current service configurations
3. Services must be stopped first using the Service Control Panel

#### Enabling Services
1. Click **"Enable Services"** to restore services from backup
2. Restores original startup modes (Auto/Auto Delayed) from backup file
3. Maintains proper DelayedAutoStart registry settings

### Expert Mode Operations

#### Accessing Expert Mode
1. Click the **"E"** button in the top-right corner
2. Confirm multiple safety warnings
3. Expert Mode interface becomes available with force capabilities

#### Force Operations
- **Force Stop Services**: Click the main button to stop all service groups
- **Force Start Services**: Click the main button to start all service groups
- **Dropdown Control**: Click dropdown arrows for individual service group selection

#### Service Group Targeting
Use dropdown menus to target specific groups:
- **ET Services Only**: Experion Technology services
- **HSC Services Only**: Historical Server Collection services
- **SQL Services Only**: Microsoft SQL Server services
- **CC Services Only**: Control Core services
- **Other Services Only**: Additional Honeywell services

### Utility Functions
- **Honeywell Service Control Panel**: Launch SSServices.exe for standard operations
- **Windows Services**: Open services.msc for direct Windows service management

## Advanced Features

### Service Management Implementation
- **3-Retry Logic**: Each service operation attempts up to 3 times
- **Process Killing Fallback**: Force terminates processes when graceful stop fails
- **Service Existence Checks**: Only operates on services that actually exist
- **Registry Integration**: Direct registry updates for startup mode changes
- **Timeout Handling**: 30-second timeout per service with clear error reporting

### Safety & Reliability
- **Task Conflict Detection**: Prevents simultaneous operations
- **Button State Management**: Disables conflicting buttons during operations
- **UI Responsiveness**: Async operations with progress updates
- **Multiple Confirmations**: Expert mode requires safety acknowledgments
- **Automatic Backups**: Timestamped backups in system directories

### Technical Implementation
- **Language**: C# (.NET Framework 4.0)
- **GUI Framework**: Windows Forms with professional styling
- **Service Management**: WMI (Win32_Service) and Service Control Manager
- **Registry Access**: For DelayedAutoStart and startup mode configuration
- **Process Management**: Advanced process termination capabilities
- **Architecture**: Single executable, no external dependencies

## Safety Features

- **Running Service Protection** - Cannot disable services while they're running
- **Deployment Agent Exclusion** - Deployment agent service runs independently
- **Automatic Backups** - Creates timestamped backups in system directories
- **Service State Validation** - Verifies service states before operations
- **Expert Mode Warnings** - Multiple confirmation dialogs for force operations

## File Locations

- **Backup Directory**: `%ProgramData%\KDService\`
- **Last Backup**: `last_backup.csv` (automatic restore source)
- **Timestamped Backups**: `backup_YYYYMMDD_HHMMSS.csv`

## Expert Mode Warnings

**Expert Mode is for experienced administrators only**
- Force operations can cause data loss
- Force operations may corrupt databases  
- Force operations can leave system in unstable state
- Always backup critical data before force operations
- Use with extreme caution in production environments

## Version History

See [CHANGELOG.txt](CHANGELOG.txt) for detailed version history and recent improvements.

**Latest Version: 2.8.6**
- Enhanced button state management during operations
- Improved UI responsiveness and timeout handling
- Advanced force operations with dropdown control
- Service existence validation before operations

## Support

**Developed by ReRackIT Software**

For issues or questions:
- Check existing [Issues](https://github.com/dev-KyleDavis/KDS-Tool/issues)
- Create a new issue with detailed description
- Include Windows version and Experion PKS version
- Specify if using Standard Mode or Expert Mode

## License

Copyright (C) 2025 ReRackIT Software. All rights reserved.

This software is provided "as is" without warranty of any kind. Use at your own risk.

---

**Enterprise-ready service management** with both safe standard operations and advanced force capabilities for expert administrators.
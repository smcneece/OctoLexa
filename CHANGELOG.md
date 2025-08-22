# Changelog

All notable changes to the OctoLexa blueprint will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Home Assistant Versioning](https://developers.home-assistant.io/docs/creating_integration_manifest/#version) (YYYY.MM.V).

## [Unreleased]

## [2025.8.1] - 2025-08-22

### Added
- Initial release of OctoLexa blueprint
- Alexa notifications with configurable time restrictions
- Mobile push notifications with timestamps
- Persistent UI notifications in Home Assistant
- Automatic friendly printer name generation from sensor entity IDs
- Support for multiple notification types (toggleable)
- Queued execution mode to handle rapid state changes
- Comprehensive setup documentation

### Features
- Monitor OctoPrint printer state sensors
- Announce print start, pause, resume, and completion events
- Time-based Alexa notification restrictions (quiet hours)
- Configurable notification services for Alexa and mobile
- Automatic message formatting with timestamps
- Error state detection and notifications

### Requirements
- Home Assistant 2024.4 or newer
- OctoPrint Integration
- Alexa Media Player Integration (for Alexa notifications)
- Mobile App Integration (for mobile notifications)

---

*OctoLexa – keeping you smarter than your printer.™️*

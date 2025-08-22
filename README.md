# 🐙 OctoLexa – OctoPrint Status Notifications via Alexa, Mobile, and Persistent Alerts

[![GitHub release (latest by date)](https://img.shields.io/github/v/release/smcneece/OctoLexa)](https://github.com/smcneece/OctoLexa/releases)
[![GitHub commit activity](https://img.shields.io/github/commit-activity/y/smcneece/OctoLexa.svg)](https://github.com/smcneece/OctoLexa/commits/main)
[![GitHub](https://img.shields.io/github/license/smcneece/OctoLexa)](LICENSE)
[![Maintainer](https://img.shields.io/badge/maintainer-Shawn%20McNeece%20%40smcneece-blue.svg)](https://github.com/smcneece)

> [![Sponsor](https://img.shields.io/badge/Sponsor-💖-pink)](https://github.com/sponsors/smcneece) <-- Why not sponsor me, even a few bucks shows you appreciate the work and gives encouragement. You can sponsor me monthly, or just a one time thing. Check out my [other HA Automations & Blueprints](https://github.com/smcneece?tab=repositories) while you're here.

> ⭐ **Help Others Find This Blueprint!** If OctoLexa is working well for you, please star this repository to help other Home Assistant users discover these OctoPrint notifications!
>
> [![GitHub stars](https://img.shields.io/github/stars/smcneece/OctoLexa?style=social)](https://github.com/smcneece/OctoLexa/stargazers) [![GitHub forks](https://img.shields.io/github/forks/smcneece/OctoLexa?style=social)](https://github.com/smcneece/OctoLexa/network/members)

> 📬 **Stay Updated:** Click the "Watch" button (top-right of this repo) → "Releases only" to get email notifications when new versions are released!

> ⚠️ **CAUTION:** Recent update to HA/OctoPrint integration doesn't allow renaming entities properly anymore. See: https://github.com/home-assistant/core/issues/146805 - It can be done manually, but that's a pain!

---

## 📋 Overview

**OctoLexa** sends real-time print status notifications from your OctoPrint-connected 3D printers to Alexa, your mobile devices, and Home Assistant's UI. Stay informed when a print **starts**, **pauses**, **resumes**, or **finishes** — no more guessing if your print is done.

Designed to be lightweight, fast, and easy to configure.

---

## 🚀 Features

- 🗣️ Alexa announces important printer events (optional)
- 📱 Mobile push notifications with timestamps (optional)
- 🖥️ Persistent UI notifications with timestamps (optional)
- 🛠️ Automatically generates a friendly printer name from your sensor entity
- 🧩 Modular: Use it with any number of printers — create a new automation for each one
- 🛡️ Single Alexa entity required — create groups easily if needed

---

## ⚙️ Requirements

- Home Assistant 2024.4 or newer
- [OctoPrint Integration](https://www.home-assistant.io/integrations/octoprint/)
- [Alexa Media Player Integration](https://github.com/custom-components/alexa_media_player) (for Alexa notifications)
- A printer state sensor (example: `sensor.chiron_right_current_state`)

---

## 🛠️ Installing OctoLexa Blueprint

1. **Import the Blueprint:**  
   [![Import Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://raw.githubusercontent.com/smcneece/OctoLexa/main/blueprints/automation/smcneece/octolexa.yaml)

2. Create a new automation based on the blueprint
3. Fill out the required fields:
   - **Printer State Sensor**: Select your OctoPrint state sensor (example: `sensor.chiron_right_current_state`)
   - **Alexa Notifications**: Toggle on to enable Alexa announcements
   - **Persistent Notifications**: Toggle on to enable UI messages inside Home Assistant
   - **Mobile Notifications**: Toggle on to enable push notifications
   - **Alexa Entity**: Enter your Alexa notification entity manually (text string, example: `notify.alexa_media_echoclockdot`)

---

## 🔔 Staying Updated

HACS will not automatically notify you of new blueprint updates using this install method.

To get update notifications:
- Click the **"Watch"** button (top-right of the GitHub repo)
- Select **"Releases only"** or **"All Activity"**
- Or check the [Releases](https://github.com/smcneece/OctoLexa/releases) page manually

---

## 📱 How to Find Your Notification Entities

> ⚠️ Developer Tools → Services no longer shows notify services as of recent Home Assistant updates. Here's the reliable method:

The `notify.` domain is funky and doesn't always show up in the **Entities** list. Here's the best way to find the right names:

### 📱 Mobile App Notify Entity
1. Go to **Settings → Automations & Scenes → Create Automation**
2. Click **Create a new automation**
3. Scroll down to **Then Do** and click **Add Action**
4. In the search bar, type part of your mobile device name or `mobile_app`
5. Select your device, such as `notify.mobile_app_shawn_cell`
6. Click the **three dots → Edit in YAML**
7. You'll see something like:
   ```yaml
   action: notify.mobile_app_shawn_cell
   ```
8. Copy the value after `action:` and paste it into the blueprint.

### 🗣️ Alexa Notify Entity

**Make sure [Alexa Media Player](https://github.com/custom-components/alexa_media_player) is installed and configured.**

1. Go to **Settings → Automations & Scenes → Create Automation**
2. Click **Create a new automation**
3. Scroll down to **Then Do** and click **Add Action**
4. In the search bar, type part of your Alexa device name or `alexa_media`
5. Select your device, such as `notify.alexa_media_echoclockdot`
6. Click the **three dots → Edit in YAML**
7. You'll see something like:
   ```yaml
   action: notify.alexa_media_echoclockdot
   ```
8. Copy the value after `action:` and paste it into the blueprint.

💡 *Want multiple Echos to announce together?*  
Use a group notify like `notify.alexa_media_everywhere`.

---

## 🏗️ How to Create Alexa Groups

1. Open the **Alexa app**
2. Tap **Devices**
3. Tap the **"+" icon → Combine Speakers**
4. Choose **Multi-Room Music**
5. Pick your Echo devices and name the group
6. It will appear as: `notify.alexa_media_<group_name>`

> **Note:** Alexa Groups must be created inside the Alexa app first before they appear as available notify targets.

---

## 💬 Example Notification Messages

- **Alexa**: "Print job started on Chiron Right."
- **Mobile**: "Print job started on Chiron Right @ 09:39 AM."
- **Persistent UI**: "Print job completed on Chiron Right @ 02:15 PM."

---

## 📂 Project Home

**GitHub Repo:** [https://github.com/smcneece/OctoLexa](https://github.com/smcneece/OctoLexa)

---

## 🏷️ GitHub Repo Tags
```
home-assistant, blueprint, octoprint, 3d-printing, alexa, notifications, mobile-notifications, persistent-notifications, automation, smart-home
```

---

*OctoLexa – keeping you smarter than your printer.™️*

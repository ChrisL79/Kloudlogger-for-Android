# Kloudlogger-for-Android

Android Kloudlogger client app to connect to my Kloudlogger online logbook. Works with both smartphones and tablets. It will also work with Cloudlog!

I make programs for myself if nothing exists that I exactly want. If they turn out to be half decent, I will share them with the world.

I'm not a programmer! I just program for fun and to create something I need.

# Kloudlogger Android App

A full featured amateur radio QSO logging client for Kloudlogger/Cloudlog remote servers, with integrated DX cluster connectivity, QO-100 satellite finder, Icom IC-705 Bluetooth CI-V integration, and real time server synchronisation.

## Features

### QSO Logging
- **Fast entry** — Callsign, frequency, mode, RST sent/received, and optional notes.
- **Live sync** — QSOs upload to your Kloudlogger/Cloudlog server automatically.
- **Contest mode** — Toggle to track serial numbers per contest.
- **QRZ lookup** — Fetch caller info from QRZ.com (API credentials required).
- **Frequency and mode locking** — Lock to a single frequency, mode, or both.

### Server Integration
- **Real-time sync** — Upload QSOs to the server as you log them (user configurable delay).
- **Server status** — Connection indicator with activity LEDs for ping, uplink, and downlink.
- **Public logbook** — View your shared logbook via your Kloudlogger/Cloudlog public slug.
- **Status monitoring** — See sync status and server connectivity at a glance.

### DX Cluster
- **Live spot stream** — Persistent telnet connection to public DX clusters (DX Spider, AR-Cluster, etc).
- **Band filtering** — Filter spots by any amateur radio band from 2200m through 1mm wavelength.
- **Spot posting** — Post DX spots directly to the cluster with your callsign!

### QO-100 Geostationary Satellite Finder
- **AR camera mode** — Live camera feed with augmented reality overlay.
- **Precise look angles** — Real time azimuth and elevation to QO-100.
- **Sensor fusion** — Accelerometer + magnetometer with aggressive low pass filtering for smooth tracking.
- **Compass tape** — Bearing scale across top of screen and elevation tape on right edge.
- **Sun/Moon overlay** — Displays the Sun and Moon at their current positions.
- **Off-screen indicator** — Arrow shows direction when satellite is behind you.
- **Multi-orientation** — Works in portrait and landscape and auto corrects for device rotation.

### Icom IC-705 Bluetooth CI-V Integration
- **Wireless connection** — Connects to the IC-705 over Bluetooth SPP using CI-V. No cables needed.
- **Live meter bars** — S-meter, RF power, ALC, COMP, SWR, voltage and current all update in near real time.
- **ALC reference line** — White line on the ALC bar shows the operating limit as measured from a real IC-705.
- **Peak hold** — S-meter and ALC bars hold the peak reading for easy reading.
- **PTT control** — Press and hold to transmit (momentary) or tap to latch TX on and off.
- **TUNE button** — Fires the antenna tuner directly from the app via CI-V.
- **TX indicator** — The IC-705 tile border goes red the instant you key up and clears the instant you unkey.
- **Autofill** — Frequency, mode and RST received can all autofill the log form from the radio as you tune.
- **Safety timeout** — In latching PTT mode, a configurable timeout automatically unkeys if you forget.
- **Configurable display** — Every meter row can be individually shown or hidden in settings.

### Logbook
- **Session view** — Browse all logged QSOs in the current session.
- **QSO detail** — View and edit individual log entries.
- **Daily stats** — Live count of QSOs today and average rate per hour when 2 or more QSOs are made.

## Screenshots

### Main Screen
![Main Screen](Images/Main%20Screen.jpg)

### IC-705 Integration
![Main Screen IC-705 Integration](Images/Main%20Screen%20IC-705%20Integration.jpg)

### Contest Logging
![Contest Logging](Images/Contest%20Logging.jpg)

### DX Cluster
![DX Cluster](Images/DX%20Cluster.jpg)

### QO-100 Locator
![QO-100 Locator](Images/QO-100%20Locator.jpg)

### Server Logbook
![Server Logbook](Images/Server%20Logbook.jpg)

### Session Logbook
![Session Logbook](Images/Session%20Logbook.jpg)

### Settings
![Settings Page 1](Images/Settings%20Page%201.jpg)
![Settings Page 2](Images/Settings%20Page%202.jpg)
![Settings Page 3](Images/Settings%20Page%203.jpg)

## Requirements

- **Android:** API level 24 (Android 7.0) or higher.
- **Permissions:** Internet (for connection to the remote Kloudlogger/Cloudlog server), GPS (for QO-100 satellite finder and fall back Maidenhead locator), Camera (for QO-100 AR mode), Bluetooth (for IC-705 CI-V integration).
- **Server:** Cloudlog or Kloudlogger instance (self hosted or cloud).
- **Optional:** QRZ.com account for caller lookup.
- **Optional:** Icom IC-705 for Bluetooth CI-V meter and PTT integration.

## Installation

Simple! Download and run the APK from the releases section.

## Configuration

### Server Setup (Kloudlogger/Cloudlog)

1. Open **Settings** → **Server**
2. Enter your **Hostname** (e.g., `kloudlogger.com` or `192.168.0.2` if using internal LAN only)
3. Paste your **API Key** (from your Kloudlogger/Cloudlog server's user profile)
4. Enter your **Station ID** (numeric, from your Kloudlogger/Cloudlog server setup)
5. Enter your **Public Logbook Slug** (just the slug; if your public URL is `https://kloudlogger.com/visitor/MYLOG`, enter `MYLOG`)
6. Choose **HTTP or HTTPS** — if you have signed your own certificate using NGINX for example, choose **HTTPS**. If you connect to your server only within your LAN locally, choose **HTTP**. If you operate remotely and access your server via your public IP address, select **HTTP**.
7. Tap **TEST SERVER CONNECTION** to verify

### IC-705 Bluetooth CI-V Setup

Before pairing, configure the IC-705:
- **Bluetooth:** ON
- **Bluetooth Serial Port Function:** CI-V
- **CI-V Echo Back:** OFF
- **CI-V Transceive:** ON
- **CI-V Address:** A4h (default)

Then in the app:
1. Pair the IC-705 with your Android device via Android Bluetooth Settings first
2. Open **Settings** → **IC-705 Bluetooth**
3. Toggle **Enable IC-705 Integration** on
4. Tap **Select and Connect to IC-705** and choose your radio from the paired devices list
5. The status dot on the IC-705 tile will go green when connected
6. Configure autofill, display options and PTT mode to your preference

### QRZ Setup (Optional)

1. Open **Settings** → **QRZ**
2. Enter your **QRZ.com username** and **password**
3. Tap **TEST QRZ CREDENTIALS**

### DX Cluster Setup

1. Open **Settings** → **DX Cluster**
2. Enter **Host** (default: `dxspider.co.uk`)
3. Enter **Port** (default: `7300`)
4. Enter **Cluster Login** (optional; uses your callsign if empty)
5. Enter **Password** (optional; only needed if your cluster requires it)
6. Tap **TEST CLUSTER CONNECTION** to verify

Popular open clusters:
- `dxspider.co.uk:7300` (DX Spider, callsign-only)
- `dxc.k0xm.com:7300` (DX Spider)
- `ve7cc.net:23` (VE7CC Cluster)
- `gb7djk.dxcluster.org:7300` (DX Spider)

### Your Callsign & Location

1. Open **Settings** → **Station**
2. Enter your **Callsign** (used for QRZ lookup, cluster login, and satellite finder location fallback)
3. Enter your **Maidenhead Grid** (e.g., `IO91VH`; used if GPS is unavailable or disabled)

## Usage

### Logging a QSO

1. On the main screen, fill in:
   - **Callsign** (required) — DX station you contacted
   - **Frequency (MHz)** (required) — Operating frequency
   - **Mode** (optional) — SSB, CW, FT8, etc. (locked or unlocked)
   - **RST Sent / Received** (optional) — Reception reports
   - **Notes** (optional) — Any comments
2. Tap **LOG QSO** — the entry is saved locally and queued for upload to the remote server.
3. Tap **CLR** to clear the form

### Using the IC-705 Integration

Once connected, the IC-705 tile appears at the top of the main screen:
- **Green dot** — connected and receiving data
- **Frequency display** — tracks VFO A in real time
- **Meter bars** — S-meter (RX), ALC, COMP, RF power, SWR, voltage and current all update live
- **PTT button** — green when off, solid red when transmitting. Momentary: hold to TX, release to RX. Latching: tap to TX, tap again to RX.
- **TUNE button** — triggers the antenna tuner via CI-V (map the VOX key to TUNE in the IC-705 menu first)
- **Autofill** — the log form frequency and mode fields update automatically as you tune

### Syncing to Server

- QSOs upload automatically on a schedule (default: every 30 seconds after a new entry)
- Watch the **↑ UP** LED on the server status bar — it flashes when data is being sent
- Watch the **↓ DOWN** LED — it flashes when the server responds

### Monitoring Activity

The **server status strip** shows:
- **● (dot)** — Connection state (green = connected, red = disconnected)
- **Server status text** — Current state and last message
- **● PING** — Flashes every 60 seconds when the server is pinged
- **● ↑** — Flashes when the app sends data
- **● ↓** — Flashes when the server/cluster responds

### Using the DX Cluster

1. Tap **DX Cluster** from the menu
2. Wait for the cluster to connect (watch the green dot)
3. Spots from other operators appear live as they are posted
4. Filter by band using the **All bands** dropdown
5. To post your own spot:
   - Enter the **DX Callsign**, **MHz** frequency, and optional **Comment**
   - Tap **POST SPOT TO CLUSTER**

### QO-100 Satellite Finder

1. Tap **QO-100 Finder** from the menu
2. Allow **Camera** and **Location** permissions
3. Point your phone at the sky:
   - **Green ring** = satellite is on-screen and on-target (within 5° of centre)
   - **Red ring** = satellite is on-screen but off-target
   - **Arrow off-screen** = satellite is behind you or out of frame
4. Rotate your phone to portrait or landscape — the overlay auto-corrects. It can take a few seconds to gain accuracy after doing this.

### Viewing Your Logbook

1. Tap **⋮ (menu)** → **Server Logbook** to view your shared public logbook
2. Tap **⋮ (menu)** → **Logbook** to browse all QSOs logged in this session

## Troubleshooting

### Server Connection Won't Connect

- **Check hostname:** Ensure it's reachable and doesn't include `http://` or `https://`
- **Check API key:** Copy it directly from your server's user profile, without extra spaces
- **Firewall:** If self-hosted, ensure the port is open and reachable from outside your network

### IC-705 Won't Connect

- **Bluetooth settings on the radio:** Serial Port Function must be CI-V, Echo Back OFF, CI-V Transceive ON
- **Pair first:** The IC-705 must be paired with Android via Bluetooth Settings before the app can connect
- **One connection at a time:** Disconnect any other app that may already be connected to the IC-705

### DX Cluster Spots Aren't Appearing

- **Check cluster:** Tap **Settings** → **DX Cluster** → **TEST CLUSTER CONNECTION**
- **Reconnect:** On the DX Cluster page, tap **RECONNECT**
- **Wrong cluster:** Try `dxspider.co.uk:7300` if yours is unreliable

### QSOs Not Uploading

- **Check server:** Tap **Settings** → **TEST SERVER CONNECTION**
- **Local queue:** Tap the **Logbook** menu to see QSOs — they're stored locally even if sync fails. Red = not yet uploaded, amber = uploading, green = uploaded.

## Technical Details

### Architecture
- **Language:** Kotlin
- **UI Framework:** Android AppCompat + Material Design
- **Database:** SQLite (local QSO storage)
- **Networking:** OkHttp3 (Kloudlogger API), raw sockets (telnet for DX cluster), Bluetooth SPP (IC-705 CI-V)
- **Sensors:** Accelerometer + Magnetometer fusion (device orientation)
- **Camera:** Camera1 API (QO-100 finder AR overlay)

### Permissions

| Permission | Purpose |
|-----------|---------|
| `INTERNET` | Server sync, QRZ lookup, DX cluster telnet |
| `ACCESS_FINE_LOCATION` | GPS for QO-100 finder look angles |
| `ACCESS_COARSE_LOCATION` | Network-based location fallback |
| `CAMERA` | QO-100 AR overlay display |
| `ACCESS_NETWORK_STATE` | Monitor internet connectivity |
| `BLUETOOTH_CONNECT` | IC-705 CI-V connection (Android 12+) |
| `BLUETOOTH_SCAN` | Discover paired IC-705 device (Android 12+) |

## Author

**Chris M7JEX** (Somerset, UK)

## Licence

This software is provided 'as is' for the community. Please do not sell or modify this software.

- QRZBook: [qrzbook.net](https://qrzbook.net)
- Kloudlogger: [kloudlogger.com](https://kloudlogger.com)
- QRZ: [qrz.com/db/M7JEX](https://www.qrz.com/db/M7JEX)

## FAQ

**Q: Can I use this with Cloudlog?**  
A: Yes. Kloudlogger is Cloudlog compatible; the app works with both.

**Q: Does the app work offline?**  
A: Partially. You can log QSOs offline and they're stored locally. Once you have internet, they'll sync to the server. DX cluster and QRZ lookup obviously require internet. Telepathy is not yet supported!

**Q: Can I edit a QSO after logging?**  
A: Yes. Open the **Logbook**, tap a QSO, and tap the edit pencil icon.

**Q: How often does the app sync to the server?**  
A: Default is 30 seconds after a new QSO. You can change this in **Settings** → **Server** → **Auto-sync delay**.

**Q: The DX cluster keeps disconnecting.**  
A: Some clusters have timeouts or require periodic keep-alives. Try a different cluster from the suggestions in the settings, or check with your cluster sysop.

**Q: Does the IC-705 integration work with other Icom radios?**  
A: Possibly, but it has only been tested on the IC-705. Other radios may use different CI-V addresses or sub-command codes.

**Q: Do I need the AH-705 for the TUNE button to work?**  
A: You need a compatible tuner. The TUNE button sends CI-V command 1C 01 02 which starts a tune cycle. Map the VOX key to TUNE in the IC-705 menu for it to operate the ATU.

---

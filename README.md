# NetPulse

**Real-time internet monitoring and performance analytics**

NetPulse is a browser-based internet monitor that tracks connection drops, latency, and speed in real-time. It visualizes 30 minutes of history, logs all events, and exports reports for your ISP. All data stays local — no servers, no installation. Just open and monitor.

![Status](https://img.shields.io/badge/status-stable-green)
![License](https://img.shields.io/badge/license-MIT-blue)
![Platform](https://img.shields.io/badge/platform-browser-orange)

---

## Features

- **Real-Time Monitoring** — Checks connection every 3 seconds with visual online/offline status
- **Latency Tracking** — Measures and displays average ping times
- **Speed Testing** — Automatic tests every 5 minutes + manual testing option
- **Interactive Graphs** — 30-minute history with latency and speed views
- **Event Logging** — Records all connect/disconnect events with timestamps
- **Export Reports** — JSON snapshots for ISP documentation
- **100% Local** — All data stored in browser, nothing sent to external servers
- **Zero Setup** — Single HTML file, no installation required

## Quick Start

1. Download `connection-monitor.html`
2. Open it in any modern browser
3. Start monitoring

That's it. No build steps, no dependencies, no configuration.

## Dashboard Overview

| Metric | Description |
|--------|-------------|
| **Uptime** | Connection reliability percentage |
| **Drops** | Number of disconnection events |
| **Session** | Current monitoring duration |
| **Avg Latency** | Mean response time in milliseconds |
| **Download** | Current download speed (Mbps) |
| **Upload** | Current upload speed (Mbps) |

## Graph Views

**Latency View**
- Green/red bands show online/offline periods
- Blue line tracks latency over time

**Speed View**
- Green/red bands show online/offline periods
- Blue line for download speed
- Purple line for upload speed

## Controls

| Button | Action |
|--------|--------|
| **Test Now** | Run immediate speed test |
| **Export Report** | Download JSON report |
| **Pause/Resume** | Toggle monitoring |
| **Clear Data** | Reset all statistics |

## Export Data

Exported reports include:

```json
{
  "reportGenerator": "NetPulse v1.0",
  "exportDate": "2024-01-15T10:30:00.000Z",
  "summary": {
    "totalUptime": "3600 seconds",
    "totalDowntime": "45 seconds",
    "uptimePercentage": "98.77%",
    "connectionDrops": 2,
    "averageLatency": "42ms"
  },
  "speedTest": {
    "currentDownload": "85.50 Mbps",
    "currentUpload": "22.30 Mbps",
    "averageDownload": "82.15 Mbps",
    "averageUpload": "21.80 Mbps"
  },
  "events": [...],
  "connectionHistory": [...],
  "speedTestHistory": [...]
}
```

## Technical Details

### Data Storage
- **localStorage key**: `netpulse_data`
- **Connection history**: Last 600 points (30 min at 3s intervals)
- **Speed tests**: Last 50 results
- **Events**: Last 100 entries

### Connectivity Check
- Primary endpoint: Google favicon
- Fallback: Cloudflare favicon
- Timeout: 5 seconds
- Interval: 3 seconds

### Speed Test
- Download: 3 iterations using CDN resource
- Upload: 2 iterations with 512KB payload
- Auto-test interval: 5 minutes

## Browser Support

Works on all modern browsers:
- Chrome / Edge (recommended)
- Firefox
- Safari
- Opera

## Use Cases

- **Troubleshooting** — Identify if issues are internet or application-related
- **ISP Documentation** — Collect evidence of connection problems
- **Pattern Recognition** — Spot recurring drop times
- **Performance Monitoring** — Track speed degradation over time
- **Service Validation** — Verify ISP meets promised speeds

## Privacy

NetPulse respects your privacy:
- No data sent to external servers
- No analytics or tracking
- No cookies (uses localStorage only)
- All processing happens in your browser

## License

MIT License — feel free to use, modify, and distribute.

---

**NetPulse** — Monitor your connection, document the drops.


📄 `README.md` (Updated for v1.0.0)

# 🌿 Home Assistant Plant Care System

Modular blueprint and JSON-based automation for intelligent plant monitoring, alerting, and dashboard integration.

---

## 🧠 Features

- Dynamic thresholds per plant, stage, and month via `plantdata.json`
- Real-time comparison of lux, light duration, AWC, temperature, humidity
- Light duration tracking using lux + binary + history_stats
- Alert generation and notifications
- Dashboard-ready care summaries and status
- Semantic versioning and modular file structure

---

## 📁 Folder Structure

# /config/plant_care/
# ├── blueprints/
# │   └── plantcare_v1.0.0.yaml
# ├── entities/
# │   ├── input_text.yaml
# │   ├── binary_sensors.yaml
# │   └── sensors.yaml
# ├── plantdata.json 
# ├── plant_dashboard.yaml
# ├── lovelace_dashboards.yaml
# ├── LICENSE
# ├── README.md


---

🛠 Setup Checklist (First-Time User)

1. ✅ Minimal configuration.yaml setup

Add these lines to your `configuration.yaml`:

#plant_care
input_text: !include plant_care/entities/input_text.yaml
binary_sensor: !include plant_care/entities/binary_sensors.yaml
sensor: !include plant_care/entities/sensors.yaml
lovelace:
  dashboards: !include plant_care/lovelace_dashboards.yaml


This loads all plant care entities and registers the dashboard in the sidebar.

---

2. 📦 Folder structure

Ensure your `/config/plant_care/` folder contains all the folders and files:

• `entities/` → holds modular entity definitions
• `plantdata.json` → defines thresholds and care summaries
• `blueprints/` → contains the automation blueprint
• `plant_dashboard.yaml` → defines the dashboard view
• `lovelace_dashboards.yaml` → registers the dashboard
• `LICENSE` and `README.md`


---

3. 🌱 Import and configure the blueprint

In Home Assistant UI:

• Go to Settings → Automations & Scenes → Blueprints → Import Blueprint
• Paste the contents of `plantcare_v1.0.0.yaml`
• Create a new automation from the blueprint
• Fill in:• `plant_type` and `growth_stage`
• Sensor entities: lux, AWC, temperature, humidity
• `light_duration_sensor` (from history_stats)
• `notify_target` (e.g. mobile app or Telegram)
• `alert_time` (e.g. `"18:00:00"`)



---

4. 📊 View your dashboard

After restarting Home Assistant:

• The Plant Care dashboard will appear in the sidebar
• It shows live sensor values, care summaries, and alert status
• No manual card setup needed — it’s fully defined in YAML

Sidebar-integrated dashboard shows:

• Plant type, stage, and current month
• Live sensor values
• Care summary from JSON
• Alert status from input_text


---

🧩 Versioning

v1.0.0 – Initial Release

Includes:

• Threshold logic and care summaries
• Blueprint automation with configurable alert time
• Light duration tracking
• Modular entity definitions
• Sidebar dashboard integration
• Licensing and attribution


---

🙏 Attribution

If you use or adapt any part of this system (blueprints, JSON logic, summaries, or automation structure), please credit:

Martin – Home Assistant Plant Care System

Include attribution in your README, comments, or documentation.
Example:

“Based on Martin’s Home Assistant Plant Care System (CC BY-NC 4.0)”

---

📜 License

This project is licensed under the Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0).

You may use, adapt, and share this system for personal and non-commercial purposes, provided that:

• You credit Martin as the original author
• You include a link to this system or reference its origin
• You do not use it for commercial gain without explicit permission


See `LICENSE` for full terms.
License details: https://creativecommons.org/licenses/by-nc/4.0/

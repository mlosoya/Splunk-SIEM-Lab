# Splunk SIEM Home Lab

## Overview
Built a Splunk Enterprise SIEM lab on Windows to practice log ingestion, security event monitoring, alert creation, and dashboard building using real Windows Event Log data.

## Objectives
- Install and configure Splunk Enterprise on Windows
- Ingest Windows Security, System, and Application Event Logs
- Search and analyze security events using SPL queries
- Create a detection alert for failed login attempts
- Build a security dashboard to visualize event data

## Environment
- Windows 10/11 host machine
- Splunk Enterprise free trial
- Data source: Windows Event Logs (Security, System, Application)

## Steps Performed
1. Downloaded and installed Splunk Enterprise on Windows
2. Configured Splunk to monitor local Windows Event Logs
3. Searched and analyzed 34,456 security events using SPL queries
4. Searched for failed login attempts using EventCode 4625
5. Triggered real failed login events by entering wrong passwords
6. Created a detection alert named Failed Login Attempt Detected triggered when EventCode 4625 results are greater than 0
7. Built a Security Overview dashboard with two panels showing event counts by type and failed login attempts over time

## SPL Queries Used
- `index=main sourcetype=WinEventLog:Security` — pulls all security events
- `index=main sourcetype=WinEventLog:Security EventCode=4625` — filters for failed login attempts
- `index=main sourcetype=WinEventLog:Security | stats count by EventCode` — counts events by type
- `index=main sourcetype=WinEventLog:Security EventCode=4625 | timechart count` — charts failed logins over time

## What I Learned
- How to ingest and search Windows Event Logs in Splunk
- How to use SPL to filter and analyze security events
- How EventCode 4625 maps to failed login attempts in Windows
- How to create detection alerts and dashboards in a SIEM

## Tools Used
- Splunk Enterprise
- Windows Event Viewer
- SPL (Splunk Processing Language)

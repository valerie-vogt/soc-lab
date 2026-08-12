# Build — Sysmon
Date: 2026-08-12

## What I was trying to do
Set up Sysmon to familiarize myself with event logs.
## What I built / ran
installed sysmon:
  downloaded sysmon zip from 'https://learn.microsoft.com/sysinternals/downloads/sysmon'
  Extracted contents
  Opened power shell as administrator and navigated to the fold sysmon extracted to 
  ``` cd C:\Users\YourName\Downloads\Sysmon ```
  ran Sysmon64.exe with config provided by 'github.com/SwiftOnSecurity/sysmon-config' (note: using a premade config as i am not focusing on the configuration side of sysmon at this moment)
  ``` .\Sysmon64.exe -accepteula -i sysmonconfig-export.xml ```
## What it does now
Sysmon allows me to view various events happening on my VM and inspect each one for anomalous behavior.
## What I observed
In event viewer > applications and service logs > Microsoft > Windows > sysmon > Operational i observed many types of events notable event ID 1, Event ID 13, and Event ID 22.
with additional research i learned the types of events i saw
Event ID 1:
  A process was created e.g. a program was started, viewing the details of these events gave me information on what was launched, where it was launched from and with what command, and who (what program) launched it.
Event ID 13:
  Registry value change. something wrote to the windows registry. (id like to look more into the windows registry to understand more beyond persistent this does)
Event ID 22: 
  DNS Query, a process asked to resolve a domain, while not as interesting as the rest, given my experience with DNS protocol still useful information about what queried a domain and what domain was queried.

while watching the event viewer and getting to know it i noticed an event where msedge.exe ran a cmd with -utility -utility-sub-type=unzip.mojom.unzipper with that i concluded it was for the ms edge web browser unzipping my recently downloaded files

## Where I got stuck and how I got unstuck
During this process i did not get stuck.

## What this would look like in a real environment
In a real SOC environment Sysmon would feed logs into SIEM, where analysts write detection rules against these fields.

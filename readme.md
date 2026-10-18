# Unofficial Roth Touchline Web Portal Refresh

A modern, unofficial browser interface for legacy Roth Touchline LAN controllers. View room temperatures, with optional temperature control, without a Java browser plugin.

> [!WARNING]
> Experimental software, developed with AI assistance, without independent human code review or hardware safety validation. Not affiliated with or approved by Roth. Installation and use may disrupt heating or cause damage. Use at your own risk and keep a working backup.

## Choose your version

| Version | File | Features |
| --- | --- | --- |
| No control | [portal/no control/index.htm](portal/no%20control/index.htm) | Displays room temperatures. |
| Control | [portal/control/index.htm](portal/control/index.htm) | Adds a control switch and −/+ temperature-target adjustments. |

Both files are named `index.htm`. Choose **one**; no renaming or build tools are needed.

## Compatibility

Previously used hardware:

- Thermostat: Roth Touchline ROU **1135006444**.
- Controller: Touchline 8-channel LAN, Nordic **17466393.008**.

The exact tested firmware version was not recorded. The European controller **1135006442** is untested. The January 2018 **V2.8 with LAN** package layout was inspected, but **no exact hardware/firmware combination is validated for this release**.

## Manual installation

**Find and legally obtain suitable Roth firmware and update instructions yourself.** Confirm compatibility with your exact device. This repository supplies neither vendor software nor device-update instructions.

1. Back up your current installation and keep an untouched copy of the original firmware package. Establish a recovery method before proceeding.
2. Extract the package and make a separate working copy.
3. In the working copy, locate and delete the original **`index.htm`**.
4. Copy **one** `index.htm` from the version you chose above into the same location. Copy the file, not its containing folder.
5. Leave **every other file unchanged**, including firmware images, Java libraries, and legacy assets. No additional deletions are required.
6. Compare against your original copy: only `index.htm` should differ. Use the update process you independently established for your device.

Keep the modified vendor package private. Do not commit it or include it in project releases.

## Usage

Open the controller’s local IP address in your browser, then press **refresh** at the bottom right. Readings are refreshed manually and may be slow.

With the **control** version, complete a successful refresh, enable the control switch, and use −/+ to adjust individual targets. Targets move to the next half-degree step within the controller-reported limits. Refreshing turns control off.

If a change is **not confirmed**, refresh and check the actual target before retrying: the change may already have reached the controller.

## Rollback

Replace the project’s `index.htm` with the original from your backup, using your established recovery process. Check normal operation locally afterward.

Restoring the page **does not restore temperature targets** changed through the control version. Restore those separately using approved controls.

## Limitations and safety

- Keep the controller on a trusted LAN; do not expose it directly to the internet. The portal adds no authentication or encryption.
- This is not a safety monitor. Continue using approved thermostats and heating controls.
- No schedule, pairing, operating-mode, pump/valve, or safety-limit editing is provided. Temperature-target changes can still affect heating demand.
- The code accepts up to 256 paired devices across 16 controllers; this is not tested hardware capacity.

## Warranty and limitation of liability

Modifying, installing, and using this project is at your own risk. The software and documentation are provided **“as is” and “as available,” without warranties of any kind**, express or implied, including merchantability, fitness for a particular purpose, and non-infringement, to the extent permitted by applicable law.

To the fullest extent permitted by applicable law, the authors and contributors disclaim liability for claims, losses, or damages arising from modification, installation, use, or inability to use the project, including heating interruption, equipment or property damage, and data loss.
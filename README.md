# Extinguisher Tracker

A phone-friendly extinguisher register, inspection log, spreadsheet reconciliation tool, and reporting app.

## Current edition: local-first

The app works without Firebase sign-in or shared cloud storage. It saves records in the browser on the current device. A public HTTPS host allows phone-camera scanning, but it does not synchronize data between devices.

Features include extinguisher records, QR and barcode labels, camera scanning on supported browsers, configurable inspection checklists, inspection history, CSV/XLS/XLSX imports, review-before-import reconciliation, CSV exports, and print-to-PDF reports. Fresh installs start with an empty fleet.

## Move data between devices

1. On the device with the latest records, open **Reports → Move data between devices → Download backup JSON**.
2. Transfer the downloaded `extinguisher-tracker-backup-YYYY-MM-DD.json` file using a method you trust.
3. On the other device, open **Reports → Restore backup**, choose that file, review the counts, then select **Merge backup**.

A restore merges fleet and inspection records by ID. A backup record replaces a local record with the same ID; records found only on the local device are kept. The checklist is replaced by the backup checklist. For two-way updates, restore each device's backup on the other, then repeat with the newly merged backup so both devices end up with the same records. Keep copies of backups before merging if you need a rollback.

CSV fleet and inspection reports can also be transferred, but the full JSON backup preserves checklist settings and inspection checklist responses.

## Hosting

GitHub Pages is configured to publish this repository's root from the `main` branch. The expected URL is `https://ishalommensah-crypto.github.io/extinguisher-tracker/`, but that URL returned 404 on the last check, so hosting is not yet confirmed live. The app source is public. Extinguisher records are not uploaded by the app; they stay in each browser's local storage. Data in backup files may contain asset IDs, locations, and inspection details, so share those files only through a trusted channel.

## Later shared edition (optional)

Shared team sync is off in this edition. Re-enabling it requires Firebase project permissions for Authentication, Firestore rules, and Hosting. Manual JSON backup/restore is the current no-cost way to carry data between devices.

## Safety notes

- The configurable checklist is a general starting point, not a replacement for your jurisdiction's required inspection standard. Have the responsible fire-safety professional approve it.
- The app does not upload inspection photos or run OCR. Transcribe paper/photo entries and review matches before importing.
- QR/barcode, spreadsheet, and font libraries load from public CDNs, so the browser needs internet access.



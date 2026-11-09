# appaday-186-home-asset-tracker

**AppADay Day 186, Home Asset Tracker** (Utility, AI)

Live: https://augustineiacopelli.github.io/appaday-186-home-asset-tracker/
Portfolio: https://augustineiacopelli.github.io/appaday/

Photograph your belongings room by room and Claude suggests the name, brand, model, condition and a replacement and used value range for each one. Track purchase prices, compare your total against your coverage limit, and export an insurance-ready PDF, a CSV, or a full photo backup. Everything stays on your device.

## How it works

On first run a five step walkthrough explains the two photo slots, Claude suggestions and Confirm all, purchase price versus estimate, the coverage limit, and why to keep a backup off the phone, ending on Add my first item. The empty inventory shows the same three starting steps, and the walkthrough can be reopened anytime from Help in Settings.

Each item has two photo slots, Whole item and Label or plate, that open the rear camera. With a Claude API key, Claude reads the photos and suggests the name, brand, model, category, condition, a serial number only when one is clearly legible, a replacement range for a new equivalent, a used fair market range, a confidence level and a one line basis. Suggested fields arrive tinted with a Claude tag that clears when you edit the field or tap Confirm all, and any field still unconfirmed at save time is recorded with the item. A blurry or unclear photo comes back as ambiguous with its reason and fills nothing. Without a key, a chooser offers to add one or to continue without AI, and every field can always be entered by hand.

An item's value is its purchase price when you enter one (marked Yours). Otherwise it is the midpoint of the range that matches your policy basis, replacement cost or actual cash value (marked Est.), times quantity. Jewelry and Watches or Collectibles items over $1,500 carry a Sublimit badge.

The Items view filters by room chip, category and search across name, brand, model, serial and notes. The Dashboard shows the total, the estimated range, the split between your prices and estimates, a coverage bar (green under 80 percent of your limit, amber from 80 to 100, red with the underinsured amount above 100), and value by room and by category.

## Exports and backup

The PDF report is letter size, with a cover page (date, totals, policy basis, coverage comparison and a disclaimer that estimates are not appraisals) and item pages grouped by room, each with a one inch thumbnail, every field and a room subtotal. It saves as home-assets-YYYY-MM-DD.pdf. The CSV holds every field with a UTF-8 BOM and no photos. The JSON backup holds settings, items and every photo; restore offers Merge (by id, newer updatedAt wins) or Replace, and nothing is cleared until the whole file has been read. Settings reminds you when you have changes since the last backup.

## Settings

Claude key manager from the shared AppADay key ring, the current model name, coverage limit, policy basis, room add, rename and delete (deleted rooms move their items to Unassigned), backup and restore, and a guarded Erase everything.

## Tech

One self contained index.html in vanilla HTML, CSS and JavaScript. Storage in IndexedDB through idb-keyval (items, settings, and each 1200px photo as a Blob), with persistent storage requested on first run. PDF by jsPDF. Claude key from keys.js and model from models.js at the portfolio root; the app has no key field and no model ID of its own. Photos go only to Anthropic and only when you add them with a key saved.

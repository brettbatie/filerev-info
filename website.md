# Filerev — Feature & Capability Reference

## What Filerev Is

Filerev is a web app (with Android and iOS apps, plus a Google Workspace Marketplace add-on) that helps users clean up and organize Google Drive. It scans a user's Google Drive account, categorizes files, surfaces clutter (duplicates, hidden files, old files, empty files/folders, temporary files), and supports bulk delete and bulk move operations. It also supports Shared Drives and Shared-with-Me files.

Filerev does not download user files. It connects directly to Google Drive, fetches minimal metadata, and performs actions (move/delete) only when the user initiates them. Deletions go to the Google Drive trash (recoverable for 30 days).

- Website: https://filerev.com
- App: https://my.filerev.com
- Company: Filerev, Inc. (Michigan corporation), Traverse City, MI
- Support: brett@filerev.com
- Founder: Brett Batie

## Core Workflow

1. **Scan** — User logs in with Google, chooses what to scan (entire Drive, specific folders, Shared Drives, Shared-with-Me, Hidden Files, Synced Computers). Scan uses a proprietary algorithm that reads minimal metadata; it does not download files.
2. **Review** — After scan, a summary page shows storage usage across Google Drive/Gmail/Google Photos/uncategorized, largest folders, duplicate storage, hidden/empty file counts, and file-type breakdown.
3. **Organize** — User drills into categories, applies filters, and moves or deletes files. Bulk operations act on an entire category or a filtered subset.

Users get an email when a scan completes.

## Tools / Features

### Duplicate File Finder
- Detects files with 100% identical content (byte-level fingerprint match), not filename or size matching.
- Shows thumbnails, folder location, owner, creation date for each duplicate.
- "Same Folder Duplicates" view isolates duplicates sitting in the exact same folder — the safest cleanup target.
- Supports bulk delete, or manual per-file selection (including "select oldest" / "select newest" on a page).
- Filters: folder, creation date, owner, file type/extension, storage used.
- **Google Docs / Sheets / Slides**: duplicate detection for Google's proprietary formats is not currently supported.
- **PDFs**: PDFs with differing internal metadata (author, unique document IDs, digital signatures, generator software) won't group as duplicates even if the visible content is identical — intentional, so signed/versioned documents aren't collapsed together.
- **Images**: images with differing EXIF/metadata, or that have been cropped/resized, won't match — only byte-identical images group.
- **Thumbnails may differ across duplicates**: Google doesn't always produce identical thumbnails for identical files (videos in particular may use different frames). Grouping is content-based, not thumbnail-based.
- **Storage-used can differ across duplicates**: older Google Docs/Sheets/Slides or photos synced before Google's free-storage changes may report 0 bytes while a newer identical copy uses real quota.

### Duplicate Photo Finder
- Subset of the Duplicate File Finder filtered to image file types (jpg, png, gif, webp, tiff, psd, raw, bmp, jpeg, svg).
- Duplicates must be 100% byte-identical content (file name, folder, owner, creation date can differ).
- Operates on Google Drive only — not Google Photos.

### Bulk File Deleter
- Delete all files in any predefined category with one click, or filter first and delete the subset.
- Categories supported: duplicate, hidden, empty, large, old, shared, temporary, files by mime type/extension.
- No hard limit beyond plan quotas; works where Google Drive's native UI can only select ~100 files at a time.
- Files go to Google Drive trash (30-day recovery window).

### Hidden File Finder
- Finds "orphaned" files — files that exist in Google Drive but aren't inside any folder the user can browse to (commonly caused when someone else deletes a shared parent folder while the file inside is owned by the user).
- Hidden files still count against the Google Drive storage quota.
- User can restore hidden files by moving them into a folder, or bulk delete them.
- Note: desktop-style dotfiles (e.g., `.ds_store`) are a separate concept and are found via the File Type Organizer.

### Empty File Remover
- Finds zero-byte files. Only shows truly empty files (where no prior version contains data), so removal is safe.
- Also exposes empty folders.
- Supports filters (folder, owner, file type, creation date) and bulk delete.

### Folder Size Analyzer
- Shows folder sizes (Google Drive does not expose this natively).
- Tree-based browsing with graphical size representation; largest folders first.
- Can scan a single folder or a subset without scanning the whole Drive.
- Does not download files — reads metadata, so it's fast regardless of network speed.

### Storage Analyzer
- High-level view of storage across Google Drive, Gmail, Google Photos, and uncategorized (e.g., third-party apps, Android/iOS backups, Google One shared pools).
- Breakdown by custom categories (duplicate, hidden, empty, large, old, shared, temporary, trash) and by file type (Documents, Photos, Audio, Video, Archive).
- Graphical storage usage visualization.
- **Scope note**: Filerev *displays* storage usage for Gmail and Google Photos but does not find or delete duplicates inside them. Duplicate and cleanup tools operate on Google Drive only.
- Note re: Google Docs/Sheets/Slides — these count against quota unless created before 2021-06-01 and never edited after that date.

### Google Drive Organizer
- Auto-categorizes files during scan without modifying anything in Drive.
- Umbrella feature that ties together duplicate/large/hidden/empty/old file views plus filters and bulk actions.

### File Type Organizer / Sorter (Files by Type & Extension)
- Groups files into high-level categories: Documents, Photos & Images, Audio, Video, Archive, Other.
- Drills down to specific file types (e.g., Documents → PDF, Microsoft Word, PowerPoint, Markdown, CSV, Google Docs, Google Sheets).
- Also browsable by raw file extension, including files with no extension.
- Shows storage used per file type; largest first.

### Video Duration Summary
- Shows total video duration across all videos in a Google Drive account (or within a specific folder / file type).
- Requires Google to have "processed" each video; Filerev flags when unprocessed videos are present (duration can't be computed for those until Google processes them).

### Old File Manager
- Default view: files older than 1 year. Selectable to older thresholds.
- Use cases: data retention compliance (HIPAA, GDPR), archival, reclaiming storage.
- Archive by moving, or bulk delete by date range.
- Can combine with file-type filter (e.g., "PDFs older than X").

### Shared File Viewer ("Not Owned by Me")
- Shows files that others have shared with the user.
- Filter by sharing person, file extension, etc.
- Finds duplicates between user-owned files and shared copies.
- Storage note: shared files owned by someone else do **not** consume the user's quota. But uploading a new version of someone else's shared file keeps the owner as the other user (and their quota). Uploading a new file into a shared folder defaults to being owned by the uploader.
- Cannot delete files you only have read access to — can only hide them from your view. Files inside a shared folder also can't be removed individually (access comes from the folder, not the file).

### Shared Drive Organizer
- Scans one or multiple Google Workspace Shared Drives (can combine with My Drive scan).
- Same category views as My Drive (duplicates, hidden, empty, large, old, temporary, by extension, folder sizes).
- Shared Drives limits: 500,000 files/folders per Shared Drive; storage shares the Workspace pool.
- Shared Drives require a Workspace plan: Business Starter/Standard/Plus, Enterprise Standard/Plus, Education Fundamentals/Standard/Teaching and Learning Upgrade/Plus, Essentials variants, Nonprofits, G Suite Business.

### Temporary File Cleaner
- Finds common temp file patterns: `.tmp`, `.temp`, `.old`, `.download`, etc.
- These typically get synced from desktop apps (e.g., Microsoft Word intermediate files) via Google Drive for Desktop.
- Bulk delete or filter-then-delete.

### Clear Google Drive (Remove All Files)
- Deletes every file in the user's Drive via the Bulk Delete tool (sets Storage Used filter to `-1` to match all).
- Confirmation dialog before deletion. Files go to trash (30-day recoverable window).
- Useful for a full reset.

### Restore Google Drive Trash (Bulk Trash Restore)
- Restores every file in the Google Drive trash with one click.
- Preserves original folder hierarchy by restoring top-level folders before nested ones (Google's native flow restores orphaned intermediates to Drive root, which Filerev avoids).
- Found under "Files by Category" page → trash row → 3-dot menu → "Restore Files in Trash".

### Export Google Drive File List (CSV Export)
- Exports a list of files and per-file metadata from any Filerev category to a CSV report.
- Available on every category view (Duplicates, Hidden, Empty, Large, Old, Shared, Temporary, Files by Type, Files by Extension, Folder Sizes, etc.) and respects any filters applied — so a user can export "all files", "files over X MB", "files in a specific folder", "PDFs older than 2 years", and similar slices.
- Use cases: auditing what's in a Google Drive account, compliance/retention reviews, sharing an inventory with a client or manager, migration planning, spotting ownership issues, and general "what do I actually have in Drive?" reporting.

### Filters (cross-cutting feature)
Available on category views to narrow results before taking action. Filter dimensions:
- File creation date (range)
- Owner
- Storage used by the file
- Folder(s) the files reside in
- File type / extension

### Custom View
Paid-plan feature. Build a filter-based view that isn't one of the built-in categories. Bookmarkable URL.

### Scan Options
- My Drive, Shared with Me, Hidden Files (all plans support at least some of these).
- Synced Computers (paid plans).
- Shared Drives (Premium only).
- Select specific folders to scan instead of the whole account (Standard and up).

### Platforms
- Web app at my.filerev.com.
- Android app (Google Play, Samsung Galaxy Store).
- iOS app (Apple App Store).
- Google Workspace Marketplace add-on — installs as a sidebar inside Google Drive.
- No native desktop app.

## Pricing & Plans

Billing is via Stripe. Annual billing is ~60% off vs. monthly. Cancel any time from the billing page (`my.filerev.com/billing`). No refunds (see terms). Google sign-in required.

### Free
- 1 scan/month, up to 1M files
- 500 moves & deletions/month
- Scans My Drive only
- No bulk delete, no filters
- Includes view access to: Duplicate, Hidden, Empty, Large, Old, Files Owned by Others, Temporary, Files by Type, Files by Extension
- **Permanent tier — not a time-limited trial.** Free accounts are deactivated only after 30 days of inactivity (scanned data is cleared at that point).

### Basic — $4/mo (billed annually)
- 3 scans/month, up to 1M files
- 10,000 moves & deletions/month
- Adds: Synced Computers, Shared with Me, Bulk Delete, Filters, Custom View
- Low scan priority

### Standard — $8/mo (billed annually) — "Most Popular"
- 5 scans/month, up to 2M files
- 100,000 moves & deletions/month
- Adds (vs. Basic): Select Folders to Scan, Storage Analyzer, Empty Folders view
- Medium scan priority

### Premium — $12/mo (billed annually)
- Unlimited scans/month, up to 5M files
- 500,000 moves & deletions/month
- Adds (vs. Standard): Scan Shared Drives
- High scan priority

### Premium+ Add-on
- Paid extension that can be stacked onto the Premium plan to raise limits (files scanned, moves/deletions).
- Configured via a slider on the public pricing page; existing Premium subscribers can add it from the Stripe Billing Portal.

### Bulk / Enterprise Licensing
- Custom pricing and packaging available for bulk-license and enterprise use cases, plus custom feature requests.
- Arranged via the Filerev contact form.

### Plan change mechanics
- Plan upgrades/downgrades are prorated.
- Monthly limits (scans, moves/deletions) reset on the account-creation anniversary day each month, not on the first of the month.
- Discontinued plans: the legacy **Individual** plan was retired in February 2022. Existing subscribers retain access to it; it cannot be newly purchased.

### Plan comparison quick reference

| Feature | Free | Basic | Standard | Premium |
|---|---|---|---|---|
| Scans/month | 1 | 3 | 5 | unlimited |
| Files scanned/month | 1M | 1M | 2M | 5M |
| Moves/deletions/month | 500 | 10,000 | 100,000 | 500,000 |
| Scan priority | lowest | low | medium | high |
| Bulk Delete | — | ✓ | ✓ | ✓ |
| Filters | — | ✓ | ✓ | ✓ |
| Synced Computers | — | ✓ | ✓ | ✓ |
| Shared with Me | — | ✓ | ✓ | ✓ |
| Custom View | — | ✓ | ✓ | ✓ |
| Select Folders to Scan | — | — | ✓ | ✓ |
| Storage Analyzer | — | — | ✓ | ✓ |
| Empty Folders view | — | — | ✓ | ✓ |
| Shared Drives | — | — | — | ✓ |
| Duplicate/Hidden/Empty/Large/Old/Owned-by-Others/Temporary/By-Type/By-Extension | ✓ | ✓ | ✓ | ✓ |
| Android & iOS Apps | ✓ | ✓ | ✓ | ✓ |
| Customer Support | ✓ | ✓ | ✓ | ✓ |

When a user's Drive exceeds their plan's file limit, they receive an email prompting upgrade.

## Security & Privacy

- OAuth into Google; Filerev requests minimal Drive scopes.
- All transfers over SSL. Stored account info is encrypted at rest and in transit, with per-user isolation.
- **Annual third-party security audits** against [OWASP ASVS](https://owasp.org/www-project-application-security-verification-standard/) and [CASA (Cloud Application Security Assessment)](https://appdefensealliance.dev/casa) standards. Audit results are also reviewed by Google. Public CASA reports are published on filerev.com for 2024, 2025, and 2026.
- Automated security scans run before every app release.
- User data is never sold.
- Not HIPAA compliant — users subject to HIPAA may not use Filerev.
- Payment processing via Stripe; Filerev does not store card numbers.
- **Data retention**: scanned file metadata is automatically removed after 30 days of account inactivity.
- Users can delete their account and data via https://filerev.com/help/account/account-deletion/ or by emailing personal-data@filerev.com. Deletion has a 30-day grace window — signing back in during that window cancels the deletion.
- Retained after deletion: email address & preferences, IP, last login, high-level usage counts.
- Data hosted in the United States.
- **Google Advanced Protection Program**: accounts enrolled in Google's Advanced Protection Program block Filerev by default. Gmail users can unenroll; Workspace admins can allowlist Filerev via Admin Console → Security → Access and data control → API Controls → Manage Third-party app access.
- Press coverage: ZDnet and Chrome Unboxed have published reviews of Filerev.

## Affiliate Program

- 30% recurring commission on referred paid subscriptions.
- Managed via Rewardful; paid monthly via PayPal; $100 minimum payout.
- No self-referrals, no paid ads on branded terms, no coupon/cashback sites.
- Signup: https://filerev.getrewardful.com/signup

## Notable Behavioral Details for LLMs

- **Duplicate definition**: content is 100% byte-identical. Not filename-based, not fuzzy. Google proprietary formats (Docs/Sheets/Slides) are not currently checked for duplicates.
- **Deletions are soft**: always go to Google Drive trash. 30-day recovery window before permanent deletion. Filerev's "Restore Trash" tool can pull them back en masse.
- **Hidden/orphaned file mechanism**: occurs when a file's parent folder (owned by someone else) is deleted. The file persists, still counts against quota, but isn't reachable via normal browsing.
- **Google Drive's native limitations that Filerev works around**:
  - No folder-size display
  - No native duplicate detection
  - Multi-select in the web UI caps around 100 files and can crash on large selections
  - No bulk trash restore
  - No automatic old-file deletion
  - No way to view files by specific extension (only broad types)
- **Shared files ownership quirk**: if someone shares a file with you, it doesn't use your quota. But copying it into "My Drive" creates a new owned copy that does.
- **Read-only shared files cannot be deleted**: Filerev can only hide them from the user's view — the same limitation Google Drive imposes. Files inside a shared folder also can't be removed individually; the action has to happen at the folder level.
- **Scan scope is flexible**: user can scan entire Drive, specific folders, Shared Drives (Premium), or Shared-with-Me. Scan is metadata-only, so typically fast even on very large accounts.
- **Multiple Google accounts**: each Google account needs its own Filerev login (switch via sign-out or `my.filerev.com/login?switch=1`). A single Filerev subscription can effectively clean files across accounts when files live in a Shared Drive or have been re-assigned to the logged-in user as owner.
- **Storage-usage troubleshooting caveats**:
  - Each Shared Drive has its own trash that counts against Workspace storage separately from My Drive trash.
  - After mass deletions, Google can take up to ~24 hours to update reported storage usage.
  - "Uncategorized" storage typically comes from third-party apps' hidden data folders, Android/iOS device backups, Google One shared storage pools, or other Google services.
- **Scale claim**: "7.0 billion files scanned, 37 petabytes organized" across the user base.

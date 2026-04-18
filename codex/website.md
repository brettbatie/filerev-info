# Filerev Website Summary for Future LLMs

This file is a condensed product brief derived from Filerev's website content. It removes crawl metadata, page structure dumps, legal text, testimonials, founder bio, affiliate content, contact/coupon pages, repetitive CTA copy, and long general-audience FAQs.

## What Filerev Is

Filerev is a Google Drive cleanup and organization app. It scans a user's Google Drive account, categorizes files and folders, shows where storage is being used, and helps users review, move, delete, bulk delete, or restore items.

Primary use cases:

- Find duplicate files
- Identify large files and folders
- View storage usage across Google Drive, Gmail, and Google Photos
- Find hidden/orphaned files
- Find empty files and empty folders
- Find old files
- Browse files by type or extension
- Review files shared with the user or owned by others
- Find temporary files
- Organize Shared Drives
- Bulk delete large sets of files
- Restore all files from Google Drive Trash
- Wipe all files from Google Drive

## Core Product Model

Filerev's basic workflow is:

1. Scan some or all of a Google Drive account.
2. Show a summary of storage usage and categorized file/folder issues.
3. Let the user review results.
4. Let the user move, delete, bulk delete, or restore files.

Important operating characteristics:

- Users can scan an entire Google Drive account or only selected folders, depending on plan.
- Filerev automatically categorizes files inside the app without modifying Google Drive during the scan.
- Actions such as move, delete, or restore happen only when the user initiates them.
- Filerev claims to retrieve only a minimal amount of metadata and not download user files.
- Deletions go to Google Drive Trash rather than immediately permanently deleting files.
- Files in Trash can generally be restored within 30 days.
- Filerev also offers a one-click bulk restore of all files in Google Drive Trash.

## What Filerev Analyzes

Filerev exposes file/folder information through summary pages, categories, and filters.

It can analyze:

- My Drive
- Shared with Me / shared files
- Hidden files
- Synced computer files
- Shared Drives
- Specific folders only

It groups or surfaces files by:

- Duplicate status
- File type and extension
- File owner
- Creation date / file age
- Storage used
- Folder path
- Shared/not owned by me
- Temporary file status
- Hidden/orphaned status
- Empty file status
- Trash status

## Key Concepts Used by the App

### Duplicate Files

- A duplicate file is defined as a file whose content is 100% identical to another file.
- Duplicate files may differ in file name, folder, owner, or creation date.
- Filerev includes a "same folder duplicates" view for identical files located in the exact same folder.

### Hidden Files

- Hidden files are described as orphaned Google Drive files that are no longer in any folder.
- A common cause is when a parent folder is deleted but the file itself is not.
- These files can still consume storage.
- Filerev can surface them and either delete them or move them back into a folder.

### Empty Files

- Filerev identifies empty files that have no content.
- The website claims its empty-file view excludes cases where a previous file version still contains data, making cleanup safer.

### Temporary Files

- Temporary files are files created by apps or operating systems for intermediate work, such as `.tmp`, `.old`, or similar artifacts.
- These may be unintentionally synced into Google Drive and can usually be removed.

### Old Files

- Old files are files older than a chosen date threshold.
- The default old-file view is described as files older than one year, with filters to adjust the threshold.

## Main Tools and Capabilities

### Storage Analyzer

Purpose:

- Show high-level storage usage across Google Drive, Gmail, Google Photos, and uncategorized/third-party-app areas.
- Show storage used by folders.
- Show storage used by categories such as duplicates, hidden files, old files, temporary files, and trash.
- Show storage used by file types.

Notable details:

- Helps users drill from a high-level summary into specific folders, file types, and categories.

### Folder Size Analyzer

Purpose:

- Calculate folder sizes in Google Drive.
- Show the largest folders first.
- Let users browse into folders to see which subfolders and files consume the most space.

Notable details:

- Can scan only a specific folder or set of folders instead of an entire account.
- Intended to solve the fact that Google Drive does not natively show folder sizes well.

### Duplicate File Finder

Purpose:

- Find all duplicate files in Google Drive.
- Show how much storage duplicates consume.
- Let users review details for each duplicate.

Notable details:

- Duplicate detection is based on 100% identical content.
- Users can manually select duplicates, select oldest/newest on the page, or bulk delete.
- Filters can narrow duplicates by folder, owner, date, file type, or storage used.

### Duplicate Photo Finder

Purpose:

- Focus the duplicate-file workflow on photo/image formats.
- Show duplicate photos, compare them, and bulk delete them.

Notable details:

- The app describes this as a filtered view of duplicate files for image formats.

### Bulk File Deleter

Purpose:

- Mass delete files with one click.
- Delete all files in a category or a filtered subset.

Notable details:

- Can bulk delete duplicates, hidden files, empty files, large files, old files, and more.
- Can be combined with filters to delete only a subset.
- Moves deleted files to Trash.

### Clear Google Drive

Purpose:

- Remove all files from Google Drive with a one-click bulk-delete workflow.

Notable details:

- Filerev says it performs a comprehensive scan first so users can review what will be affected.
- Hidden files are included in the scan so they are not overlooked.
- Deletion sends files to Trash, not immediate permanent deletion.

### Restore Files in Google Drive Trash

Purpose:

- Restore every file in Google Drive Trash with one click.

Notable details:

- Restores files to their original locations.
- Filerev claims it restores items in the correct order so nested folder structures are preserved.
- This is positioned as especially useful when many files or folders are in Trash.

### Google Drive Organizer

Purpose:

- Provide a central organization workflow rather than a single-purpose tool.
- Categorize files and folders, expose clutter, and help users move or remove items.

Notable details:

- Surfaces categories such as duplicates, large files, hidden files, empty files, empty folders, old files, temporary files, and files by extension.
- Lets users move files as well as delete them.

### File Type Sorter

Purpose:

- Group files into high-level file-type categories and then into specific mime types or extensions.

High-level groups mentioned on the site:

- Documents
- Photos & Images
- Audio
- Video
- Archive
- Other

Notable details:

- Users can drill into types such as PDF, Google Docs, Google Sheets, Microsoft Word, etc.
- Filters can be combined with file-type views.
- Users can move or bulk delete files of a specific type.

### Hidden File Finder

Purpose:

- Find hidden/orphaned files that are not visible through normal folder browsing.

Notable details:

- Shows how much storage hidden files use.
- Users can delete them or restore them by moving them back into folders.

### Empty File Remover

Purpose:

- Find and remove empty files.

Notable details:

- Can scan entire accounts, specific folders, or Shared Drives.
- Shows owner, location, and other details for each empty file.
- Supports manual deletion or one-click bulk deletion.

### Old File Manager

Purpose:

- Find old files and either archive them by moving them or bulk delete them.

Notable details:

- Users can filter by age threshold, owner, folder, and file type.
- Website positioning also emphasizes compliance and retention-policy cleanup.

### Shared File Viewer

Purpose:

- Manage files shared with the user or files not owned by the user.

Notable details:

- Shows files in a "Not Owned by Me" category.
- Helps identify duplicate shared files.
- Supports filtering by owner, extension, storage used, date, and folder.
- Supports deleting or bulk deleting shared files from the user's Drive view.

### Shared Drive Organizer

Purpose:

- Apply Filerev's categorization and cleanup workflow to Google Shared Drives.

Notable details:

- Supports duplicate detection, folder-size browsing, empty-file/empty-folder views, old files, temporary files, and file-type views within Shared Drives.
- Supports scanning whole Shared Drives or selected folders within them.

### Temporary File Cleaner

Purpose:

- Find temporary files unintentionally synced into Google Drive and remove them.

Notable details:

- Positioned as cleanup for junk left by desktop apps, downloads, or interrupted processes.

## Common Filters and Review Controls

Across the site, Filerev repeatedly describes filters for narrowing results. Common filters include:

- File creation date
- File owner
- Storage used
- Folder path / location
- File type or extension

This matters because many Filerev actions are not only category-wide actions; users can usually filter down to a subset and then bulk delete or review just that subset.

## Locations and Scan Scope

The site describes support for scanning:

- My Drive
- Shared with Me
- Hidden files
- Synced computers
- Shared Drives
- Specific folders instead of an entire account

This means Filerev is not only a "scan all of Google Drive" tool; it can also target narrower scopes for review.

## Safety and Security Positioning

Filerev's website repeatedly emphasizes:

- The app does not modify files during scanning.
- It retrieves minimal metadata rather than downloading files.
- Transfers use secure SSL connections.
- Stored account information is encrypted.
- The service undergoes regular third-party security audits.
- The company says it does not use customer information for anything other than providing the service.
- Deletion actions move files to Google Drive Trash first.

## Product Constraints and Limits

### Plan Summary

Free:

- 1 scan per month
- Up to 1 million files scanned per month
- 500 moves/deletions per month
- Can scan My Drive

Basic:

- 3 scans per month
- Up to 1 million files scanned per month
- 10,000 moves/deletions per month
- Includes Bulk Delete
- Includes Filters
- Can scan My Drive, synced computers, Shared with Me, and hidden files

Standard:

- 5 scans per month
- Up to 2 million files scanned per month
- 100,000 moves/deletions per month
- Includes Bulk Delete
- Includes Filters
- Includes Select Folders to Scan
- Includes Storage Analyzer
- Includes Empty Folder views

Premium:

- Unlimited scans per month
- Up to 5 million files scanned per month
- 500,000 moves/deletions per month
- Includes Bulk Delete
- Includes Filters
- Includes Select Folders to Scan
- Includes Storage Analyzer
- Includes Empty Folder views
- Includes Shared Drive scanning

### Plan-Gated Features Mentioned Explicitly

- Bulk Delete is paid-only.
- Filters are paid-only.
- Select Folders to Scan starts at Standard.
- Storage Analyzer starts at Standard.
- Empty Folder views start at Standard.
- Shared Drive scanning is Premium-only.

## Additional Notes Useful for Future LLMs

- Filerev positions itself as a Google Drive cleanup, storage analysis, and organization tool rather than a generic cloud storage platform.
- The site's repeated core promise is visibility plus action: surface clutter, show storage usage, then let the user clean it up safely.
- The app appears optimized for accounts with very large numbers of files, including millions of files.
- Many pages emphasize that Filerev is faster than manually downloading or locally scanning all files.
- The site strongly differentiates between scanning/review and user-initiated modification.
- Shared-drive support exists, but it is not on every plan.
- The site mentions an Android app, but that is not central to understanding Filerev's capabilities.

## What Was Intentionally Removed From the Original Website Dump

The following were intentionally excluded because they are not useful for teaching a future LLM what Filerev does:

- Crawl metadata and sitemap boilerplate
- Repeated page structure outlines
- Image links and placeholders
- Marketing CTAs
- Testimonials
- Founder biography
- Contact page details
- Coupon page
- Affiliate program and affiliate terms
- Terms of service
- Privacy policy details beyond the product-relevant security summary
- Repetitive consumer-facing FAQs that mainly explain Google Drive rather than Filerev
- Duplicate homepage copy and "Untitled Copy" content

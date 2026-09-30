# Lecturer Timetable Generator — Version 1

A self-contained generator for Francis's semester timetables. Runs as a local HTML file or on GitHub Pages. No Google Sheet, account login, npm install or server is needed to use the generator.

## Start on your computer

1. Unzip this package.
2. Open `index.html` in Chrome, Edge or Safari.
3. The first timetable is empty. Use **Load sample** to try the illustrative entries, or enter your actual activities.
4. In **Settings**, check your lecturer details, semester period and timetable days/hours. An institution logo can be uploaded; no crest is included in the package.
5. Add activities. Click a coloured block or choose **Activity list → Edit** to revise an entry.
6. Save a JSON backup when you finish.

Theme settings can be changed before entering any timetable activities. Both light and dark generator appearances are available. Exported semester pages use a light layout for viewing and printing.

## Outputs

| Button | Result |
| --- | --- |
| Save JSON backup | An editable backup of ALL semesters, profile settings, logo and every activity, including private entries. |
| Load JSON | Restores the backup, replacing the generator's existing working data after confirmation. |
| Export HTML | A standalone, read-only semester timetable named after the semester code, for example `A261.html`. |
| Preview timetable | Opens the current shared timetable in a new tab. |
| Print / Save PDF | Opens a print-ready shared timetable. Select Save as PDF in the browser print dialog. |
| Moodle code | A self-contained, inline-styled timetable table for Moodle's HTML source editor. |
| Moodle link button | A Moodle button linking to the published semester page. Set the publishing address first. |

Only activities marked **Include in shared timetable** appear in semester HTML, print/PDF and Moodle outputs. Lecturer details and the timetable note appear in those outputs as well. Personal entries are unchecked by default when that activity type is chosen. JSON always contains every activity.

The sample contains illustrative course codes, rooms and hours. It is NOT a confirmed teaching timetable. The generator starts empty; the sample does not load automatically.

## Publish the generator on GitHub Pages

Use your existing `lecturer-timetable` repository if you already created one. Keep previous files you still need; this package does not require deleting your repository.

1. Sign into GitHub on your desktop and open the repository. If it does not exist, create a public repository named `lecturer-timetable`.
2. Select **Add file → Upload files**.
3. Upload `index.html` and `README.md` from the unzipped folder into the repository root. Do not upload the ZIP itself as the website. Do not put `index.html` inside an extra parent folder.
4. Save/commit the upload to your publishing branch (usually `main`; use the branch name shown in your repository).
5. Open **Settings → Pages**.
6. Under **Build and deployment**, choose **Deploy from a branch**. Select your publishing branch and **/(root)**, then save.
7. Wait for GitHub Pages to finish deployment. Open the URL shown in Pages settings.

With the repository name and username in your reference image, the expected generator address is:

`https://francischuah.github.io/lecturer-timetable/`

This package has not been uploaded to your GitHub account. The address is proposed, not verified as a deployed version of this generator.

## Publish a timetable for a semester

1. Finish semester A261 in the generator and save a JSON backup locally.
2. Click **Export HTML**. This downloads `A261.html`.
3. In GitHub, create the `semesters` folder if needed: select **Add file → Create new file**, enter `semesters/README.md`, write a short description and commit. You only need to do this once. Alternatively, upload the `semesters` folder supplied in this package.
4. Open the repository's `semesters` folder, select **Add file → Upload files** and upload `A261.html` there. Commit the change.
5. After the deployment finishes, your semester page will be at:

`https://francischuah.github.io/lecturer-timetable/semesters/A261.html`

6. In the generator's **Settings → Publish this semester**, enter the GENERATOR address (ending with `/lecturer-timetable/`) and save it. You can then copy the semester link or generate a Moodle link button.

Exporting a file or copying the prepared link does not upload or publish it. The link only works after the exported semester file is committed to GitHub and deployed. Keep filenames and semester codes consistent: `A261.html` and `a261.html` are different paths.

## Revise a published timetable

1. Open the generator; load your JSON backup if the timetable is not already available.
2. Select the semester, revise the activities, and save a fresh JSON backup.
3. Export the HTML again.
4. Upload the revised HTML into `semesters` using the SAME filename, replacing its previous version.
5. After deployment, students can continue using the same semester link. Refresh the page if a browser shows an older version.

Do not rename or remove previous semester files if you want their links to remain available. The Moodle link button opens the latest version at that address. A pasted Moodle timetable is a snapshot; paste fresh code when the timetable changes.

## Add the next semester

In **Settings**, choose **Add semester**, enter a unique code such as A262, set its period and enter its activities. Switch semesters using the dropdown at the top. Export its page as `A262.html` and upload it into the same `semesters` folder. JSON backups contain every semester in the generator.

Deleting a semester from the generator does not remove an already published HTML file from GitHub.

## PDF and phone viewing

The PDF button uses the browser's print system, rather than a separate PDF service. Select **Save as PDF**, A4, landscape. Turn on background graphics for coloured blocks, and turn off browser headers/footers if desired. The timetable is followed by an activity-detail page. Dense schedules with many overlapping activities can use extra pages.

On phones, the timetable scrolls horizontally so actual start/end times remain proportional. The full activity details underneath the shared timetable provide readable titles and venues even for very short time blocks. The generator's input form appears beneath its workspace on narrow screens.

If Preview or PDF does not open, allow pop-ups for the generator. Safari/iOS may present the system print/share workflow; desktop Chrome or Edge is the most straightforward route for producing PDFs.

## Saving and privacy

The generator attempts to save its working state in the current browser automatically. Local browser saving may be unavailable for some local-file or private-browsing configurations, and clearing site data can remove it. JSON backup files are the portable editing record. Moving between devices is manual: transfer and load the JSON file.

Your exported HTML is self-contained and continues working if the generator is updated. It has no editing controls, database connection or dependency on your JSON file. Visiting the public generator gives each visitor their own browser workspace; they do not modify your saved timetable or the published semester HTML through it.

Keep JSON backups containing personal entries on your computer/OneDrive. Upload only the timetable HTML you intend to share to a public repository. The generator's default lecturer profile is included in its source; change it if distributing the generator to other lecturers.

Activities cannot cross midnight. Enter overnight activities as separate entries and expand the visible hours when needed. Existing activities must fit the selected days and hours, so settings cannot silently hide them. Overlapping activities occupy separate lanes within their day.

## Package contents

- `index.html`: the complete generator; no other code files required.
- `README.md`: these setup and usage instructions.
- `Sample_Timetable_Backup.json`: an illustrative backup to test loading (contains a personal sample entry).
- `semesters/A261-example.html`: an illustrative shared output, with the private sample omitted.
- `semesters/README.md`: explains where your real exported semester HTML files belong.

## Validation

Checked in desktop Chromium: adding and editing activities; invalid time rejection; overlap lanes; public/private filtering; JSON download and restore; semester creation and switching; dark theme; safe text escaping and backup validation; mobile page overflow; standalone HTML and printed PDF generation.

Browser-specific print dialogs and GitHub account deployment still require checking on your computer after upload.

Official GitHub instructions:
- https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository

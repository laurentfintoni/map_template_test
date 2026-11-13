# Storymap template (map track)

A scrolling story on a map. Each chapter of the story is one row in a table. You only need the GitHub website and a spreadsheet programme: no Google account, no API key, no code.

The template opens with a sample story about four monuments in Ravenna. Replace it with your own.

## Make your own in four steps

1. **Copy the template.** Click the green **Use this template** button, then **Create a new repository**. Give it a short name without spaces. Keep it **Public**.
2. **Publish it.** In your new repository: **Settings → Pages**. Under *Branch* choose **main**, then **Save**. After one or two minutes your map is live at `https://YOUR-USERNAME.github.io/YOUR-REPO/`.
3. **Edit the settings.** Open `csv/Options.csv`, click the pencil, and change the title, subtitle, author names and repository link. Only edit the middle column (`Customize`). Click **Commit changes**.
4. **Add your chapters.** Replace the sample rows in `csv/Chapters.csv` with your own (see below). Commit, wait a minute, reload your map.

## Editing the chapters

`csv/Chapters.csv` is your data. One row is one chapter of the story, shown in order from top to bottom. Aim for 10–15 chapters.

The safest way to edit it:

1. Open `csv/Chapters.csv` on GitHub and click the download button.
2. Open it in a spreadsheet programme (LibreOffice Calc, Excel, Google Sheets).
3. Edit, then save or export as **CSV, UTF-8**, with the same file name: `Chapters.csv`.
4. On GitHub, open the `csv` folder, then **Add file → Upload files**, drop the file in, and **Commit changes**. It replaces the old one.

Small corrections can be made directly on GitHub with the pencil.

**Do not rename the columns or the files.** The map finds its data by these exact names.

### Columns the map uses

| Column | What to write |
|---|---|
| `Chapter` | The chapter title |
| `Media Link` | An image: either a web address ending in `.jpg` or `.png`, or a file you uploaded to the `media` folder, written as `media/my-image.jpg`. Leave blank for no image |
| `Media Credit` | Who made the image, where it comes from, and its licence |
| `Media Credit Link` | Web address of the image source |
| `Description` | The text of the chapter |
| `Zoom` | How close the map zooms: 13 is a whole town, 17 is a single building |
| `Marker` | `Numbered` (automatic), a number or letter of your choice, `Plain`, or `Hidden` |
| `Marker Color` | `blue`, `red`, `green`, `orange`, `purple`, `black` and others |
| `Location` | The name of the place, for your own reference |
| `Latitude`, `Longitude` | The coordinates of the place, as decimal numbers with a point: `44.420556` and `12.196389` |
| `Overlay`, `Overlay Transparency`, `GeoJSON Overlay`, `GeoJSON Feature Properties` | Optional and advanced: leave blank |

### Columns for your metadata

The map ignores these columns, but your project needs them. They make this file your metadata table as well as your story. You can add more columns of your own.

| Column | What to write |
|---|---|
| `date` | The date or period of the object or place |
| `wikidata` | The Wikidata address of the place or object, for example `http://www.wikidata.org/entity/Q721817` |
| `source` | Where your information comes from |
| `rights` | The licence or rights statement for the image and text |

## Finding coordinates

- **From Wikidata.** If your place has a Wikidata page, look for the statement *coordinate location*. In OpenRefine, after reconciling your place names with Wikidata, use **Edit column → Add columns from reconciled values** and choose *coordinate location*. Then split the result into two columns, latitude and longitude.
- **By hand.** On [openstreetmap.org](https://www.openstreetmap.org), right-click the place and choose **Show address**. The two numbers shown are latitude and longitude, in that order.

## If something goes wrong

| What you see | What to check |
|---|---|
| A message saying the map could not read `csv/Options.csv` | Both files must be inside the `csv` folder and be called exactly `Options.csv` and `Chapters.csv` |
| The page loads but the map is grey or in the sea | A latitude or longitude is missing, swapped, or written with a comma instead of a point |
| Text shows strange characters instead of accented letters | Save the file again as CSV with **UTF-8** encoding |
| An image does not appear | The address in `Media Link` must end in `.jpg`, `.jpeg`, `.png` or `.gif`. For your own files, check the name matches exactly, including capital letters |
| Your changes do not appear | Wait two minutes, then reload the page while holding Shift. Check for a green tick next to your last commit |
| A chapter is missing or columns look shifted | A row has too many or too few columns. Open the file in a spreadsheet and check the row |

## Optional: a different background map

The template uses the standard OpenStreetMap background, which needs no registration. If you prefer a lighter background (CARTO Positron):

1. Get your own free key at <https://carto.com/basemaps/apikey/>.
2. In `csv/Options.csv`, set `Basemap Tiles` to `CartoDB.Positron`.
3. Paste your key in the `Basemap Tiles API Key` row.

Use your own key, not someone else's. If the key stops working, the background shows "API KEY REQUIRED": set `Basemap Tiles` back to `OpenStreetMap.Mapnik` and clear the key.

## Credits and licence

This template is adapted from [Leaflet Storymaps with Google Sheets](https://github.com/HandsOnDataViz/leaflet-storymaps-with-google-sheets) by Jack Dougherty and Ilya Ilyankou, described in [*Hands-On Data Visualization*](https://handsondataviz.org/leaflet-storymaps-with-google-sheets.html). The code is under the MIT licence (see `LICENSE`). Map data © OpenStreetMap contributors. Sample images are from Wikimedia Commons, credited in each chapter.

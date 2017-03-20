# Tracker Killer
This was built for experimentation purposes with the goal of inspecting how anime tracking sites deal
with users with ludicrously large libraries.

It is beneficial for testing how well these sites cope with the following:
- Initial library page load time
- Library API request serialisation time
- Library API request download size

## Results
### Anime
<table>
  <tr>
    <th rowspan="2">Service</th>
    <th rowspan="2">Library Size</th>
    <th rowspan="2">Anime Loaded</th>
    <th colspan="2">Page Load Time (seconds)</th>
    <th colspan="4">Network (seconds)</th>
    <th colspan="3">API</th>
  </tr>
  <tr>
    <td>Initial</td>
    <td>Refresh</td>
    <td>Loading</td>
    <td>Render</td>
    <td>Script</td>
    <td>Paint</td>
    <td>Response Time (seconds)</td>
    <td>Size (MB)</td>
    <td>Type</td>
  </tr>
  <tr align="right">
    <td>AniDB</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr align="right">
    <td>AniList</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr align="right">
    <td>AnimePlanet</td>
    <td colspan="11" align="center">No API Available</td>
  </tr>
  <tr align="right">
    <td>Annict</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr align="right">
    <td>Kitsu</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr align="right">
    <td>MyAnimeList (Classic)</td>
    <td rowspan="2">12603</td>
    <td>12603</td>
    <td>42.8</td>
    <td>42.5</td>
    <td>2.3</td>
    <td>22.8</td>
    <td>11.2</td>
    <td>0.7</td>
    <td rowspan="2">5.2</td>
    <td rowspan="2">10.1</td>
    <td rowspan="2">XML</td>
  </tr>
  <tr align="right">
    <td>MyAnimeList (Modern)</td>
    <td>300</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</table>

### Manga
<table>
  <tr>
    <th rowspan="2">Service</th>
    <th rowspan="2">Library Size</th>
    <th rowspan="2">Manga Loaded</th>
    <th colspan="2">Page Load Time (seconds)</th>
    <th colspan="4">Network (seconds)</th>
    <th colspan="3">API</th>
  </tr>
  <tr>
    <td>Initial</td>
    <td>Refresh</td>
    <td>Loading</td>
    <td>Render</td>
    <td>Script</td>
    <td>Paint</td>
    <td>Response Time (seconds)</td>
    <td>Size (MB)</td>
    <td>Type</td>
  </tr>
  <tr align="right">
    <td>AniDB</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr align="right">
    <td>AniList</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr align="right">
    <td>AnimePlanet</td>
    <td colspan="11" align="center">No API Available</td>
  </tr>
  <tr align="right">
    <td>Annict</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr align="right">
    <td>Kitsu</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr align="right">
    <td>MyAnimeList (Classic)</td>
    <td rowspan="2">42579</td>
    <td colspan="7" align="center">Page fails to load - 500</td>
    <td rowspan="2" colspan="2" align="center">API 500s</td>
    <td rowspan="2">XML</td>
  </tr>
  <tr align="right">
    <td>MyAnimeList (Modern)*</td>
    <td>300</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</table>

\* Page becomes unresponsive after loading up to 20700 manga, consuming ~20% CPU and ~4 GB of RAM on Chrome and Edge

## Usage
**<p align="center">⚠️️ This will completely overwrite all library data on these services without warning ⚠️️</p>**

### Requirements
- [git](https://git-scm.com/) 2.0.0 or newer
- [node.js](https://nodejs.org) 7.0.0 or newer
- npm 3.10.8 or newer (installed with node.js)
  - run `npm install npm -g` to update to latest version

### Setup
1. Download source code:

    ```bash
    git clone https://github.com/wopian/tracker-killer.git
    cd tracker-killer
    ```
2. Install dependencies:

    ```bash
    npm i
    ```

3. Copy `env.template.js` to `env.js`
4. Edit `env.js` and modify the required account information

### Running
Enter the command below and use the arrow keys to select the service to test with.
```bash
npm start
```

### Reporting
WIP
```bash
./node_modules/.bin/phantomas https://myanimelist.net --har=./report/myanimelist/har --film-strip --film-strip=./report/myanimelist/.filmstrip --film-strip-prefix=''
```

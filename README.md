# WOIM (Webport)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)]()
[![WebAssembly](https://img.shields.io/badge/WebAssembly-654FF0?style=for-the-badge&logo=webassembly&logoColor=white)]() <br><br>
ALL CREDIT GOES TOWARDS DOGSPAWN FOR THIS AMAZING GAME :)<br>
Check out Dogspawn here! : https://dogspawn.net/ <br>
WOIM: https://store.steampowered.com/app/4272020/WOIM/ <br><br>
For game site dev and such, just use woim.html and it should load up fine, do not fork this repo, **LFS WILL fail**. <br><br>
No crediting required, as long as you use woim.html directly to load the game. <br>
For users with internet wanting a downloadable copy, download woim.html and double click to run it. More details below. <br><br>
A webport of the Woim demo, rebuilt and compiled to run directly inside modern desktop web browsers. 
<br><br>
The original desktop build of Woim relies on native system executables and deep Steamworks integrations. This project extracts the compiled assets, strips out the platform-specific dependencies, bypasses background Steam initialization hooks, and repacks the core project files into a standalone WebAssembly format. 
<br><br>
The live version is hosted via GitHub Pages at: https://katsugachi.github.io/Woim-DEMO-Webport/ <br><br>
Download woim.html: https://github.com/Katsugachi/Woim-DEMO-Webport/releases/download/random/woim.html

## Local Installation and Execution

### Prerequisites
Ensure you have Python installed on your system to quickly deploy the server wrapper.

### Running the Project

1. Clone or download this repository to your local drive.
2. Open your terminal or PowerShell window inside the root directory where `index.html` is located.
   * On Windows, you can hold `Shift`, right-click an empty space inside the folder, and select **Open PowerShell window here**.
3. Spin up a lightweight Python HTTP server by running the following command:
   ```bash
   python -m http.server 4050
   ```
   *(If your system defaults to Python 3 explicitly, use `python3 -m http.server 4050` instead).*
4. Once the terminal indicates that the server is active, open your web browser and navigate to:
   ```text
   http://localhost:4050
   ```

## Development and Stack Data
* **Engine Environment:** Godot 4.6.2 Stable (Compatibility Renderer / WebGL 2.0 architecture)
* **Extraction Utility:** GDRE Tools Framework

---
*Disclaimer: This is a non-commercial, community-driven deployment intended strictly for portability and accessibility research. All original audio assets, visual artwork, and source logic belong entirely to the respective game developers.*

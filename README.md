# Woim (Webport)
For game site dev and such, just use woim.html and it should load up fine, do not fork this repo, **LFS WILL fail**. <br><br>
No crediting required, as long as you use woim.html directly to load the game. <br>
For users with internet wanting a downloadable copy, download woim.html and double click to run it. More details below. <br><br>
A webport of the Woim demo, rebuilt and compiled to run directly inside modern desktop web browsers. 
<br><br>
The original desktop build of Woim relies on native system executables and deep Steamworks integrations. This project extracts the compiled assets, strips out the platform-specific dependencies, bypasses background Steam initialization hooks, and repacks the core project files into a standalone WebAssembly format. 
<br><br>
The live version is hosted via GitHub Pages at: https://katsugachi.github.io/Woim-DEMO-Webport/

## Technical Architecture
Converting a native Godot 4 project to run smoothly within a sandboxed browser environment requires several structural adjustments to the original codebase:
<br>
* **Steamworks Bypass:** The native `GodotSteam` GDExtension asset cannot run on web architectures. The background `steamworks.gd` autoload script has been disabled, and interface scripts (such as `main_menu.gd`) were patched with placeholder code to safely ignore achievement and profile tracking updates.
* **Single-Thread Optimization:** The export uses a single-threaded configuration. This removes the strict requirement for cross-origin isolation headers (SharedArrayBuffer) on the hosting server, ensuring the game runs out of the box on standard web hosts like GitHub Pages.
* **Storage Re-routing:** Local save data paths (`user://`) are automatically routed through the browser's IndexedDB engine rather than writing directly to the host operating system's local storage disk.

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

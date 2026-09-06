# tangle-bureau 🎯


## Basic Details
### Team Name: KNR


### Team Members
- Team Lead: [Raihan] - VISWAJYOTHI COLLEGE OF ENGINEERING AND TECHNOLOGY
- Member 2: [Nivin] - VISWAJYOTHI COLLEGE OF ENGINEERING AND TECHNOLOGY

### Project Description
A web tool where you upload a photo of tangled wires or cables, and it runs real edge-detection image processing (not fake) to measure how genuinely knotted it is — factoring in both sharpness of edges and how compactly the wire is balled up. It then issues you a mock official "Tangle Severity Certificate" with a class rating (I–V), estimated crossing points, and untangling time, which you can print.

### The Problem (that doesn't exist)
We're solving the deeply unaddressed crisis of not knowing, with scientific certainty, exactly how tangled your earphones are before you attempt to untangle them — and giving you an official government-style certificate about it, because your suffering deserves documentation.

### The Solution (that nobody asked for)
Upload a photo of your tangled wires 📸 — real pixel-level edge-detection math scans it for chaos and clumpiness, no gimmicks. Out pops an official, printable Certificate of Tangle Severity, complete with a case number, Class rating (I–V), and court-ordered untangling time. 🪢⚖️

## Technical Details
### Technologies/Components Used
For Software:
- HTML, CSS, JavaScript
- none-plain vanilla, no framework
- None — the Sobel edge-detection algorithm was hand-coded from scratch using the native Canvas API (no OpenCV, no ML libraries)
- Browser Canvas API (getImageData/pixel manipulation), FileReader API (image upload), window.print() (certificate printing)

For Hardware:
- Image upload & preview module (FileReader API)
Grayscale conversion engine
Sobel edge-detection engine (custom convolution, hand-coded)
Mask dilation module (merges thin wire outlines into a solid shape)
Compactness calculator (bounding-box fill ratio — the anti-false-positive fix)
Crossing-estimation module (sliding-window density scan)
Severity scoring engine (combines edge density × compactness)
Certificate generator UI (case number, class rating, verdict, print view)
Reset/re-upload controller
- Runs entirely client-side in the browser — no server, no backend, no internet needed after loading
Input: any JPG/PNG photo via file upload
Image auto-downscaled to max 220px for fast real-time processing
Output: Tangle Severity Score (0–100), Class rating (I–V), estimated crossing count, estimated untangling time
Printable certificate via native browser print
Single self-contained .html file — no installation
- Any modern web browser (Chrome/Edge/Firefox) — that's it
A text editor (only needed if judges want to see/edit the code, e.g. VS Code or Notepad)
No installs, no API keys, no internet dependency, no build steps

### Implementation
For Software:
# Installation
# 1. Clone or download the project
git clone <your-repo-url>
cd tangle-assessment-bureau

# 2. That's it — no dependencies to install
# (pure HTML/CSS/JS, zero npm packages, zero build step)

# 3. Run it — just open the file in any browser
open tangle-bureau.html        # macOS
start tangle-bureau.html       # Windows
xdg-open tangle-bureau.html    # Linux

# Optional: serve it locally instead of double-clicking
python3 -m http.server 8000
# then visit http://localhost:8000/tangle-bureau.html

# Run
# Option 1 — just double-click the file (simplest, no commands needed)
open tangle-bureau.html        # macOS
start tangle-bureau.html       # Windows
xdg-open tangle-bureau.html    # Linux

# Option 2 — run via a local server (if double-click doesn't work in your browser)
python3 -m http.server 8000
# then open: http://localhost:8000/tangle-bureau.html

# Option 3 — using Node instead of Python
npx serve .
# then open the localhost link it prints

### Project Documentation
For Software:Project Documentation
National Cable Tangle Assessment Bureau 🪢⚖️
Overview

A web-based satirical tool that applies real computer vision (Sobel edge detection, hand-coded from scratch) to photos of tangled wires and cables, issuing an official-style "Certificate of Tangle Severity" — solving a problem nobody asked to have solved, with more rigor than it deserves.

Problem Statement

There is currently no scientific, standardized, or legally-adjacent way to measure exactly how tangled your earphones are before attempting to fix them. This project fills that gap.

Solution

Users upload a photo of their tangled wires. The app processes the image entirely in-browser using pixel-level edge detection to measure two things: how sharp/jagged the wire outlines are, and how tightly the wire is balled up (compactness). These are combined into a Tangle Severity Score, mapped to a Class rating, and presented as a printable certificate.

Features
Photo upload with live preview
Real-time client-side image analysis (no server, no internet needed after load)
Sobel edge-detection algorithm, implemented from scratch
Compactness-based accuracy correction (prevents false positives on single/untangled wires)
Estimated crossing-point count
Tangle Class rating system (Class I–V)
Estimated untangling time
Printable official certificate with case number and timestamp
"Upload New Photo" reset flow
Tech Stack
Layer	Technology
Structure	HTML5
Styling	CSS3
Logic	Vanilla JavaScript
Image processing	Canvas API (getImageData, pixel manipulation)
File handling	FileReader API
Output	window.print()
How It Works (Architecture)
Upload → image loaded via FileReader, drawn onto a downscaled canvas (max 220px) for performance
Grayscale conversion → standard luminance formula (0.299R + 0.587G + 0.114B)
Sobel edge detection → 3×3 convolution kernels detect sharp brightness changes (wire outlines)
Mask dilation → thickens thin edge lines into a solid wire-shaped mask
Compactness calculation → wire's filled area ÷ its bounding box area (distinguishes a single straight wire from a real knot)
Crossing estimation → sliding-window density scan flags overlapping-strand regions
Scoring → edge density × compactness factor → final 0–100 severity score
Certificate generation → score mapped to Class I–V, verdict text, time estimate, case number
Installation
bash
git clone <your-repo-url>
cd tangle-assessment-bureau
# no dependencies — nothing to install
Run
bash
open tangle-bureau.html   # or start / xdg-open depending on OS
Usage
Click the upload box, select a photo of tangled wires
Click "Submit for Official Assessment"
View your Tangle Severity Certificate
Use "Print Certificate" to print/save, or "Upload New Photo" to test another
Limitations
Crossing count is an estimate, not exact (true crossing-counting would require skeletonization)
Accuracy depends on photo lighting/contrast and background clutter
Tuned for close-up wire photos, not wide scenes
Future Scope
Skeletonization for exact crossing counts
Shareable certificate image export
Leaderboard of worst tangles
Mobile camera capture support

# Screenshots (Add at least 3)
<img width="960" height="482" alt="project inter face" src="https://github.com/user-attachments/assets/94081805-aa43-42eb-88ec-76a3590684fb" />

this is the interface of the website when opened

<img width="960" height="481" alt="project with uploaded photo" src="https://github.com/user-attachments/assets/9e139790-3f58-4d8d-b429-5fb899447da6" />

it shows how it looks after an photo is uploaded by the author

<img width="960" height="472" alt="final outcome given by our project" src="https://github.com/user-attachments/assets/6cf1afd3-33a0-4113-8818-7bbeb437510b" />

this the reslt or outcome after the uplopad of the photo shown in image as the analyser gives out the percentage of chance of tangle and how many minute do we need to untangle them.


# Diagrams
<img width="293" height="256" alt="Screenshot 2026-09-06 081440" src="https://github.com/user-attachments/assets/dc281415-7d8e-40c2-89e7-0885f3f56e77" />
<img width="461" height="355" alt="Screenshot 2026-09-06 081356" src="https://github.com/user-attachments/assets/def4eaa2-f37b-4f1f-9008-c278676eab4c" />

For Hardware:

# Schematic & Circuit
![Circuit](Add your circuit diagram here)
*Add caption explaining connections*

![Schematic](Add your schematic diagram here)
*Add caption explaining the schematic*

# Build Photos
![Components](Add photo of your components here)
*List out all components shown*

![Build](Add photos of build process here)
*Explain the build steps*

![Final](Add photo of final product here)
*Explain the final build*

### Project Demo
# Video

*Explain what the video demonstrates*

# Additional Demos
[Add any extra demo materials/links]

## Team Contributions
- [Nivin Nibu]: [Core building the website]
- [Raihan abdul rasheed A]: [idea and research]



---
Made with ❤️ at TinkerHub Useless Projects 

![Static Badge](https://img.shields.io/badge/TinkerHub-24?color=%23000000&link=https%3A%2F%2Fwww.tinkerhub.org%2F)
![Static Badge](https://img.shields.io/badge/UselessProjects--26-26?link=https%3A%2F%2Ftinkerhub.org%2Fevents%2F1M8ORET9A1%2Fuseless-projects-3.0)




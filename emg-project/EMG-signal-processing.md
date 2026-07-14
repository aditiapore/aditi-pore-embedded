
Claude finished the response
I am technical secretary


Thought for 2s
Thought for 2s
Good catch — thanks for the correction. Let me fix that in your README.


Edited 3 files, read a file
Edited 3 files, read a file
Fixed both mentions. Also worth double-checking your actual resume PDF and LinkedIn — if those still say "Secretary" instead of "Technical Secretary," you'll want that corrected there too so everything's consistent across your resume, LinkedIn, and GitHub.

Want me to update my memory so I have "Technical Secretary" right going forward, or was it already saved that way and this was just a one-off fix for the README?


Readme
Document · MD 
how do i upload readme


Charted dual pathways for README deployment strategies
Charted dual pathways for README deployment strategies
Here's how, depending on whether you already have a README in your repo or not.

If your repo already has a README.md (created automatically when you made the repo)
Go to your repo on github.com
Click on README.md in the file list to open it
Click the pencil/edit icon (top-right of the file view)
Select all existing text and delete it
Open the README.md file I created for you, copy all its content
Paste it into GitHub's editor
Scroll down to the "Commit changes" section
Add a short commit message like "Update README with projects and skills"
Click Commit changes
If you don't have a README yet, or want to upload the file directly instead of copy-pasting
Go to your repo
Click "Add file" → "Upload files"
Drag and drop the README.md file (download it from our conversation first if you haven't already)
Scroll down, add a commit message
Click Commit changes
⚠️ One catch with Option 2: if a README.md already exists in the repo, uploading a new one this way will ask you to confirm you want to replace the existing file — just confirm, and it'll overwrite correctly.

Quick tip
The copy-paste into the editor (Option 1) is usually easier for text files like README, since you can see and tweak the content directly in GitHub's browser editor before committing — no need to manage a local file at all.

Once it's up, your repo will show this README as the front page description anyone sees when they land on your GitHub — that's your resume link, project summaries, and skills all visible immediately without needing to click further in.

EMG_Circuit_detection (1).pdf
IEEE_Access_AI_Vision_for_Blind.pdf
KHN_Report.pdf
I have uploaded these three files


Orchestrated documentation strategy leveraging newly provided source materials
Orchestrated documentation strategy leveraging newly provided source materials
Perfect — I now have full detail from your EMG paper, KHN filter report, and the IEEE Access AI Vision paper. Let me build proper write-ups for your GitHub repo using this real content.


Ran 2 commands
Ran 2 commands
Now let me also draft a write-up for your published IEEE Access paper, and update the README to link all three properly.


Creating AI-Vision-Assistant.md write-up for the published IEEE paper
Creating AI-Vision-Assistant.md write-up for the published IEEE paper
Now updating the README to link all three properly, plus noting the IEEE publication status:


Edited 2 files, read a file
Edited 2 files, read a file
You now have four files ready to upload:

README.md — repo homepage, links to all three project write-ups
EMG-signal-processing.md
KHN-filter.md
AI-Vision-Assistant.md — now correctly flagged as a published IEEE Access 2025 paper, which is genuinely a strong credibility signal worth having front and center
To upload: go to your repo → "Add file" → "Upload files" → drag in all four (plus your resume PDF and the actual PDFs of these papers/reports if you want the source documents linkable too) → commit.

One thing worth deciding: do you want the actual PDF papers (the EMG paper, KHN report, IEEE Access paper) uploaded to the repo as well, so a recruiter can click through from the markdown summary straight to the full document? That's an easy addition — just say the word and I'll note where to link them from each .md file.


Readme
Document · MD 

Emg signal processing
Document · MD 

Khn filter
Document · MD 

Ai vision assistant
Document · MD 
the ieee paper is not yet published


Identified publication status error and revised documentation accordingly
Identified publication status error and revised documentation accordingly
Good catch — that's an important correction to make before this goes anywhere public. Let me fix it in both files.


Edited 2 files, read a file
Edited 2 files, read a file
Fixed both — now correctly says "submitted, under review" instead of published. This kind of accuracy actually matters more than it might seem: if an interviewer asks about it and the status doesn't match what's written, it can undercut trust in everything else on the resume. "Submitted, under review" is a completely respectable and honest status to list — it still shows serious research work without overclaiming.

Quick check on your actual resume PDF too — worth confirming it doesn't say "published" anywhere for this paper either, since we're now tightening up the GitHub version. Want me to check the resume text for that phrasing?


Readme
Document · MD 

Ai vision assistant
Document · MD 
i will make folders and add .md and also pdf for the projects


Devised practical guidance for organizing markdown and PDF project structure
Devised practical guidance for organizing markdown and PDF project structure
Sounds like a solid plan. A couple of quick pointers so it goes smoothly:

Suggested structure
aditi-pore-portfolio/
├── README.md
├── Aditi_Pore_Resume.pdf
├── emg-project/
│   ├── EMG-signal-processing.md
│   └── EMG_Circuit_detection.pdf
├── khn-filter/
│   ├── KHN-filter.md
│   └── KHN_Report.pdf
└── ai-vision-assistant/
    ├── AI-Vision-Assistant.md
    └── IEEE_Access_AI_Vision_for_Blind.pdf
Two things to update once you do this
1. README links — since the files are moving into folders, the README's relative links need updating to match:

[Seven-Stage Analog EMG Signal Processing Circuit](./emg-project/EMG-signal-processing.md)
[KHN State-Variable Audio Filter](./khn-filter/KHN-filter.md)
[AI Vision for Blind...](./ai-vision-assistant/AI-Vision-Assistant.md)
2. Link to the PDF from within each .md — add a line near the top of each write-up, e.g. in EMG-signal-processing.md:

📄 [Full Report (PDF)](./EMG_Circuit_detection.pdf)
This way anyone reading your summary can click straight through to the original document if they want full derivations, all figures, or the complete reference list.

Want me to regenerate the three .md files with the folder-relative paths and the PDF links already built in, so you can just upload everything as-is without manually editing paths yourself?

how to create a folder


Charted straightforward pathway for folder creation guidance
Charted straightforward pathway for folder creation guidance
On GitHub, you don't create an empty folder directly — folders exist only because a file is inside them. Here's how to do it in practice:

Method 1: While uploading files (easiest)
Go to your repo → "Add file" → "Upload files"
Drag in a file (e.g., EMG-signal-processing.md)
Before committing, there's a filename field — type the folder name as a prefix, like:
emg-project/EMG-signal-processing.md
GitHub automatically creates the emg-project/ folder the moment you commit that file
Method 2: Creating a new file directly on GitHub
Go to your repo → "Add file" → "Create new file"
In the filename box at the top, type the folder path followed by a filename:
khn-filter/KHN-filter.md
Add content, then commit — GitHub creates the khn-filter/ folder automatically
Uploading the PDF into the same folder
Once the folder exists (from step above), you can navigate into it:

Click into emg-project/ from your repo's file list
Click "Add file" → "Upload files" again
Now anything you upload here lands inside that folder automatically — no need to type the path again
Key thing to remember
GitHub has no concept of an "empty folder" — a folder only appears once it contains at least one file. So you can't create a blank folder first and add files later; the folder and its first file are created together in one commit.

Want me to regenerate the three .md files with folder-relative links already built in (pointing to the PDFs and to each other), so you can upload them straight into this structure without editing paths yourself?

explain steps to create folder


Architected step-by-step GitHub interface walkthrough for clarity
Architected step-by-step GitHub interface walkthrough for clarity
Here's the clearest step-by-step walkthrough, using the method most people find easiest — creating a new file with a folder path typed into the filename.

Steps to create a folder on GitHub
Step 1: Open your repository on github.com

Step 2: Click the "Add file" button (usually top-right of the file list)

Step 3: From the dropdown, click "Create new file"

Step 4: You'll see a text box at the top labeled something like "Name your file..."

Step 5: Type the folder name, followed by a forward slash /, followed by the file name. For example:

emg-project/EMG-signal-processing.md
The moment you type that /, GitHub visually shows it as a folder path — you'll see emg-project appear as a separate segment before the filename.

Step 6: Paste or type your file's content into the big text area below

Step 7: Scroll down to the "Commit new file" section

Step 8: Click the green "Commit new file" (or "Commit changes") button

Result: GitHub creates the emg-project folder automatically, with your .md file already inside it. If you go back to your repo's main page, you'll now see emg-project listed as a clickable folder.

To add the matching PDF into that same folder afterward
Step 1: From your repo's main page, click on the emg-project folder to open it

Step 2: Click "Add file" → "Upload files"

Step 3: Drag in your PDF (e.g., EMG_Circuit_detection.pdf)

Step 4: Scroll down, add a commit message, click "Commit changes"

Since you're already inside the emg-project folder when you upload, GitHub places the PDF there automatically — no need to type the folder path again.

Repeat this for your other two projects
Same steps, just swap in khn-filter/KHN-filter.md and ai-vision-assistant/AI-Vision-Assistant.md respectively.

Want me to regenerate the three .md files now with the folder-relative PDF links already written in, so they're ready to paste in as soon as you create each folder?







Claude is AI and can make mistakes. Please double-check responses.


Emg signal processing · MD
Seven-Stage Analog EMG Signal Processing Circuit
Co-authors: Pranshu Sabat, Aditi Pore, Sajal Patil — Dept. of Electronics and Telecommunication Engineering, COEP Technological University Tools: TL071 Op-Amps, Proteus (KiCad schematic), RIGOL Digital Storage Oscilloscope Domain: Biomedical signal processing, prosthetic control

Overview
A fully analog, microcontroller-free signal chain that takes weak surface EMG (sEMG) signals (50 µV – 5 mV at the skin) and conditions them into a clean 0–5 V DC envelope suitable for direct prosthetic motor control. Built entirely from TL071 JFET-input op-amps, powered from a dual ±9 V battery supply for a floating, mains-isolated system.

Why this is hard
sEMG signals present three core challenges: extremely low amplitude (requiring 1,000–10,000× gain), large common-mode interference from 50 Hz mains coupling, and low-frequency motion artefacts below 20 Hz. A usable front-end needs high gain, high CMRR (≥80 dB), and a well-defined 10–500 Hz passband — all without introducing offset or instability.

Signal Chain (7 Stages)
Instrumentation Amplifier — 3-op-amp topology, gain = 201 V/V, high input impedance, strong common-mode rejection
High-Pass Filter — removes DC offset and motion artefacts (target 16 Hz, measured 29.94 Hz)
Low-Pass Filter — limits bandwidth to reject high-frequency noise (target 480 Hz, measured 431 Hz)
Twin-T Notch Filter — rejects 50 Hz power-line interference specific to Indian mains supply
Second Gain Stage — restores signal level after filtering losses, gain = 16 V/V
Precision Full-Wave Rectifier — uses diodes inside the op-amp feedback loop to eliminate the ~0.6 V diode dead-band at millivolt signal levels
Envelope Detector — RC low-pass (τ ≈ 1s) smooths the rectified signal into a proportional DC envelope
Measured Results
Stage	Target	Measured
INA Gain	201 V/V	201 V/V
HPF cutoff	16 Hz	29.94 Hz
LPF cutoff	480 Hz	431 Hz
Notch frequency	50 Hz	50 Hz
Overall gain	—	≈10,000 V/V
CMRR	≥80 dB	>80 dB
Envelope output	0–5 V	≈4.92 V (full excitation)
Small deviations in cutoff frequencies are attributable to standard ±5% component tolerances and remain within acceptable ranges recommended in EMG acquisition literature.

Validation
Each stage was independently verified on a breadboard prototype using a function generator as input and a digital storage oscilloscope to capture waveforms — confirming instrumentation amplifier gain, filter roll-offs, notch rejection, rectifier behavior (no dead-band), and final envelope tracking from ~30 mV (rest) to ~4.92 V (full contraction).

Key Design Decision
The entire system is deliberately microcontroller-free — a design choice that trades the flexibility of digital post-processing (used in research-grade multichannel EMG systems) for hardware simplicity, low power consumption, and direct compatibility with analog motor drivers — well suited to embedded, power-constrained prosthetic applications.




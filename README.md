Unbiased Lucky Draw

A simple, secure, and provably fair lucky draw application that runs entirely in your browser. No server, no database, no installation required.

[Try the Live Demo!](https://jasman-hazly.github.io/LuckyDraw/luckydrawv2.html)

The Problem
1. Running a lucky draw for a company event or marketing promotion needs to be transparent and fair. Using a simple "random" function can be biased, and it's hard to prove that the draw wasn't tampered with. 
2. How do you handle past winners? What if the browser crashes?This tool solves all those problems. 
3. It's a high-integrity application built to be provably fair.

Core Features: 
🔒 Provably Fair: Uses a cryptographically secure random number generator (CSPRNG), not the standard, predictable Math.random().
💾 Persistent Winner List: Automatically saves a permanent history of confirmed winners to your browser's localStorage.
👥 Smart Filtering: Intelligently filters out past winners from new lists. It even fairly handles duplicate names!
🔄 Session Recovery: Automatically saves your current draw session. If your browser crashes, you can recover your session and resume where you left off.
👀 "MIA" (Missing In Action) Handling: Mark a winner as "MIA" to remove them from the current draw but not the permanent winner list, giving them a chance to win in the future.
📥 Data Portability: Download the complete history of past winners as a .csv file for your records.
🕵️ 100% Private & Client-Side: Everything runs in your browser. No participant data is ever sent to a server.

How to Use
1. Prepare Your List: Create a .csv file with one participant name per line.
2. Upload: Open the index.html (or live GitHub Pages link). Click "Select .CSV File" and choose your list.
3. The app will confirm how many participants are eligible and how many past winners were filtered out.
4. Draw: Click the "Draw a Winner!" button. Confirm: A modal will pop up with the winner's name.
5. Click "Done (Award Prize)" to confirm the win and save them to the permanent winner list.
6. Click "MIA (Not Present)" to discard the win.
7. Repeat: Continue drawing. The remaining participant count will update automatically.
  
The "Provable Fairness" Guarantee

This app's main feature is its integrity. 
1. Here is how we guarantee a fair draw:Cryptographically Secure (CSPRNG): We use window.crypto.getRandomValues, a high-entropy function built into modern browsers. It's the same level of randomness used for generating secure keys, not the simple Math.random() which is predictable and unfit for security.
2. Unbiased Selection (Rejection Sampling): To prevent a subtle bug called "modulo bias," we use a technique called Rejection Sampling. This ensures that every single participant has a statistically identical chance of being chosen, down to the last decimal.
3. Order-Proof (Fisher-Yates Shuffle): To ensure that the order of your .csv file (e.g., sorted alphabetically) has no impact on the outcome, the entire list of eligible participants is shuffled using the high-security Fisher-Yates algorithm (powered by the same CSPNG) before the first draw.
  
How to Deploy Your Own
1. You can host this for free on GitHub Pages!Create a new repository on GitHub.
2. Rename luckydraw.html to index.html.Upload the index.html file to your new repository.
3. In your repository, go to Settings > Pages.Under "Branch," select your main branch (e.g., main or master) and click Save.
4. Your lucky draw app will be live at https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/
  
Technology Stack
1. HTML5
2. Tailwind CSS (via CDN)
3. Vanilla JavaScript (ES6+)
4. Confetti-js (for the celebration!)

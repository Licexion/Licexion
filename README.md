🚀 How I Lost My Wallet and Built My Own System

📱 The Beginning. A Lost Wallet

It all started when I decided to buy 7 Solana at ~$130 each — for long-term gain. I understood crypto, but only at a basic level: I knew I had to store the seed phrase, but had no idea how easily and quickly it could be lost. 💸 I either wrote the words down or took a screenshot — I honestly can't remember anymore. My phone started acting up, I reset it to factory settings, and only then realized: the record was gone. The wallet was lost. ⚠️

I spent the next week in despair. I searched for any way to regain access, tried combinations, read forums. Paid solutions didn't inspire trust, and during my searches I even picked up a virus that forced me to format my drive using special utilities. 🦠 And then an idea came to me that changed everything: what if I wrote such a program myself? 💡

💻 First Step. A Console Checker

I didn't understand much about programming at the time. I tried Python first, but didn't like its syntax — so I switched to JavaScript (Node.js).⚙️ After about a week, the first console checker for Solana appeared. Weak, unstable, it constantly broke and froze. Every failure drained me emotionally. 😫 But a few hours later I'd sit back down at the computer and continue.

After roughly two weeks I achieved stable operation. The checker processed around 200 requests per second. But back then I knew nothing about nodes — the program used only 3 public ones, which quickly died under the load. 📉 As I later realized, most results were simply incorrect: data was lost before even reaching the server. I was seeing generation speed, not real verification speed. Speed means nothing without reliability — that was the first real lesson. 🛠️

But despite everything, I kept going. For three months before the loss I watched that wallet every single day: tracked the price, watched the balance grow, and at some point it had nearly doubled. 📈 I knew what this program was capable of — and it was that memory of the numbers I saw every day that was the fuel bringing me back to the computer again and again. 🔥

📉 First Expansion Attempts and the Big Crash

After the first success I decided to add support for Litecoin and Dogecoin. But every time I tried to integrate them, everything fell apart. 💥 All the stability I had fought so hard for disappeared within minutes. In the end I kept only Solana and shelved the project.

Coming back, I realized the old code was beyond saving — so many errors had accumulated in the current project that fixing one created two new ones. I made the hard decision: start from scratch. 🔄

🤖 Claude and a Hard Lesson

At some point I decided: better to rewrite everything from scratch. Claude (the free version) generated a project that looked perfect — structured, modular, beautiful on the surface. But in reality it was just air: the code didn't work, the logic was broken, and a week of attempts to fix it led nowhere. 🧪 I went back to my old code.

That's when I bought Claude Pro — and here a completely different quality of help revealed itself. ✨ It could write entire files with no line or character limits, and simultaneously find and fix logical errors in the architecture — not just syntax, but the logic of the program itself. I fixed errors in the main code one by one — in circles, over and over — until at some point they ran out and the program finally started breathing normally. 🌬️

📨 Full Refactor and Telegram

I built the new project slowly and carefully. Sometime in the summer, after a few weeks of work, a stable console version appeared. But then a new idea came: I want a tool I can use from any device — phone, tablet, TV, computer. 🌍 The choice fell on a Telegram bot.

This was completely new territory too. I did everything myself — read documentation and endlessly debugged code. 🕹️ Back then I was using early AI tools: Gemini 1.5 Pro, Claude, and ChatGPT. The last one was hardest — send 3 files and you'd hit a 5-hour limit. No modern tools like Cursor existed yet. I could spend 10 hours just figuring out that something was simply impossible to implement the way I'd planned.

After two months a bot with several dozen buttons was working. My first real battles here were with correct seed phrase generation — which I struggled with for a very long time — and with properly distributing requests across nodes. ⛓️ In parallel, I added SOL+ETH mode — since both networks use the same word library (BIP39), it was relatively easy to implement. Later I successfully added Bitcoin, Arbitrum, and Polygon.

The main problem remained the same — Solana nodes: there are very few public ones, all weak, quickly dying under load. A private node would solve the problem, but it costs money I didn't have at the time. 💸

Later I added the ability to enter a partial seed phrase directly in the chat. By autumn I had a more or less stable version that I could turn on and leave running. Every day I improved something — design, functionality, backend stability. 🛠️

💾 The SSD Disaster

From the very beginning, the program was quietly wearing out my SSD — writing enormous amounts of logs in the background, and I had no idea. ⚡ The issue wasn't storage space filling up, but write endurance (TBW) — the drive's rewrite resource was simply being exhausted. I found out about this only recently — after the code for automatic IP rotation was already finished. In 8 months of operation the program wrote 130 terabytes of data. 🩹 It was a gut punch — the drive was severely worn. Immediately after this discovery I fully optimized the logging: reduced it to an absolute minimum, keeping only what was essential. 🛑

🌀 Google Antigravity and New Possibilities

Later came Google Antigravity — an AI development environment from Google with access to Claude Opus and Sonnet. It was a genuine "wow" moment. 🌪️ The tool provided free access to powerful models, and I consumed all the limits to zero, waited for renewal, and consumed again. I began implementing all the ideas I couldn't before — sometimes spending the entire day's limit and waiting a week for it to reset. ⏳

🛡️ Whonix and Privacy

At some point I became aware of the risks of a static IP address while the program was running. I switched to Whonix Linux — a system stored on a USB drive and launched through a virtual environment, fully anonymizing all traffic. 🕵️‍♂️

In parallel I carried out a large-scale code optimization:

🧠 RAM usage — only 60 MB

⚡ CPU load — no more than 10%

🚀 Launch — with a single terminal command

📺 Runs on any device, even the weakest

🏛️ Final Architecture

The Telegram bot became a true command center with dozens of functions — like a cockpit panel: hundreds of buttons, each doing one specific thing, none of them redundant. 🕹️ And thanks to the 60 MB RAM optimization, the program became so universal it can run on literally any device. That is the best proof that the optimization was real.

The program's architecture became complex, but reliable:

👷 Each worker performs its own separate task

🔄 Tasks are distributed dynamically between threads

🚄 The number of threads adapts depending on the operating mode

🩹 If a thread "dies" — the program automatically restarts it without stopping the system

🌐 If an IP gets blocked — the program changes it in real time on its own

⚡ The nodes file and configuration can be edited while the program is running — it picks up changes instantly without crashing. This is what industrial software calls hot-swapping — a level most amateur projects never reach

📥 Full automatic node pulling from the internet

📝 Minimal logging — only the essentials

And the last thing — something I implemented just a few days ago: automatic IP rotation in real time. 🔄 If the program senses that an address has been blocked — it changes the IP on its own, without stopping, and continues working. This is critical because public RPC nodes ban for activity very quickly. The idea came to me on my own — AI only helped implement it in code. 🧠

✅ Conclusion

Since the moment I lost that wallet, a lot of time has passed. I went from someone who couldn't program at all to the author of a distributed system with its own architecture, traffic anonymization, automatic thread recovery, and a cross-platform interface. 🏁

It cost hundreds of hours, emotional exhaustion, a heavily worn SSD, and countless errors. But every time it seemed like there was nowhere left to go, I somehow came back — an hour later, a day later, a week later.

The program works. 💎

I never recovered my wallet. But it was precisely that desire — to finish what seemed impossible — that pushed me forward every time I wanted to give up. 

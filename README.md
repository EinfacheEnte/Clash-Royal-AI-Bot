## Clash Royale AI (Work in Progress)
An experimental, in-development AI agent designed to play Clash Royale automatically using computer vision and emulated inputs.

Status: Extremely early development. Expect bugs, missing features, and hardcoded logic. Currently, there is no configuration file or easy setup process.

> Disclaimer: Using bots, AI, or any third-party software to automate gameplay violates Supercell's Terms of Service. This repository is built strictly for educational purposes (learning computer vision, OCR, and automated state-machine logic). Using this on your actual account will likely result in a permanent ban.

Project Goal
The ultimate aim of this project is to build a closed-loop system that can:

See: Read the screen of an Android emulator (BlueStacks/Nox) to identify Elixir levels, cards in hand, and troops on the board.

Think: Process that information to decide which card to play and where.

Act: Send simulated tap/swipe commands to the emulator via Android Debug Bridge (ADB).

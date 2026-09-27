# Cross-Device Clipboard (p2p-clip) https://reveko0o.github.io/p2p-clip/

<img width="693" height="615" alt="image" src="https://github.com/user-attachments/assets/3d5e6128-f698-4dd7-a4cb-0b7ef8e4521e" />


I built this out of pure frustration because transferring simple text, links, or notes between my PC and phone was way more painful than it should have been. No sign-ups, no bloated apps, no cloud storage—just a direct, serverless P2P bridge to sync text instantly.

## Features

- **Serverless & Direct:** Built on WebRTC via PeerJS. Your text goes straight from device to device without hitting any third-party cloud database.
- **Auto-Clipboard Sync:** Incoming text is automatically captured and copied directly to your device's clipboard.
- **Zero Configuration:** Just open the page on two devices, match the IDs, and start sharing text.

## How It Works

- **Architecture & Workflow:**
  - **Connection Setup:** When you open the web app, it generates a unique ID (`clip_xxxxxx`) via a public PeerJS signaling server. Once the peer-to-peer tunnel is established between your two devices, the signaling server steps out entirely.
  - **Data Transfer & Clipboard API:** When you type or paste text and hit send, the string is streamed instantly over the secure WebRTC Data Channel. On the receiving end, the browser's `Clipboard API` (`navigator.clipboard.writeText`) automatically intercepts the incoming string and copies it directly to your system clipboard so you can paste it immediately.

## License

Distributed under the MIT License. See `LICENSE` for more information.

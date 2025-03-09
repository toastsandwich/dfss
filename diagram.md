                 ┌─────────────────────────────────┐
                 │     Metadata Server (Optional)  │
                 │  - Tracks file versions, peers  │
                 │  - Manages authentication       │
                 └──────────────▲──────────────────┘
                                │
                   Peer Discovery & Sync Requests
                                │
    ┌─────────────────────────────────────────────────────┐
    │                 P2P File Sync System                │
    │                                                     │
    │ ┌───────────┐        ┌───────────┐       ┌───────────┐ │
    │ │  Peer A   │ ◀────▶ │  Peer B   │ ◀───▶ │  Peer C   │ │
    │ │  (Client) │        │  (Client) │       │  (Client) │ │
    │ └───────────┘        └───────────┘       └───────────┘ │
    │       ▲                     ▲                     ▲    │
    │       │                     │                     │    │
    │ File Watchers     Delta Transfer + Encryption     │    │
    │ (inotify, etc.)      (TCP, QUIC, WebRTC)          │    │
    └───────────────────────────────────────────────────┘

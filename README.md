# Core Components `This is also my todo....`

[x] Plan it

[]  **Metadata Server**
  - Track nodes who have a certain file
  - Stores `Hashes, timestamps and Peer info`
  - Helps with peer discovery

[] **Client Node**
  - Watch over files
  - Send updates to other peers
  - Receive and Update file

[]  File Transfer Layer
- Delta Transfer (rsync-style) - only send changes file part
- Compression
- Secure Communication


# Data Flow
### **A. When a File is Modified**

1. **File watcher detects a change**  
2. **Compute a hash (SHA-256, MurmurHash)** to check if it's modified  
3. **Notify peers (or metadata server) about the update**  
4. **Sync the file using delta transfer** (only send changes)  
5. **Peers update their local copy**

### **B. When a New Peer Joins**

1.  **Peer connects to metadata server (if using one)**  
2. **Metadata server tells it which peers have the latest files**  
3. **Peer syncs files from nearest available node**

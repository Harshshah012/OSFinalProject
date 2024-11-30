# OSFinalProject
## Harsh Shah

```markdown
# P2P Publisher-Subscriber System with Hypercube Topology

A decentralized peer-to-peer publisher-subscriber system built on a hypercube topology, enabling efficient message routing and fault-tolerant communication.

## Features

- Decentralized P2P architecture with no central server
- Hypercube-based topology for efficient message routing
- Topic-based publish-subscribe system
- Fault tolerance with automatic recovery
- Message deduplication and TTL-based routing
- Dynamic peer discovery and connection management

## System Requirements

- Python 3.7+
- asyncio library
- Network connectivity for peer communication

```

## Usage

### Starting a Peer Node

```bash
1. python3 FinalProject.py <peer-id> <port>
2. make run
```

- `peer-id`: 3-bit binary identifier (e.g., "000", "001")
- `port`: Port number between 1-65535

## Available Commands

1. Create Topic
2. Delete Topic
3. List Available Topics
4. Subscribe to Topic
5. Pull Messages
6. Connect to Peer
7. Publish Message
8. Leave Network
9. Display Network Stats
10. Search Topics
11. Exit

## Testing Suite

### Running Tests

```bash
# Run all tests
make tests

# Run individual tests
make test_deployment
make test_failure
make test_node
make test_replica
make test_replication
make benchmark
```

## Extra Credit
```bash
# Run Extra Credit Program
make extra
```



```markdown
## File Structure

```
p2p-pubsub-system/
├── FinalProject.py          # Main implementation file
├── FinalProjectcopy.py      # Backup copy of main file
├── benchmark.py             # Performance testing suite
├── ExtraCred1.py            # Extra credit implementation
├── Makefile                 # Build and test automation
├── test_deployment.py       # Basic deployment tests
├── test_failure_recovery.py # Failure recovery tests
├── test_node_recovery.py    # Node recovery tests
├── test_replica_failover.py # Replica failover tests
└── test_replication.py      # Replication system tests
```

### Core Files:

- **FinalProject.py**: Contains the main P2P system implementation with DHT and PeerNode classes
- **benchmark.py**: Performance testing and metrics collection
- **ExtraCred1.py**: Additional features implementation

### Test Suite:

- **test_deployment.py**: Validates basic system deployment
- **test_failure_recovery.py**: Tests system resilience
- **test_node_recovery.py**: Verifies node state recovery
- **test_replica_failover.py**: Tests failover mechanisms
- **test_replication.py**: Validates topic replication
```


**DHT (Distributed Hash Table)**
- Manages topic storage and retrieval
- Handles topic replication
- Maintains peer mappings

**PeerNode**
- Manages peer connections
- Handles message routing
- Implements publish-subscribe logic
- Manages topic subscriptions

### Network Topology

- Hypercube-based structure
- Each peer connects to nodes differing by one bit in their ID
- Maximum of 3 hops for 8-node network (3-bit IDs)

## Performance

- Message routing optimized using Hamming distance
- Logarithmic routing complexity
- Predictable performance with maximum 3 hops in 8-node network
- Automatic fault detection and recovery

## Fault Tolerance

- Heartbeat mechanism for peer health monitoring
- Topic replication across multiple peers
- Dynamic topic reassignment on peer failure
- Alternative routing paths for message delivery

## Logging

- Each peer maintains its own log file
- Format: `<peer_id>_log.txt`
- Logs include operations, errors, and network events

## Cleanup

```bash
make clean
```

Cleans up:
- Running peer processes
- Open network ports
- Temporary files

## Known Limitations

- Local network operation only
- Requires manual peer connection
- No persistent storage

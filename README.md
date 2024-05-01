# Peer-to-Peer Decentralized Network Optimization Algorithm with Minimal Server Oversight

## Pseudo Code Algorithm

**Variables**:
- `NU`: New User
- `RU`: Random User
- `DU`: Disconnected User

**Configuration**:
- Maximum number of connections per user: 5
- Similarity threshold to halt the algorithm: 60%

**Algorithm**:
1. Gather a descriptive vector about `NU` (interests, job, major, etc.) from their profile.
2. Classify `NU` based on this basic info using k-means.
3. Randomly select a `RU` from the same cluster as `NU` and pass the info to the `NU` client-side code.

**Process**:
```plaintext
While conditions are False:
  if NU is more similar to RU than one of RU's existing connections:
    - NU.connections += 1
    - RU = RU's connection that NU had the highest similarity to
    - DU.connections -= 1
    - DU re-runs this algorithm until conditions are satisfied.

  else if NU is less similar to RU than any existing connections but RU has less than 5 connections:
    - NU.connections += 1
    - RU.connections += 1
    - RU = RU's connection that NU had the highest similarity to

  else if NU is less similar to RU than any existing connections and RU has more than 5 connections:
    - RU = RU's connection that NU had the highest similarity to

  if NU.connections == 5:
    - conditions = True
    - Stop algorithm for client


<br><br><br>
Potential solutions to current issues:<br>
Issue: Network volatility due to users continuously getting purged from the network because of similarity contraints. <br>
Solution: People can be connected to people who aren't connected to them. This prevents constant reorganizing of the network. Once a user has found their five connections they are set in stone (best to put a minimum threshold of similarity between the two) <br>
<br>
Issue: The network will get stale after a while.<br>
Solution: Have the users run this algorithm once a week in order to get setup with new users with new data, though this whole algorithm could cause users to inadvertantly converge towards each other but we'll see. <br>

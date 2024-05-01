# Peer-to-Peer Decentralized Network Optimization Algorithm with Minimal Server Oversight
Pseudo Code Algorithm:
NU = New User
RU = Random User
DU = Disconnected User
define number of connections each user in this network should have (increasing this drastically increases the computational requirements of the network) [we'll define this arbitrarily as max # of connections = 5]
define a similarity threshold to allow users to halt algorithm [we'll define this arbitrarily as 60%]
1. Gather a descriptive vector about a new user (NU) (this could be their interests, job, major, etc that they select when creating a profile on a website)
3. Cluster them off of this basic info using kmeans to receive their cluster.
4. Randomly pull a user (RU) from the same cluster as them and hand the info over to their client-side code <br>
While(conditions == False):<br>
  if (NU is more similar to RU than one of RU's existing connections):<br>
    NU.connections += 1<br>
    RU = RU's connection that NU had the highest similarity to<br>
    DU.connections -= 1<br>
    DU calls this algorithm until conditions are satisfied.<br>
  else if (NU is less similar to RU than any existing connections but RU has less than 5 connections):<br>
    NU.connections += 1<br>
    RU.connections += 1<br>
    RU = RU's connection that NU had the highest similarity to<br>
  else if (NU is less similar to RU than any existing connections and RU has more than 5 connections):<br>
    RU = RU's connection that NU had the highest similarity to<br>
  if (NU.connections = 5):<br>
    conditions = True<br>
    stop algorithm for client<br>

<br><br><br>
Potential solutions to current issues:<br>
Issue: Network volatility due to users continuously getting purged from the network because of similarity contraints. <br>
Solution: People can be connected to people who aren't connected to them. This prevents constant reorganizing of the network. Once a user has found their five connections they are set in stone (best to put a minimum threshold of similarity between the two) <br>
<br>
Issue: The network will get stale after a while.<br>
Solution: Have the users run this algorithm once a week in order to get setup with new users with new data, though this whole algorithm could cause users to inadvertantly converge towards each other but we'll see. <br>

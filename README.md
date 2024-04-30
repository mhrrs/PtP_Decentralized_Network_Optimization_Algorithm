# Peer-to-Peer Decentralized Network Optimization Algorithm with Minimal Server Oversight
Pseudo Code Algorithm:
define number of connections each user in this network should have (increasing this drastically increases the computational requirements of the network) [we'll define this arbitrarily as max # of connections = 5]
define a similarity threshold to allow users to halt algorithm [we'll define this arbitrarily as 60%]
1. Gather a descriptive vector about a new user (NU) (this could be their interests, job, major, etc that they select when creating a profile on a website)
3. Cluster them off of this basic info using kmeans to receive their cluster.
4. Randomly pull a user (RU) from the same cluster as them and hand the info over to their client-side code
While(conditions == False):
  if (NU is more similar to RU than one of RU's existing connections):
    conditions = True
    Stop algorithm for this client
  else if (NU is less similar to RU than any existing connections but RU has less than 5 connections):
    conditions = True
    Stop algorithm for this client
  else if (NU is less similar to RU than any existing connections and RU has more than 5 connections):
    conditions = False
    RU = RU's connection that NU had the highest similarity to
   

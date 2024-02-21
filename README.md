# cs4700-project3

# high-level approach
Implementation of dynamic routing:
  I designed a multi-layered decision-making process to evaluate the priority of each route. This includes parsing AS paths, calculating local preference values, evaluating source types for routes, etc.
  Use priority queues to store routes in forwarding tables to quickly select the best path.
  
Route aggregation：
  I implemented a method to determine if two routing entries can be aggregated by comparing their prefix length and netmask. This requires precise handling of IP addresses and subnet masks. To accomplish this goal, I wrote several equations for converting IP addresses and numbers into binary as well as equations for calculating cidr. I also wrote methods to compare network prefixes. The aggregated route entries are updated to a broader prefix, which helps reduce the size of the forwarding table and improves router efficiency.

Message processing framework：
  According to the requirements of the project, I designed an extensible message processing framework that can dynamically adjust the processing strategy according to the message type (such as update, withdrawal, and data).
  
# Challenges
  The biggest challenge I face is understanding the structure of all the data structures we are using and how to combine them to get the desired outputs. Considering multiple factors (e.g., local preference, AS path, source type, etc.) complicates the decision logic when implementing the BGP decision process. I think ensuring the accuracy and efficiency of the logic is a challenge in this project. When implementing route aggregation, I had difficulty in determining which routes could be merged. This is because it involves precise manipulation and comparison of IP addresses and subnet masks. In the beginning, I forgot to convert the network prefixes to binary as well as calculate the CIDR which cost me a lot of time.

# Testing
  ran the tests in the config file

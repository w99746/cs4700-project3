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
  The biggest challenge I face is understanding the structure of all the data structures we are using and how to combine them to get the desired outputs

# Testing

# 4700-p3
### High Level Approach
1. Parse arguments for AS number and connections.
2. Create router using given
AS number and connections
3. Establish connection with neighbor routers and send handshake message.
4. Run router:
    - Monitors socket with select function for any incoming messages.
    - For all active sockets, receive data and handle the following message types delivered in JSON:
        - Update Messages
        - Withdraw Messages
        - Data Messages
        - Dump Messages
    - While handling these messages, the router keeps a list of announcements as well as a forwarding table--aggregating possible entries and removing withdrawn networks appropriately.

### Challenges
- Misunderstanding with the definition of source/destination with regards to relationships and data messages section of the requirements.
- Developing aggregation and disaggregation while
accurately taking into account withdrawals. Settled on base forwarding table with updating aggregation table.


### Testing
This code was tested using the given configurations.

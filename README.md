# .NET_with_Docker

### show reserved ports
``` netsh int ip show excludedportrange protocol=tcp ```

### Windows NAT Driver (winnat) sometimes reserves random ports
``` net stop winnat ```
``` net start winnat ```
### choose the port which is not reserved after restarting

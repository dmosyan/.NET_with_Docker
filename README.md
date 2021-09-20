# .NET_with_Docker

### show reserved ports
``` netsh int ip show excludedportrange protocol=tcp ```

### Windows NAT Driver (winnat) sometimes reserves random ports
``` net stop winnat ```
``` net start winnat ```
### choose the port which is not reserved after restarting

### create certificate manually
``` dotnet dev-certs https -ep $env:USERPROFILE\.aspnet\WeatherAPI.pfx -p pa55s0rd! ```
``` dotnet dev-certs https --trust ```

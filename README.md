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
### add user secret
``` dotnet user-secrets set "Kestrel:Certificates:Development:Password" "pa55s0rd!" ```

### configure https for container
``` docker run -p 8080:80 -p 8081:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8081 -e ASPNETCORE_ENVIRONMENT=Development -v $env:APPDATA\Microsoft\UserSecrets\:/root/.microsoft/usersecrets -v $env:USERPROFILE\.aspnet:/root/.aspnet/https/ weatherapi ```

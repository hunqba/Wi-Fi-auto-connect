Connect to a Wi-Fi automatically

If your password has the special characters such as '&' will be written '&amp;'
To determine password exactly.
Please use command (run as an administrator): netsh wlan export profile name="Your SSID" key = clear folder = "path"
Your password will be a value of the key <keyMaterial>Your-password</keyMaterial>
	
You can use the command '$env:userdnsdomain' on powershell to detect your 'userdomain' or '$env:userdnsdomain' on powershell to detect your 'USERDNSDomain'

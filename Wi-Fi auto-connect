# import module
import os
import tempfile

# function to establish a new connection
def createNewConnection(name, SSID, password):
    with open(tempfile.NamedTemporaryFile().name, 'w') as file:
        config = """<?xml version=\"1.0\"?>
        <WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
            <name>"""+name+"""</name>
            <SSIDConfig>
                <SSID>
                    <name>"""+SSID+"""</name>
                </SSID>
            </SSIDConfig>
            <connectionType>ESS</connectionType>
            <connectionMode>auto</connectionMode>
            <MSM>
                <security>
                    <authEncryption>
                        <authentication>WPA2PSK</authentication>
                        <encryption>AES</encryption>
                        <useOneX>false</useOneX>
                    </authEncryption>
                    <sharedKey>
                        <keyType>passPhrase</keyType>
                        <protected>false</protected>
                        <keyMaterial>"""+password+"""</keyMaterial>
                    </sharedKey>
                </security>
            </MSM>
        </WLANProfile>"""
        file.write(config)
    file.close()
    command = "netsh wlan add profile filename=\""+file.name #+".xml\""
    os.system(command)
    os.unlink(file.name)

# function to connect to a network
def connect(name, SSID):
	command = "netsh wlan connect name=\""+name+"\" ssid=\""+SSID+"\" interface=Wi-Fi"
	os.system(command)
  
  
# input wifi name and password
name = "Your SSID" #input("Name of Wi-Fi: ")
# note that: if special character such as '&' will be written '&amp;'
# to determine password exactly. Pls use command (run as an administrator): netsh wlan export profile name="Your SSID" key = clear folder = "path"
# your password is the value on the key <keyMaterial>Your-password</keyMaterial>
password =  "Your-password" #input("Password: ")
	
#You can use the command '$env:userdnsdomain' on powershell to detect your 'userdomain' or '$env:userdnsdomain' on powershell to detect your 'USERDNSDomain'
if(os.environ['userdomain'] == "input-your-userdomain") or os.environ['USERDNSDomain'] == "input-your-USERDNSDomain":
    # establish new connection
    createNewConnection(name, name, password)
    # connect to the wifi network
    connect(name, name)

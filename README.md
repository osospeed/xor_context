# xor_context
Metasploit context-keyed payload encoder

# Available context keys:
- hostname: linux, intel, 64 bit
- domainname: windows, intel, 32 bit (Work in progress by [jonasw234](https://github.com/jonasw234))
- domainname: windows, intel, 64 bit (by [jonasw234](https://github.com/jonasw234))
# How to
- Copy the file `xor_context.rb` to the encoders folder e.g.: `/opt/metasploit/modules/encoders/x64/xor_context.rb`
- You can use the module inside Metasploit or msfvenom. eg.:  
`msfvenom --platform linux -p linux/x64/exec cmd='ls -la' -e x64/xor_context C_HOSTNAME=victimpc -f elf -o test`  
- This resulting file will work only on machines having 'victimpc' as hostname
- For the domainname encoders you need to use
`msfvenom --platform windows -p windows/x64/exec cmd='calc.exe' -e x64/domainname_x64 C_DOMAINNAME='yourdomain' -f exe -o test.exe`  

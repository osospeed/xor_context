# UPDATE
This is now part of Metasploit: https://github.com/rapid7/metasploit-framework/pull/12033

# xor_context
Metasploit context-keyed payload encoder

# Available context keys:
- hostname: linux, intel, 64 bit
- domainname: windows, intel, 32 bit (Work in progress by [jonasw234](https://github.com/jonasw234))
- domainname: windows, intel, 64 bit (Work in progress by [jonasw234](https://github.com/jonasw234))
# How to
- Copy the file `xor_context.rb` to the encoders folder e.g.: `/opt/metasploit/modules/encoders/x64/xor_context.rb`
- You can use the module inside Metasploit or msfvenom. eg.:  
`msfvenom --platform linux -p linux/x64/exec cmd='ls -la' -e x64/xor_context C_HOSTNAME=victimpc -f elf -o test`  
- This resulting file will work only on machines having 'victimpc' as hostname

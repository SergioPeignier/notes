# Reinstall xcode:
https://apple.stackexchange.com/questions/254380/macos-sierra-invalid-active-developer-path
`xcode-select --install`

# Copy gcc as gcc-4.2 (same for g++) in order to build python C wrappers
sudo ln -s /usr/bin/gcc /usr/local/bin/gcc-4.2

# In sierra there is an anoying System Integrity Protection to avoid it:
+ restart your Mac and hold Command+R as it boots
+ type `csrutil disable`
https://www.howtogeek.com/230424/how-to-disable-system-integrity-protection-on-a-mac-and-why-you-shouldnt/

# Spotlight works as crazy, the best idea is to disable it:
+ type `sudo launchctl unload -w /System/Library/LaunchDaemons/com.apple.metadata.mds.plist`
http://www.iclarified.com/49187/how-to-disable-and-reenable-spotlight-indexing-on-your-mac
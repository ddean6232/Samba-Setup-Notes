# Samba-Setup-Notes

Arguments for the valid users parameter must be comma-separated. Also, notice that you typed "writable" instead of writeable.  
And, because writeable is the inverted synonym of read only, there's no need to declare the read only parameter.  

Here's the correct config:  

[Daze]  
comment = Default connect  
path = /  
valid users = darren_dean, admin, root   
force user = root  
force group = root  
browseable = yes  
writeable = yes  
admin users = root  
public = yes  
create mask = 0777  
directory mask = 0777  
Restart your Samba server (run e.g. sudo service smbd restart or sudo systemctl restart smbd.service) with these configs and see if it works.  

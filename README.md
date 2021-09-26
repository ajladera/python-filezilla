# python-filezilla

```sh
import glob
from ftplib import FTP


ftp = FTP()
ftp.connect('host-ftp', port) # ftp.connect('ftp-files.integracion.io', 2124)
ftp.login(user='user', passwd='passwd')
ftp.retrlines('LIST')
ftp.cwd('/directory')

filenames = ftp.nlst()

for filename in filenames:

    with open( filename, 'wb' ) as file :
        ftp.retrbinary('RETR %s' % filename, file.write)

        file.close()

ftp.quit()
```

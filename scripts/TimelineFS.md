#### Timeline a mounted Windows partition
1. log2timeline.py -hashsers md5 -z CST6CDT /data/HOSTNAME/HOSTNAME_1.pb /MOUNTPOINT
2. analyzeMFT.py --bodyfull -b /data/HOSTNAME /HOSTNAME1.bodyfile -f /MOUNTPOINT/\$MFT  
3. log2timline.py  /data/HOSTNAME/HOSTNAME_1.pb /data/HOSTNAME /HOSTNAME1.bodyfile  
4. log2timline.py  /data/HOSTNAME/HOSTNAME_2.pb /data/HOSTNAME /HOSTNAME2.bodyfile  
   
#### Generate CSVs
5. psort -analysis tagging -o l2tcsv -w /data/HOSTNAME/HOSTNAME_1.csv /data/HOSTNAME/HOSTNAME_1.pb
6. psort -analysis tagging --tagging-file /usr/share/plaso/tag_windows.txt -o l2tcsv -w /data/HOSTNAME/HOSTNAME_2.csv /data/HOSTNAME/HOSTNAME_2.pb
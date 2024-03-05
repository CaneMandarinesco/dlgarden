https://www.ilpuntotecnico.com/sblocco-smart-modem-tim-telecomitalia-technicolor-tg789-vac/
```bash
# decripta il file .ini
openssl aes-128-cbc -K a875e62aa6f1d430dac45fcd0e3bb246 -nosalt -iv 0 -d -in user_config.ini -out user.ini
# cripta il file
...

# ssh 
ssh -o KexAlgorithms=diffie-hellman-group1-sha1 -o HostKeyAlgorithms=ssh-dss -o Ciphers=3des-cbc  Unlock@192.168.1.1
```

cfw: iinet vant-6
https://github.com/BoLaMN/tch-exploit/releases/tag/2.0.1-rc7
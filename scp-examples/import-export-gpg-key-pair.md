## Export the GPG key

gpg --list-keys

Key id'nizi (seçiniz pub ile başlayan kısımda yer alan bilgiyi seçiniz)

gpg --output mygpgkey_pub.gpg --armor --export keyid
gpg --output mygpgkey_sec.gpg --armor --export-secret-key

Deneyimim o ki önce sanal / fiziksel işletim sisteminizi çalıştırmanız gerekiyor

ssh user@remotehost ile bağlantıyı sağladıktan sonra

scp mygpgkey_pub.gpg mygpgkey_sec.gpg user@remotehost:~/ ile kopyalama işlemini gerçekleştirelim.

## Sonra import edelim :

gpg --import ~/mygpgkey_pub.gpg
gpg --allow-secret-key-import --import ~/mygpgkey_sec.gpg

gpg --list-keys ile uzak bilgisayardaki bilginizi görebileceksiniz

gpg --edit-key keyid ile gpg komut satırına ulaştıktan sonra sign yazıp yes/evet seçelim , sonra trust için 5 ultimate seçelim save ile kaydedip çıkalım.

rm ~/mygpgkey_sec.gpg ~/mygpgkey_pub.gpg sonra da dosyaları silelim.

Teşekkürler

Kaynak : [How to import/export GPG key pair](https://www.debuntu.org/how-to-importexport-gpg-key-pair/)
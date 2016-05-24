# Ansible LetsEncrypt testato su Debian Jessie

Installa le dipendenze per Let's Encrypt e NGINX, genera il certificato in base al dominio e copia il template per configurare nginx su ssl

### I certificati si troveranno in questa path

* /etc/letsencrypt/live/DOMINIO.TUO/cert.pem
* /etc/letsencrypt/live/DOMINIO.TUO/privkey.pem
* /etc/letsencrypt/live/DOMINIO.TUO/chain.pem


### Note d'uso

Editare le variabili presenti in
       roles/letsencrypt/defaults/main.yml

* `letsencrypt_email` - la mail del proprietario
* `letsencrypt_domain` - il dominio su cui verrà generato il certificato


Editare il file hosts per impostare i server su cui andare ad installare tutto, esempio

`[servers]`
`test.mikytux.info`


Lanciare tutto con:

ansible-playbook -i hosts site.yml -l servers

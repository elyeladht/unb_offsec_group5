# COMANDOS

* ```hash-identifier [hash]``` = identificar o tipo de hash (mais provável)
* ```hashid -m [hash]```= identifica o tipo de hash (talvez)
* ```hashcat -h``` : verificar os modos, os tipos de hash e outras coisas mais
* ```hashcat -m [x]``` : colocar o número do modo do respectivo hash
    * Exemplo: ```hashcat -m 3200 hashbcrypt.txt /usr/share/wordlists/rockyou.txt ```

### Alguns hashs precisaram de estratégias diferenciadas:

* ```grep -E grep -E '^.{4}$' /usr/share/wordlists/rockyou.txt```: 
        filtra o dicionário rockyou.txt para conter somente palavras com 4 caracteres. Pode-se filtrar para qualquer outro número.
    * Exemplo: ```hashcat -m 1800 '$6$aReallyHardSalt$6WKUTqzq.UQQmrm0p/T7MPpMbGNnzXPMAXi4bJMl9be.cfi3/qxIf.hsGpS41BqMhSrHVXgMpdjS6xeKZAs02.' sixWordrockyou.txt --show```

* ```head -n 1000000 /usr/share/wordlists/rockyou.txt > rockyou_pequena.txt```: 
        exemplo de criação de um dicionário rockyou menor para tentar diminuir o tempo de execução.
    * Exemplo: ```hashcat -m 1800 hashbcrypt.txt rockyo_pequena.txt ```


# LINKS ÚTEIS

* https://hashcat.net/wiki/doku.php?id=example_hashes
* https://10015.io/tools/md5-encrypt-decrypt
* https://crackstation.net/


# wocker-jenkins-deploy

##Instalacja Wockera

```
vagrant plugin install vagrant-hostsupdater
git clone https://github.com/wckr/wocker.git && cd wocker
```
Więcej o instalacji przeczytasz tutaj (np. wsparcie dla Windows i NFS): _http://wckr.github.io/_

Uruchamianie maszyny wirtualnej
---
```
vagrant up
```

Dostęp do serwera WWW
---
Przy pierwszym uruchomieniu uruchomiona zostanie automatycznie czysta, testowa instancja Wordpressa z kontenera o nazwie wocker. Dostęp do tej instancji możliwy jest poprzez adres http://wocker.dev/ 

_Plugin vagrant-hostsupdater do Vagranta powinien automatycznie na lokalnej maszynie wprowadzić odpowiedni wpis w hosts i powiązać nazwę hosta z IP wirtualnej maszyny._

Dane logowania
---
Każdy nowo utworzony kontener posiada następujące dane do logowania:

*WordPress*

- User: admin
- Pass: admin

*Database*

- Name: wordpress
- User: wordpress
- Pass: wordpress

Dostęp do plików na lokalnej maszynie
---
Wszystkie kontenery są dostępne na Twojej lokalnej maszynie w katalogu data/<nazwa_kontenera>. Obydwa foldery (ten z maszyny wirtualnej jak i na maszynie lokalnej) są ze sobą zsynchronizowane.

- Katalog na lokalnej maszynie: data
- Katalog na maszynie wirtualnej: /home/core/data


Połączenie z maszyną wirtualną przez SSH
---
Aby uzyskać dostęp do konsoli na maszynie wirtualnej należy użyć poniższej komendy
```
vagrant ssh
```
_Połączenie nie wymaga logowania, zostaniemy automatycznie zalogowani na konto vagrant, jeżeli istnieje potrzeba przełączenia się na konto roota wystarczy użyć komendy 'sudo -i' już bezpośrednio z poziomu maszyny wirtualnej._

Tworzenie nowego kontenera
---
_wocker start CONTAINER_
```
wocker start test
```

Zatrzymywanie kontenera
---
_wocker stop CONTAINER_
```
wocker stop test
```

Uruchamianie istniejącego kontenera
---
_wocker run CONTAINER_
```
wocker run test
```

Wyłączanie maszyny wirtualnej
---
```
vagrant halt
```

# Users and groups

<details>

<summary>List of commands</summary>

{% code title="User commands" lineNumbers="true" %}
```bash
useradd #Add a new user
usermod #Modify an existing user.
userdel #Delete a user account
passwd #Change a user's password
chage #Change user password expiry information.
passwd -l #Lock a user account
passwd -u #Unlock a user account.
```
{% endcode %}

{% code title="Group commands" lineNumbers="true" %}
```bash
groupadd #Add a new group
groupmod #Modify a group
groupdel #Delete a group
```
{% endcode %}

</details>

## Users

### Oppgave 1

_Hvilke options brukte du, og hvilken option gjorde hva?_

{% code title="Jeg brukte følgende options" %}
```bash
-m, --create-home # Oppretter home directory for brukeren
-s, --shell SHELL # Setter stien til brukeren sin login shell
```
{% endcode %}

```bash
for user in ole dole doffen donald fantonald spokelseskladden svartepetter; do 
    sudo useradd -m -s /bin/bash "$user"
```

```sh
dole:x:1071:1071::/home/dole:/bin/bash
doffen:x:1072:1072::/home/doffen:/bin/bash
donald:x:1073:1073::/home/donald:/bin/bash
fantonald:x:1074:1074::/home/fantonald:/bin/bash
spokelseskladden:x:1075:1075::/home/spokelseskladden:/bin/bash
svartepetter:x:1076:1076::/home/svartepetter:/bin/bash
```

_Prøv å tenke gjennom hva et shell er, og hvordan du ville forklart det til noen andre._

> Et shell er ...

### Oppgave 2

_Endre passordet til alle brukerne:Finn på noe selv. Passordene skal utløpe i morgen._

{% code title="Jeg brukte følgende options" %}
```bash
-x, --maxdays MAX_DAYS # Setter max antall dager passordet er gyldig ø
```
{% endcode %}

```bash
sudo passwd ole
sudo passwd -x 1  ole
```

```bash
sudo passwd ole && sudo passwd -x 1  ole
```

### Oppgave 3

_Endre følgende attributter på brukerne:_

_- dole - nytt brukernavn: dolly_

_- alle brukerne skal få ny primærgruppe: ‘duck’_

_- ole og dole skal få en ny hjemmemappe kalt: ‘/home/ducklings’_

{% code title="Jeg brukte følgende options" %}
```bash
-l, --login NEW_LOGIN # Changes [LOGIN] to [NEWLOGIN]
-g, --gid GROUP # Endrer primærgruppen til brukeren, den nye gruppen på eksistere
```
{% endcode %}




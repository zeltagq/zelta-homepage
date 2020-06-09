## Architecture (High Level Overview)
* Zelta has a cli client, a server tier and a database tier.
* The server tier has 2 types of servers : Application Server (zelta-server) and Authentication Server (ZUM)
* The client only communicates with the Zelta server. All communication with the ZUM server is carried out by the Zelta server.
* The database tier consists of a Mongodb cluster.

## Security & Encryption (High Level Overview)
* Zelta does not collect any personal information.
* As Zelta works in the terminal, it does not log your ip address nor does it store cookies and trackers.
* Your messages are only stored until you see them. Once you view them, all records of their existence are completely erased.    So do remember to screenshot important messages.
* User passwords and group passphrases are converted to salted hashes before they are stored in the database (Bcrypt JS)
* Messages are encrypted using AES (Crypto JS) with rotating master keys maintained by the server. The server maintains a   total of 8 rotating master keys. These keys rotate after each use.
* All sensitive communication is carried out using signed json web tokens.
* ZUM maintains a separate set of master keys and signing keys. Master keys are used by the requesting server to sign their jwt tokens while the signing keys are used by ZUM to sign authorization tokens. These signing keys are only created when login requests are received.
* Finally as Zelta is an anonymous messaging service, you can always drop your current username for a new one!

## Open Source
* Zelta's claims are backed up by code.
* You will find the complete code of the cli client as well as the server tier on GitHub.
* Do leave a star and share the word if you like Zelta.
* You can always download the code and host your private Zelta and ZUM servers.

## Requirement
Node JS (v8 and above)

## Install
```
npm i -g zelta
```
```
yarn global add zelta
```

## Commands

```sh
$ zelta help
```
##### Displays a list of all the available commands

```sh
$ zelta register
```
##### Register a new username

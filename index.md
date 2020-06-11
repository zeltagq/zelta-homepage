### Architecture (High Level Overview)
* Zelta has a cli client, a server tier and a database tier.
* The server tier has 2 types of servers : Application Server (zelta-server) and Authentication Server (ZUM)
* The client only communicates with the Zelta server. All communication with the ZUM server is carried out by the Zelta server.
* The database tier consists of a Mongodb cluster.

### Security & Encryption (High Level Overview)
* Zelta does not collect any personal information.
* As Zelta works in the terminal, it does not log your ip address nor does it store cookies and trackers.
* Your messages are only stored until you see them. Once you view them, all records of their existence are completely erased.    So do remember to screenshot important messages.
* User passwords and group passphrases are converted to salted hashes before they are stored in the database (Bcrypt JS)
* Messages are encrypted using AES (Crypto JS) with rotating master keys maintained by the server. The server maintains a   total of 8 rotating master keys. These keys rotate after each use.
* All sensitive communication is carried out using signed json web tokens.
* ZUM maintains a separate set of master keys and signing keys. Master keys are used by the requesting server to sign their jwt tokens while the signing keys are used by ZUM to sign authorization tokens. These signing keys are only created when login requests are received.
* Finally as Zelta is an anonymous messaging service, you can always drop your current username for a new one!

### Open Source
* Zelta's claims are backed up by code.
* You will find the complete code of the cli client as well as the server tier on GitHub.
* Do leave a star and share the word if you like Zelta.
* You can always download the code and host your private Zelta and ZUM servers.

### Requirement
Node JS (v8 and above)

### Install
```
npm i -g zelta
```
```
yarn global add zelta
```

### Commands

*Display a list of all the available commands*
```sh
$ zelta help
```

*Register a new username*
```sh
$ zelta register
```
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/register.gif">
</p>

*Login*
```sh
$ zelta login
```
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/login.gif">
</p>

*Send a message*
```sh
$ zelta send
```
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/send-msg.gif">
</p>

*Create a group. There are two types of groups in zelta : public and private. Anyone can join a public group using the passphrase but private groups require an invite to join. The invitation is sent by the admin, who is the creator of the group. Currently in beta the group limit is 50 members.*
```sh
$ zelta group
```
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/group-creation.gif">
</p>

*Join a public group using the passphrase. Group names are referred to using the @ symbol.*
```sh
$ zelta join <group>
```
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/join-grp.gif">
</p>

*If you try joining a private group, zelta mentions that you need an invite.*
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/no-invite-join.gif">
</p>

*Invite a user to your group (admin privilege). Use @ for mentioning group name.*
```sh
$ zelta invite <user> <group>
```
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/send-invite.gif">
</p>

*Accept a group invite. You will receive the invite in your inbox.*
```sh
$ zelta accept-invite <group>
```
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/accept-invite.gif">
</p>

*To send messages to a group, just address the message to a group name using @. Needless to say, you need to be a member or admin of the group. Remember that @ tells zelta that you intend to send the message to a group. Without @ the message may be sent to a user with the same username as the group name.*
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/group-msg.gif">
</p>

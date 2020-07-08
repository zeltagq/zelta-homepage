<head>
  <link rel="shortcut icon" type="image/x-icon" href="favicon.ico">
</head>

### Project Zelta
*Zelta is a secure and anonymous messaging service. It only has a cli client to protect you against various web and mobile vulnerabilities. It is cross platform compatible with the only runtime dependency being Node JS.*

### Security & Encryption (High Level Overview)
* Zelta does not collect any personal information.
* Zelta does not log your ip address nor does it store cookies and trackers.
* Your messages are only stored until you see them. Once you view them, all records of their existence are completely erased. So do remember to screenshot important messages.
* User passwords and group passphrases are converted to salted hashes before they are stored in the database (Bcrypt JS)
* The database server hardware encrypts all data at rest.
* Messages are encrypted using AES (Crypto JS) with rotating cryptographic keys produced by the application server.
* All sensitive communication is carried out using signed json web tokens.

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

*Login. Once you login, the access token is valid for 24 hrs. You should logout after each session on an untrusted device.*
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

*You can always change the access level of your groups (admin privilege)*
```sh
$ zelta set-public <group>
```
```sh
$ zelta set-private <group>
```
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/public-private.gif">
</p>

*Check your messages using the inbox command. Group messages appear in a user@group format. The time shown is GMT unless you have configured your local timezone.*
```sh
$ zelta inbox
```
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/inbox.gif">
</p>

*Configure your local timezone using the timezone configuration wizard. For your security and anonymity, this info is not sent to the server. You will have to re-configure your timezone each time you are on a new device or each time you perform a fresh install. If you dont do this all incoming messages will show the GMT time.*
```sh
$ zelta timezone
```
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/timezone.gif">
</p>

*List all the members of a group. Needless to say, you need to be a member yourself.*
```sh
$ zelta members <group>
```
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/members.gif">
</p>

*Leave a group. If you are the admin, the oldest member of the group becomes the new admin.*
```sh
$ zelta leave <group>
```
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/leave.gif">
</p>

*Kick a group member (admin privilege)*
```sh
$ zelta kick <user> <group>
```
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/kick.gif">
</p>

*Logout. You should logout after each session on an untrusted device. If you dont logout, the access token expires in 24 hrs.*
```sh
$ zelta logout
```
<p align="center">
  <img src = "https://raw.githubusercontent.com/zeltagq/docs/master/logout.gif">
</p>

<br><br>
<hr style="height:10px;border-width:10px;color:gray;background-color:gray">
<footer>
  <p align="center"><b>CREATED BY : ZAYGOZI</b></p>
  <p align="center"><a href = "https://www.linkedin.com/in/zaygo/">Linkedin</a> &nbsp&nbsp <a href = "https://github.com/zaygozi">Github</a></p>
</footer>
<hr style="height:10px;border-width:10px;color:gray;background-color:gray">

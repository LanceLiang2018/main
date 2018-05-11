# Hack.Chat

[hack.chat](https://hack.chat/) is a minimal, distraction-free, account-less, log-less, disappearing chat service that is easily deployable as your own service. The client comes bundled with LaTeX rendering provided by [KaTeX](https://github.com/Khan/KaTeX).

A list of software developed for the hack.chat framework can be found at the [3rd party software list](https://github.com/hack-chat/3rd-party-software-list) repository. This includes bots, clients, docker containers & more.

This is a backwards compatible continuation of the [work by Andrew Belt](https://github.com/AndrewBelt/hack.chat). The server code has been updated to ES6 along with several new features- including new commands and hot-reload of the commands/protocol.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

The following versions are __required__:

```
    node >= 8.10.0
    npm >= 5.7.1
```

An installation guide for your operating system can be found [here](https://nodejs.org/en/download/package-manager/).

### Installing

First you will first need to clone this git, if you are unfamiliar with this process read [cloning a repository](https://help.github.com/articles/cloning-a-repository/), or to clone with git:

```
git clone https://github.com/hack-chat/main.git
```

Once cloned, the server will need to be setup. Using your terminal run:

```
cd main/server/
npm install
```

Or on a Windows machine with Yarn installed:

```
cd main/server/
yarn install
```

This will install the required packages to run hack.chat. Next the server will need to be configured, again in your terminal run:

```
node main.js
```

The configuration script will execute the initial server setup by requesting input. Follow the steps until it finishes.

___Note:___ if you change the `websocketPort` option during the config setup then these changes will need to be reflected on [client.js](https://github.com/hack-chat/main/blob/master/client/client.js#L59).

After the config script runs, the process will exit & the server will need to be relaunched. For a production environment we recommend using [PM2](https://github.com/Unitech/pm2) to start the server:

```
cd main/server/
pm2 start main.js --name HackChat
```

Launch `main/client/index.html`, you may now begin development or deploy to production environment.

## Deployment

After the initial installation and configuration, push everything except the node_modules folder to the live server and re-run:

```
npm install
```

You can now run start the server software with a process manager like [PM2](https://github.com/Unitech/pm2). The client code will need to be copied into your http server directory. If you plan on using SSL to serve the client; you will need to use a reverse proxy, as TLS is not natively supported by the hack.chat server software (this may change in future releases).

## Authors

* **Marzavec** - *Initial work* - [marzavec](https://github.com/marzavec)
* **MinusGix** - *Base updates* - [MinusGix](https://github.com/MinusGix)

See also the list of [contributors](https://github.com/hack-chat/main/graphs/contributors) who participated in this project.

## License

This project is licensed under the [WTFPL License]((http://www.wtfpl.net/txt/copying/)).

## Acknowledgments

* Andrew Belt, https://github.com/AndrewBelt/hack.chat, for original base work
* [wwandrew](https://github.com/wwandrew/), for finding server flaws (including attack vectors) and submitting ~~___incredibly detailed___~~ bug reports

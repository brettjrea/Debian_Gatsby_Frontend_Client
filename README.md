#### Title: "Node.js and Build Tools Installation Guide with Optional OS Upgrades"

1. Optional OS upgrades:
   1. [Upgrade Debian Bullseye to Buster](https://github.com/brettjrea/Debian_Bullseye_Upgrade_Script)
   2. [Upgrade Ubuntu Focal to Jammy](https://github.com/brettjrea/Ubuntu_Jammy_Upgrade_Script)
   
2. Node.js tools:
   1. [Install NVM](https://github.com/brettjrea/Debian_Install_NVM) - Node Version Manager
   2. [Install NVS](https://github.com/brettjrea/Debian_Install_NVS) - Node Version Switcher (added 02/23 it is a cross-platform node based successor/replacement for NVM)
   
3. Build tools:
   1. [Install common build tools.](https://github.com/brettjrea/Debian_Install_Common_Build_Tools)
   
4. Frontends, Backends, Process Manager and GitHub CLI:
   1. [Install Strapi.io backend](https://github.com/brettjrea/Debian_Strapi_Backend_API)
   2. [Install Gatsby frontend](https://github.com/brettjrea/Debian_Gatsby_Frontend_Client)
   3. [Install PM2 Process](https://github.com/brettjrea/Debian_Configure_PM2)
   4. [Install GitHub CLI](https://github.com/brettjrea/Debian_Install_GitHub_CLI)
---
### Debian Gatsby Frontend Client

#### This new one fetches a script from this repo which is useful for using inside of another script.

```
sudo apt upgrade -y && sudo apt update -y && sudo apt autoremove -y &&
sudo apt install wget &&
sudo apt-get install --reinstall ca-certificates -y &&
wget https://raw.githubusercontent.com/brettjrea/Debian_Gatsby_Frontend_Client/main/install-gatsby.sh &&
chmod +x install-gatsby.sh &&
./install-gatsby.sh &&
sudo apt autoremove -y &&
sudo apt clean -y
```

```
cd ~/my-frontend && yarn deploy
```

I seperated the command to start development because I am using PM2 from the link above. ☝️ 

#### This is a copy-paste of the commands for those who dont want to use a script.
```
sudo apt upgrade -y && sudo apt update -y && sudo apt autoremove -y &&
npm install --global yarn &&
sudo apt install git -y &&
yarn global add typescript &&
yarn global add gatsby-cli &&
gatsby options set package-manager yarn &&
gatsby new my-frontend https://github.com/brettjrea/gatsby_typescript_styled_components &&
cd my-frontend &&
yarn add styled-components gatsby-plugin-styled-components babel-plugin-styled-components &&
yarn add -D @types/styled-components &&
yarn add gatsby-plugin-react-helmet-async react-helmet-async &&
yarn add gatsby-source-strapi &&
yarn add gatsby-source-graphql &&
yarn add gatsby-source-custom-api
```
```
cd my-frontend && yarn deploy
```

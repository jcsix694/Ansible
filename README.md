# MAC Ansible Setup

A tool using Ansible to setup your mac device.

## Prerequisites
Follow the steps below which will then allow you to run the `ansible` commands.

- In the App Store, make sure you are signed in (Account Settings > Sign In)
- Install XCode via the App Store
- Ensure Apple's command line tools are installed using the following command
  ```
  xcode-select --install
  ```
- Accept the XCode license agreement. Run the command
  ```
  xcodebuild -license
  ```
   and then, type agree at the end and press enter.
- Run the following command to add Python 3 to your ```$PATH```:
  ```
  export PATH="$HOME/Library/Python/3.8/bin:/opt/homebrew/bin:$PATH"
  ```
- Upgrade Pip:
  ```
  sudo -H pip3 install --upgrade pip
  ```
- Install Ansible
  ```
  pip3 install ansible
  ```

## Confriming Ansible is Installed
Run the command to return `ansible` information:
  ```
  ansible-playbook
  ```
If the above did not work and showed an error, follow these steps to fix:
- In a terminal, type in:
```
find ~/ -name ansible-playbook 2>/dev/null
```
- Copy the output, this will now be referenced as `OUTPUT` in any samples.
- In a terminal, type in:
```
nano ~/.zshrc
```
- Enter in the following:
```
export PATH=$PATH:OUTPUT
```
- Save & Close
- In a terminal, type in:
```
source ~/.zshrcsource ~/.zshrc
```
- Retry the following command to confirm ansible is working:
```
ansible-playbook
```

## Running Ansible
In a terminal, run the following command
```
ansible-playbook main_setup.yml -K
```
You will be prompted to enter your password. Once entered correctly, ansible will run to configure your mac device.

## Configuration
This ansible setup will configure the following on your mac device:
- brew (Homebrew)
- mas (Mac App Store CLI)
- Installs Mac App Store Apps:
  - Slack
  - NordLayer
- Creates a `development` folder located in the Documents path  
# Kava Testnet-14000

**Prerequisites:** Make sure to have [Golang >=1.17](https://golang.org/).

## Build from source

You need to ensure your gopath configuration is correct. If the following **'make'** step does not work then you might have to add these lines to your .profile or .zshrc in the users home folder:

```sh
nano ~/.profile
```

```
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export GO111MODULE=on
export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin
```

Source update .profile

```sh
source .profile
```

## Submit gentx

First, install Kava v0.16.0-alpha.0 binary

```sh
git clone https://github.com/Kava-Labs/kava.git
cd kava
git tag
git checkout v0.16.0-alpha.0
make install
```

This will build and install `kava` binary into `$GOBIN`.

Note: When building from source, it is important to have your `$GOPATH` set correctly. When in doubt, the following should do:

```sh
mkdir ~/go
export GOPATH=~/go
```

Check that you have the right Kava version installed:

```bash
 kava version
 0.16.0-alpha.0
```

## Setup validator node

Below are the instructions to generate & submit your genesis transaction

### Generate genesis transaction (gentx)

1. Initialize the Kava directories and create the local genesis file with the correct chain-id:

   ```bash
   kava init <YOUR_NODE_NAME> --chain-id kava-testnet-14000
   ```

2. Create a local key pair:

   ```bash
   kava keys add <YOUR_KEY_NAME>
   ```

3. Add `1000000000000ukava` to the account

   ```bash
   kava add-genesis-account $(kava keys show <YOUR_KEY_NAME> -a) 1000000000000ukava
   ```

4. Create the gentx, use only `900000000000ukava`:

   ```bash
   kava gentx <YOUR_KEY_NAME> 900000000000ukava --chain-id=kava-testnet-14000
   ```

5. If all goes well, you will see a message similar to the following:

   ```bash
     Genesis transaction written to "/home/ubuntu/.kava/config/gentx/gentx-******.json"
   ```

### Submit genesis transaction

- Fork [the testnets repo](https://github.com/Kava-Labs/kava-testnets) into your Github account

- Clone your repo using

  ```bash
  git clone https://github.com/<your-github-username>/kava-testnets
  ```

- Copy the generated gentx json file to `<repo_path>/14000/gentxs/`
- Commit and push to your repo
- Create a PR onto https://github.com/Kava-Labs/kava-testnets

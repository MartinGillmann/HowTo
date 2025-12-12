## Walkthrough: Install Github Action Runner on Raspberry 
(arm64/aarch64)

### 1) Find latest runner
```
https://github.com/actions/runner/releases
```
search for <b>Linux arm64</b>

### 2) make a folder and install the runner
```
sudo -i
cd /opt && mkdir git-action-runner && cd git-action-runner
curl -o actions-runner-linux-arm64-2.330.0.tar.gz -L https://github.com/actions/runner/releases/download/v2.330.0/actions-runner-linux-arm64-2.330.0.tar.gz
tar xzf ./actions-runner-linux-arm64-2.330.0.tar.gz
chmod -R 777 .
exit        --> exit sudo
```

### 3) Register runner with your github organisation
On Github go to 
Settings->Actions->Runners->New Runner->Selfhosted->Linux
to see your url and token
```
./config.sh --url https://github.com/<yours> --token <yours>
nohup ./run.sh > /dev/null 2>&1 &
nohub ./run.sh &
```

### 4) Verify
On Github go to 
Settings->Actions->Runners
You will see your Raspberry under runners with status Idle.








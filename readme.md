# Readme

## Setup
```
git clone --recurse-submodules https://github.com/stormmathisen/clara-chg-calibration.git
```

Setup a venv of your choice 
```
pip install -r requirements.txt
pyinstaller ./charge_front_end_cli/chg_fe_cli.spec

```

## Goals
1. Be able to read data from EPICS
2. Be able to send commands to front end via chg_fe_cli
3. Following algorithm:
```
For sensitivities 0...3:
    Set calibration mode
    For calibration levels 0...255:
        Get some n (100? 200?) shots of pk-pk value
        Calculate statistics (mean, std dev)
        Store statistics
    Convert calibration level to charge
    Linear fit of charge vs voltage
Store in yaml file
Save figures of fits
```
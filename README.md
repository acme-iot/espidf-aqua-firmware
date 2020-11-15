# ESP-IDF Aquaponic firmware

## Pre steps

#### Install PlatformIO

##### on mac,
1. download [get-platform.py](https://raw.githubusercontent.com/platformio/platformio-core-installer/master/get-platformio.py) anywhere
2. from wherever you downloaded `get-platform.py` run `python get-platformio.py`. Python2 is fine
3. run `python -c "import os; print(os.path.join(os.getenv('PLATFORMIO_CORE_DIR', os.path.join(os.path.expanduser('~'), '.platformio')), 'penv'))"` and note the output which is PlatformIO's virtual environment which we will use
4. copy the path from the last step and run `virtualenv ~/.platformio/penv
 && virtualenv -p python3 ~/.platformio/penv` 
5. now activate the venv, `. ~/.platformio/penv/bin/activate`
6. install PIO Core in the venv, `pip install -U platformio`

#### PlatformIO extension to VSCode
1. Just search for and install the extension `PlatformIO`
2. Open `settings.json` in VSCode (from the Command Palette type `Preferences Open Settings (JSON)`)
3. Add the following (inside `{...}`),
   ```
    "platformio-ide.customPATH": "~/.platformio/penv/bin",
    "platformio-ide.useDevelopmentPIOCore": false
   ```
    **note**, customPATH probably isn't necessary since we added it to the `PATH` 
4. Restart VSCode

#### Activate Virtual Environment
You will need to activate the venv when using `pio` 

1. (optional) add `export PATH=$PATH:~/.platformio/penv/bin` to `PATH` in (bash `~/.profile`) or (zsh `~/.zprofile`)
2. activate `PIO` using `. ~/.platformio/penv/bin/activate` or (if you did step 1) `. activate`
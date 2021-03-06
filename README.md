# Overview

[![Documentation Status](https://readthedocs.org/projects/eva-core/badge/?version=latest)](http://eva-core.readthedocs.io/en/latest/?badge=latest)

Eva is an open source alternative to Amazon Echo or Google Home.
The core of Eva is a simple service that provides hooks for plugins during interactions with users. On it's own, Eva does very little. It's potential comes from the [plugins](https://github.com/edouardpoitras/eva-plugin-repository) the user chooses to enable (or create).

# Installation

If you wish to use docker-compose to run Eva, ensure you have installed [Docker](https://docs.docker.com/engine/installation/) and the [docker-compose](https://docs.docker.com/compose/install/) utility.

If you wish to run Eva outside of Docker, install the required Python dependencies:

```
$ pip3 install -r requirements.txt
```

TODO: Allow for a proper pip install eva command.

# First Steps

To run Eva with docker-compose, you simply have to run the following command:

```
docker-compose up
```

Or, if running on an ARM-based device like the Raspberry Pi:

```
docker-compose -f docker-compose-arm.yml up
```

This may take a while on the first run as the Eva container is built and all the dependencies are installed.

To run Eva outside of Docker, you simply have to execute the `eva.directory.serve()` function. This is exactly what the `serve.py` does for you:

```
python3 serve.py
```

The default setting for Eva is to install the [Web UI Plugins](https://github.com/edouardpoitras/eva-web-ui-plugins) and [Web UI Updater](https://github.com/edouardpoitras/eva-web-ui-updater) plugins (and their dependencies) on first startup. This behaviour can be changed by modifying the core Eva [configuration](https://eva-core.readthedocs.io/en/latest/configuration.html) file (typically found at `~/eva/eva.conf`).

Alternatively, once Eva is started, you may navigate to the Web UI (https://localhost:8080) and enable/disable plugins as needed. Note that a self-signed certificate warning from your browser is normal at this point.

While you're in the Web UI, you may as well download and enable the [Web UI Interact](https://github.com/edouardpoitras/eva-web-ui-interact) plugin which will allow you to test out Eva from the Web UI.

We discuss Eva clients more in depth on the [clients documentation](https://eva-core.readthedocs.io/en/latest/clients.html) page.

At this point Eva's capabilities are entirely controlled by the plugins enabled by the user. Try enabling the [echo](https://github.com/edouardpoitras/eva-echo) plugin and see if Eva echos back the commands you send it. Also try the [weather](https://github.com/edouardpoitras/eva-weather) plugin and ask Eva for the current forecast (you'll need to setup DarkSky API keys)

Note: You will need to have enabled a voice recognition plugin if you wish to speak to Eva instead of using text commands.

Note: You will need to enable a Text-to-Speech plugin if you wish to receive spoken words from Eva as a response.

# Plugin Development

Please see the [plugin development guide](https://eva-core.readthedocs.io/en/latest/plugin_development.html) for more information on how to make Eva awesome (hint: it's easy). Also check out the source code of some of the plugins mentioned in this README.

# Disclaimer

Eva is still a VERY young project. Please help us make it better by submitting feature requests and [issues](https://github.com/edouardpoitras/eva/issues) when discovered.

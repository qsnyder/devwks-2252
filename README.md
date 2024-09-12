# DEVWKS2252 | Device Compliance and Lifecycle Using Ansible

This repository serves as a landing page for the code used within the DEVWKS2252 workshop at CiscoLive events.

A recording of this event is available on the CiscoLive OnDemand website by searching for "Quinn Snyder" and scrolling down to **Melbourne 2022**.  Alternatively, [this link](https://www.ciscolive.com/on-demand/on-demand-library.html?search=quinn%20snyder#/session/1670019658356001nEmE) will take you to the search query.
This video should provide a comprehensive walkthrough of the sample code provided in this repository.

For all non-event related activities/exploration, you'll need to reserve and establish a VPN connection to one of the CML sandboxes withing [Cisco DevNet](https://developer.cisco.com).  

- [Cisco Modeling Labs Sandbox](https://devnetsandbox.cisco.com/DevNet/catalog/cml-sandbox_cml) can be found here
- Alternatively, you can utilize the NSO sandbox, which does not provide access to the underlying Cisco Modeling Labs topology, but follows the same IP addressing schema.  This sandbox can be found [here](https://devnetsandbox.cisco.com/DevNet/catalog/nso-sandbox_nso)

From there, the compliance lifecycle can be executed using the sequentially numbered Ansible playbooks (starting with "10").  You will need to ensure that the basic Python requirements are met.  Included is the requirements.txt file which can be installed within a virtual environment using the following:

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

You will also need to install the appropriate collections from Ansible Galaxy.  This can be done using the following command:

```bash
ansible-galaxy collection install cisco.ios
ansible-galaxy collection install cisco.nxos
```

If you have previously installed these collections, you may need to perform an update if you receive unexpected output from the connection to the devices in the sandbox.  This can be done using the following command:

```bash
ansible-galaxy collection install --upgrade cisco.ios
ansible-galaxy collection install --upgrade cisco.nxos
```

It is also recommended to use a Python installation not tied to the system Python installation (which is generally updated as part of the macOS/`apt`/`yum` process).  This can be easily implemented using something like `pyenv`, which can be found [here](https://github.com/pyenv/pyenv), but the installation of which is considered out of scope for this README.

## Note for Snack Minute Episode 92 Viewers

This is the foundational repository that was used during the recording of Snack Minute Episode 92.  The majority of that episode focused on the use of "check mode" (using `-C` within the command-line of a playbook to perform a "dry run") with the [`20-tags.yaml`](./20-tags.yaml) playbook, using the set of tags within that playbook, and using the configuration rendering functionality within Ansible and the [`40-render.yaml`](./40-render.yaml) playbook.

You will still need a reservation to a CML sandbox (or use your own with modifications to the Ansible inventory file), as well as a Python environment with the pre-requisites given in the [`requirements.txt`](./requirements.txt) file, both of which are mentioned above.

## Updates to thie README

Updates and additional discussions around each of the files will be coming as time permits.

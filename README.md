# DEVWKS2252 | Device Compliance and Lifecycle Using Ansible

This repository serves as a landing page for the code used within the DEVWKS2252 workshop at CiscoLive events.

For all non-event related activities/exploration, you'll need to reserve and establish a VPN connection to one of the CML sandboxes withing [Cisco DevNet](https://developer.cisco.com).  

- CML - Large Topology Sandbox (max reservation is 4 hours) can be found [here](https://devnetsandbox.cisco.com/RM/Diagram/Index/685f774a-a5d6-4df5-a324-3774217d0e6b?diagramType=Topology)
- CML - Small Topology Sandbox (max reservation is 2 days) can be found [here](https://devnetsandbox.cisco.com/RM/Diagram/Index/45100600-b413-4471-b28e-b014eb824555?diagramType=Topology)

From there, the compliance lifecycle can be executed using the sequentially numbered Ansible playbooks (starting with "10").  You will need to ensure that the basic Python requirements are met.  Included is the requirements.txt file which can be installed within a virtual environment using the following:

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

It is also recommended to use a Python installation not tied to the system Python installation (which is generally updated as part of the macOS/`apt`/`yum` process).  This can be easily implemented using something like `pyenv`, which can be found [here](https://github.com/pyenv/pyenv), but the installation of which is considered out of scope for this README.

## Note for Snack Minute Episode 92 Viewers

This is the foundational repository that was used during the recording of Snack Minute Episode 92.  The majority of that episode focused on the use of "check mode" (using `-C` within the command-line of a playbook to perform a "dry run") with the [`20-tags.yaml`](./20-tags.yaml) playbook, using the set of tags within that playbook, and using the configuration rendering functionality within Ansible and the [`40-render.yaml`](./40-render.yaml) playbook.

You will still need a reservation to a CML sandbox (or use your own with modifications to the Ansible inventory file), as well as a Python environment with the pre-requisites given in the [`requirements.txt`](./requirements.txt) file, both of which are mentioned above.

## Updates to thie README

Updates and additional discussions around each of the files will be coming as time permits.
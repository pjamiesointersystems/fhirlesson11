# FHIR Lesson 11: Working with FHIR Resources Using Python

This repository contains educational materials and example code for **Lesson 11** of the *Vanderbilt Local FHIR Training* series. The lesson is focused on using the [`fhir.resources`](https://github.com/nazrulworld/fhir.resources) Python library to work with HL7® FHIR® data formats in JSON, specifically to parse, validate, and construct FHIR resource objects in Python.

---

## 🧠 Learning Objectives

By the end of this lesson, you will be able to:

1. ✅ Understand how to install and use the `fhir.resources` Python library.
2. 📥 Parse (unmarshal) JSON-encoded FHIR data into FHIR resource objects.
3. 📤 Construct (marshal) FHIR resource objects into JSON for posting to a server.
4. 🧰 Practice basic object-oriented programming patterns for working with FHIR resource classes.

---

## 🔧 Environment Setup


To isolate your dependencies and avoid package conflicts, create a virtual environment:

# We are moving to using the uv package manager for python virtual environments and installation of packages
# on mac os run the following command at the terminal

```
# download and install uv
curl -Ls https://astral.sh/uv/install.sh | sh

```
# verify installation
uv --version

# for windows installation of uv teh recommended way is to use PowerShell
```
irm https://astral.sh/uv/install.ps1 | iex

# if script execution is blocked
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

# then verify installation
uv --version

# once installed, you can immediately use uv
uv venv

# activate it on macOS/Linux

source .venv/bin/activate

# on windows
.venv\Scripts\activate

#if command not found restart the terminal



```bash
# Create the virtual environment
python3 -m venv myenv



# Activate it (Windows)
myenv\Scripts\activate

# Activate it (macOS/Linux)
source myenv/bin/activate

from fhir.resources.patient import Patient
import json

with open("example_patient.json") as f:
    data = json.load(f)

patient = Patient(**data)
print(patient.name[0].family)

fhirlesson11/
├── example_patient.json         # Sample FHIR Patient JSON
├── requirements.txt             # Python dependencies
├── myenv/                       # (optional) Virtual environment directory
└── ...                          # Additional scripts or resources


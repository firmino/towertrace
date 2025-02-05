# TowerTrace
[![image](https://img.shields.io/pypi/v/ruff.svg)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/downloads/)

TowerTrace is a Python library for tracking metadata and collecting telemetry from agents. It provides a set of annotations and utilities to instrument your Python projects and send telemetry data to a central server.

---

## Table of Contents
1. [Installation](#installation)
2. [Quick Start](#quick-start)
3. [Configuration](#configuration)
4. [Support](#support)
5. [Contributing](#contributing)
6. [License](#license)

---

## 1. Installation
To install TowerTrace, use `uv` or `pip`:

```bash
# Using uv
uv pip install towertrace

# Using pip
pip install towertrace

```

## 2. Quick Start
### Step 1: Import and Configure
```python
from towertrace import TowerTrace, trace_function

# Initialize TowerTrace
tracer = TowerTrace(server_address="http://localhost:50051")
```

### Step 2: Annotate Your Functions
Use the @trace_function decorator to track metadata and telemetry:

```python
@trace_function
def my_function():
    print("Hello, TowerTrace!")
```

### Step 3: Send Telemetry Data
Manually send telemetry data using the send_telemetry method:

```python

tracer.send_telemetry(
    agent_id="agent_123",
    metric_name="cpu_usage",
    value=75.5,
    timestamp=1697049600,
)
```

## 3. Configuration
TowerTrace can be configured using environment variables or directly in your code:

### Environment Variables

**TOWERTRACE_SERVER_ADDRESS**: The address of the telemetry server (default: http://localhost:50051).

**TOWERTRACE_AGENT_ID**: The unique ID of the agent (default: hostname).

### In-Code Configuration
```python
from towertrace import TowerTrace

tracer = TowerTrace(
    server_address="http://localhost:50051",
    agent_id="my_custom_agent_id",
)
```
## 4. Support
If you have any questions or need help, feel free to open an issue on the GitHub repository.

## 5. Contributing

We welcome contributions from the community! If you'd like to contribute, please follow these steps:

1. **Fork the repository**  and clone it to your local machine.
```sh
git clone https://github.com/yourusername/towertrace.git
cd towertrace
```

2. **Create a new branch** for your changes.
```sh
git checkout -b my-feature-branch
```

3. Make your changes and ensure they follow the **Style Guide**.

4. **Test your changes** to ensure they work as expected

5. **Commit your changes** with a clear and descriptive commit message.
```sh
git commit -m "Add feature: describe your changes"
```

6. **Push your changes** to your forked repository.
```sh
git push origin my-feature-branch
```

7. **Open a Pull Request (PR)** against the main branch of the original repository. Include:
+ A clear description of the changes.
+ References to related issues (e.g., "Fixes #123").
+ Screenshots or test results (if applicable).


## 6. License 
TowerTrace is licensed under the MIT License. By using this library, you agree to the terms of the license.
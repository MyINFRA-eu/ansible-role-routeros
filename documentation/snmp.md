# SNMP Tasks

Manage snmp settings and communities

## Tags

- routeros_snmp

## Settings

All settings from the routeros cli are available as a setting, if none is provided default values will be used.

> Values from the default section will be overwritten with specific device settings


## Full config example

```yaml
routeros_snmp:
  default:
    enabled: yes
    contact: "info@localhost"
    location: "Default Location"
    communities:
      snmpcom:
        comment: "Test 1"
        address:
          - 127.0.0.2
        disabled: "no"
        read-access: "yes"
        write-access: "no"
      snmpcom2:
        comment: "Test 2"
        addresses:
          - 127.0.0.3
        disabled: "yes"
        read-access: "yes"
        write-access: "yes"
  device1:
    contact: "mgmt@device1.local"
    location: "Test Location 123"
    communities:
      com1:
        addresses:
          - 127.0.0.21
          - 127.0.0.22
        disabled: "no"
        comment: "Test community 1"
      com2:
        comment: "Testing with no values"
  device2:
    location: "Test Location ABC",
    communities:
      libre:
        addresses:
          - 127.0.0.31
        disabled: "no"
```

```json
"routeros_snmp": {
  "default": {
    "enabled": "yes",
    "contact": "info@localhost",
    "location": "Default Location",
    "communities": {
      "snmpcom": {
        "comment": "Test 1",
        "addresses": [
          "127.0.0.2"
        ],
        "disabled": "no",
        "read-access": "yes",
        "write-access": "no"
      },
      "snmpcom2": {
        "comment": "Test 2",
        "addresses": [
          "127.0.0.3"
        ],
        "disabled": "yes",
        "read-access": "yes",
        "write-access": "yes"
      }
    }
  },
  "device1": {
    "contact": "mgmt@device1.local",
    "location": "Test Location 123",
    "communities": {
      "com1": {
        "addresses": [
          "127.0.0.21",
          "127.0.0.22"
        ],
        "disabled": "no",
        "comment": "Test community 1"
      },
      "com2": {
        "comment": "Testing with no values"
      }
    }
  },
  "device2": {
    "location": "Test Location ABC",
    "communities": {
      "libre": {
        "addresses": [
          "127.0.0.31"
        ],
        "disabled": "no"
      }
    }
  }
},
```
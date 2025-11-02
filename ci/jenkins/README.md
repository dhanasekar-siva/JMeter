# Jenkins JMeter Pipeline
This Jenkins pipeline automates the execution of Apache JMeter performance tests directly from Jenkins.
It supports both Windows and Linux/Unix agents and can be configured for local or remote (distributed) JMeter test execution.

## Features
- Works on Windows (.bat) and Linux (.sh)
- Supports parameterized builds for flexible configuration
- Validates paths and parameters before execution
- Archives test results automatically in Jenkins
- Keeps build logs clean with timestamps and retention policies

## Pipeline Overview
| Stage | Description |
|-------|-------------|
| **Setup JMeter PATH** | Adds the JMeter bin directory to the system path |
| **Input Parameter Validation** | Ensures that key user-supplied parameters are valid |
| **Execute Test** | Runs the specified JMeter script via the command line |
| **Archive Test Results** | Copies `.jtl` results into the Jenkins workspace and archives them as build artifacts |

## Pipeline Parameters
| Name | Description |
|------|-------------|
| **JMeter_Path** | Path to JMeter’s bin directory |
| **Script_Path** | Full path to the JMeter test plan (.jmx file) |
| **Application_Name** | Name of the application under test |
| **Result_Directory** | Directory where JMeter should output result logs (.jtl files) |
| **LG_IP_Address** | Optional. Specify remote Load Generator IP if using distributed testing as a comma separated value |

## Future Enhancements
- Genarate aggregate report at end of test
- Archive test results in the cloud storage like AWS S3
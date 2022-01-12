This is the readme regarding the tests performed on the modified OpenWhisk platform, and how to replicate them. This folder is not part of the OpenWhisk deployment on kubernetes.

To deploy the functions:
- the various test cases are under `test-code`
- each of them contains an `openwhisk` folder
- for nodejs-based tests, run `npm install`
- after this, run `sls deploy`


To perform the tests:
- the tests require JMeter and are in the form of JMeter templates
- to perform them using JMeter, run `jmeter -n -t <template_name> -Jroot=<root folder> -Jip=<cluster ip> -Jcounter="<number of repetition>"`
- for tests under the `modified` folder, the `Jpolicy` parameter is required
- for the `terrain` test, the `Jhost` parameter is required
- for the `slackpost` test, the `Jslackpath` parameter is required
- for the `mongoDB` and `data-locality` test, the `Jdbip`, `Jusername`, `Jpassword`, `Jdbname` parameters are required
- for `terrain`, `mongoDB` and `data-locality` tests using the modified version, the `Jtag` and `Jtolerance` parameters are required

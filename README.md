# cloudformer-node

A port of the Ruby AWS CloudFormation tooling [https://github.com/kunday/cloudformer](https://github.com/kunday/cloudformer) and a fork of cloudformer-node npm package [https://github.com/Michael-Gannon/cloudformer-node](https://github.com/Michael-Gannon/cloudformer-node)

Cloudformer attempts to simplify AWS Cloudformation stack creation process in NodeJS projects by providing reusable operations such as apply(create/update), delete, recreate on stack along with validations on templates. Task executions which enforce a stack change will wait until ROLLBACK/COMPLETE or DELETE is signalled on the stack (useful in continuous deployment environments to wait until deployment is successful).

This forked repository is intended to be used in conjunction with an Alexa Enabled Device and AWS Lambda, and the code has been adjusted accordingly to cater towards the limitations of both services.


## Installation:

## JS Usage:

```
js
var stack = new Stack('tooling-test');
stack.apply('./samples/basic_template.json', {
  Parameters: { AmiId: 'ami-fd9cecc7' },
  DisableRollback: false,
  Capabilities: [],
  NotificationARNs: [],
  Tags: { Name: 'mystack' }
}, console.log);

stack.outputs(console.log);

stack.delete(console.log);
```

## CLI Usage:
```
bash
  stack-apply -h
  stack-outputs -h
  stack-delete -h
```

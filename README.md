Concourse Job Parameters Resource
---------------------------------

This resource can trigger jobs with parameters using a simple url

Format
------

```
[
	{
		"ref": "launch 2",
		"params": {
			"my_param_1": 80,
			"PARAM2": "hello"
		}
	},
	{
		"ref": "launch 1",
		"params": {
			"my_param_1": 100,
			"PARAM2": "hello world"
		}
	}
]
```

Sample pipeline
---------------

    echo y | fly -t lite set-pipeline -p job-parameters-demo -c sample/pipeline.yaml
    fly -t lite unpause-pipeline -p job-parameters-demo

    echo y | fly -t lite destroy-pipeline -p job-parameters-demo

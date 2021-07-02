# How to get this thing`y going:

To avoid having a .vscode/launch.json file in every top level of a multi root workspace (here: only one, but you get the point),  
add the 'launch' config as shown below.


```{
	"folders": [
		{
			"path": "."
		},
		{
			"path": "src/app"
		}
	],
	"settings": {},
	"launch": {
		"version": "0.2.0",
        // this is the setup when using debug from the vs-code-extension: orta.vscode-jest
		"configurations": [
            {
                "type": "node",
                "name": "vscode-jest-tests",
                "request": "launch",
                "console": "integratedTerminal",
                "internalConsoleOptions": "neverOpen",
                "disableOptimisticBPs": true,
                "program": "node_modules/.bin/jest",
                "cwd": "${workspaceFolder}/../../",
                "args": [
                    "--config",
                    "jest-config.json",
                    "--runInBand",
                    "--watchAll=false"
                ]
            }
        ]
	}
}
```

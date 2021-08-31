# Dynatrace Monitoring as Code Github action

Documentation on monaco: [monaco](https://github.com/dynatrace-oss/dynatrace-monitoring-as-code)

## Usage

### GitHub Actions
```
jobs:
  monaco_deploy:
    environment: ${{ github.event.inputs.environment }}
    runs-on: [self-hosted, kroger, tsa]
    steps:
      - uses: tylerstewart2/monaco-github-action@v1.1
        with:
          url: ${{ secrets.URL }}
          token: ${{ secrets.API_TOKEN }}
          project: ${{ PROJECT_NAME }}
```

Please ensure URL and API_TOKEN are set as secrets in your repo!

This github action requires you to set up a standard directory in your repo called monitoring-as-code. Directory Structure should look like this:

```
├── monitoring-as-code # root dir needed for github action
│   ├── environments.yaml
│   ├── project_name_dir
│       ├── config_type
│           ├── config.yaml
│           ├── config.json
└── ...
```

More info on directory structure and usage for Monaco: https://dynatrace-oss.github.io/dynatrace-monitoring-as-code/

### Dependencies

[wei/curl](https://github.com/wei/curl)

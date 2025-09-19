# Dotnet

## Override a value in appsettings.json with environment variable

To override application config using environment variables, use the following naming convention:

```bash
# For this appsettings.json file: {"MyService": {"Enabled": "false"}}

# Use an override for MyService.Enabled:
# (Note the double underscore used instead of colon in env variable name)
MyService__Enabled="true" dotnet run --project MyProject 

# Use defaults from appsettings.json:
dotnet run --project MyProject
```
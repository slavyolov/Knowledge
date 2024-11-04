- Work with the CLI
	- psql --host=<HOST_NAME>  --username=<USER_NAME> --dbname=<DATABASE_NAME>
	- Commands :
		- https://www.commandprompt.com/education/postgresql-basic-psql-commands/

- json and jsonb - https://stackoverflow.com/a/22910602
	- `jsonb` usually takes more disk space to store than `json` (sometimes not)
	- `jsonb` takes more time to build from its input representation than `json`
	- `json` operations take _significantly_ more time than `jsonb` (& parsing also needs to be done each time you do some operation at a `json` typed value)
# ELK Stack: Docker Compose

## Requirements
- Docker
- Docker Compose CLI
- Python3.10+
- Pip

## Start the log application
```bash
# create a virtual environment
python -m venv venv
source venv/bin/activate
pip install faker

# run app
python log_generator.py

```

## What it do?
It will create a file in root where will have all fake logs to be collected by Filebeat and put it in Logstash to be parsed and write in Elasticsearch. To finally see everything on Kibana.

## Running Stack
After that, just for this exploration, copy the `logs.log` content into `noSpoon.log` and do the follow command:

```bash
docker-compose up -d
```

## Access Kibana

Go to your web brownser and paste the url: `http://localhost:5601/`

And taram! Kibana is working, now let's configure our new index patter.

At Kibana UI, go to:

- `Stack Management` > `Index Management`
    - See if exists any index called: `filebeat-7.17*`
    - If yes, go ahead...
- Now go to: `Index Patters` > `Create a Index Patte`r > Write `fi*`
    - In the drop-down, select `@timestamp` and create it.
- Now, do ahed to `Discover` and see if everything works (your logs are there\o/)

That's it! Happy fun.
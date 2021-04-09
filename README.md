<p align="center">
    <table style="border-collapse: collapse; border: none;">
        <tr style="border-collapse: collapse; border: none;">
            <th style="border-collapse: collapse; border: none;">
                <img src="https://raw.githubusercontent.com/lalitpagaria/obsei/master/images/logos/obsei_200x200.png" width="100" height="100" />
            </th>
            <th style="border-collapse: collapse; border: none;">
                <h1>Obsei-rest: Rest API interface for Obsei</h1>
            </th>
        </tr>
    </table>
</p>


<p align="center">
    <a href="https://github.com/lalitpagaria/obsei-rest/actions">
        <img alt="CI" src="https://github.com/lalitpagaria/obsei-rest/workflows/CI/badge.svg?branch=master">
    </a>
    <a href="https://github.com/lalitpagaria/obsei-rest/blob/master/LICENSE">
        <img alt="License" src="https://img.shields.io/github/license/lalitpagaria/obsei-rest?color=blue">
    </a>
    <a href="https://pypi.org/project/obsei">
        <img src="https://img.shields.io/pypi/pyversions/obsei" alt="PyPI - Python Version" />
    </a>
    <a href="https://github.com/lalitpagaria/obsei-rest/commits/master">
        <img alt="Last commit" src="https://img.shields.io/github/last-commit/lalitpagaria/obsei-rest">
    </a>
    <a href="https://github.com/lalitpagaria/obsei-rest/issues">
        <img alt="Open Issues" src="https://img.shields.io/github/issues/lalitpagaria/obsei-rest">
    </a>
</p>

This is rest api playground on Obsei.

## Rest interface
Start docker with default configuration file:
```shell
docker run -d --name obesi -p 9898:9898 lalitpagaria/obsei-rest:latest
```
Start docker with custom configuration file (Assuming you have configfile `config.yaml` at `/home/user/obsei/config` at host machine):
```shell
docker run -d --name obesi -v "/home/user/obsei/config:/home/user/config" -e "OBSEI_CONFIG_PATH=/home/user/config" -e "OBSEI_CONFIG_FILENAME=config.yaml" -p 9898:9898 lalitpagaria/obsei:latest
```
Start docker locally with `docker-compose`:
```shell
docker-compose up --build
```
Following environment variables are useful to customize various parameters -
- `OBSEI_CONFIG_PATH`: Configuration file path (default: ../config)
- `OBSEI_CONFIG_FILENAME`: Configuration file name (default: rest.yaml)
- `OBSEI_NUM_OF_WORKERS`: Number of workers for rest API server (default: 1)
- `OBSEI_WORKER_TIMEOUT`: Worker idle timeout in seconds (default: 180)
- `OBSEI_SERVER_PORT`: Rest API server port (default: 9898)
- `OBSEI_WORKER_TYPE`: Gunicorn worker type (default: uvicorn.workers.UvicornWorker)

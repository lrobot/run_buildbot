
ref from https://github.com/buildbot/buildbot-docker-example-config

add db.env and .env file to simple dir, like below
cat simple/db.env
# database parameters are shared between containers
POSTGRES_PASSWORD=change_me
POSTGRES_USER=buildbot
POSTGRES_DB=buildbot
# in master.cfg, this variable is str.format()ed with the environment variables
BUILDBOT_DB_URL=postgresql+psycopg2://{POSTGRES_USER}:{POSTGRES_PASSWORD}@db/{POSTGRES_DB}
cat simple/.env
BUILDBOT_ENV_WORKER_PASS=change_me

edit master.cfg
and go to simple dir and run docker-compose up


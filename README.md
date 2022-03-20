# Wordpress-docker-gcp
dockerfile - wordpress -google cloud run


Deploy steps :

1 - Build image
gcloud builds submit --tag gcr.io/[PROJECT-ID]/[NAME SERVECE]:v1


2 - Deploy image: 

gcloud beta run deploy wp --image gcr.io/[PROJECT-ID]/[NAME SERVECE]:v1 \
--add-cloudsql-instances <instance-name> \
--update-env-vars DB_HOST='127.0.0.1',DB_NAME=<dbname>,DB_USER=<dbuser>,DB_PASSWORD=<dbpass>,CLOUDSQL_INSTANCE='<project.id>:<region>:<instance-name>'




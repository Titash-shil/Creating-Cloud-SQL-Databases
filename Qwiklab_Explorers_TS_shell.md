# [Creating Cloud SQL Databases](https://www.cloudskillsboost.google/course_templates/145/labs/387208)

# # Like, comment, share & Don't forget to subscribe [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN) 👍😄🤝

### Run the following Commands in CloudShell

```
export ZONE=
```

```
gcloud services enable sqladmin.googleapis.com --project=$DEVSHELL_PROJECT_ID

gcloud sql instances create postgresql-db --zone=$ZONE --database-version=POSTGRES_14 --tier=db-custom-1-3840 --root-password=awesome --edition=ENTERPRISE

gcloud sql databases create petsdb --instance=postgresql-db

gcloud sql instances create mysql-db --tier=db-n1-standard-1 --zone=$ZONE

gcloud compute instances create test-client  --zone=$ZONE --image-family=debian-11 --image-project=debian-cloud --machine-type=e2-micro

INSTANCE_NAME="mysql-db"
EXTERNAL=$(gcloud compute instances list --format='value(EXTERNAL_IP)')

gcloud sql instances patch $INSTANCE_NAME --authorized-networks=$EXTERNAL --quiet

INSTANCE_NAME="mysql-db"
PUBLIC_IP=$(gcloud sql instances describe $INSTANCE_NAME --format="value(ipAddresses.ipAddress)")

gcloud sql instances patch $INSTANCE_NAME --authorized-networks=$EXTERNAL --quiet

gcloud compute ssh test-client --zone=$ZONE --quiet --command "sudo apt-get update && sudo apt-get install -y default-mysql-client && mysql --host=$PUBLIC_IP --user=root --password"

```

# Congratulations ..!!🎉  You completed the lab shortly..😃💯

# *Well done..!* 👏

# Thank you for visiting.... :) 🗯️

# [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN)

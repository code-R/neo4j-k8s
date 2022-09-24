export CLOUDSDK_CORE_PROJECT="tilda-trial-automation" \
export CLOUDSDK_COMPUTE_REGION="us-central1" \
export CLOUDSDK_COMPUTE_ZONE="us-central1-a" \
export CLOUDSDK_CONTAINER_CLUSTER="my-neo4j-gke-cluster"

gcloud compute disks create --size 20Gi --type pd-ssd "core-disk-1" \
gcloud compute disks create --size 20Gi --type pd-ssd "core-disk-2" \
gcloud compute disks create --size 20Gi --type pd-ssd "core-disk-3"

helm install core-1 neo4j-cluster-core -f neo4j-cluster-core/core1.yaml \
helm install core-2 neo4j-cluster-core -f neo4j-cluster-core/core2.yaml \
helm install core-3 neo4j-cluster-core -f neo4j-cluster-core/core3.yaml

# xcraft_kubeconfig


1. gcloud config set project xcraft
2. gcloud compute project-info add-metadata --metadata google-compute-default-region=europe-west2,google-compute-default-zone=europe-west2-c
3. kubectl apply -f db-storage.yaml
4. kubectl apply -f odoo-storage.yaml
5. kubectl apply -f odoo.yaml

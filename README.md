# How to remove unnecessary files:
```
for d in 10-vpc/ 20-sg/ 30-bastion/ 40-eks/ 50-ecr/; do
  echo "Removing from $d:"
  echo "  $d/.terraform"
  echo "  $d/.terraform.lock.hcl"

  rm -rf "$d/.terraform" "$d/.terraform.lock.hcl"

  echo "Deleted files from $d"
done
```

# Infrastructure creation and deletion
```
for i in 10-vpc/ 20-sg/ 30-bastion/ 40-eks/ 50-ecr/ ; do cd $i; terraform init ; cd .. ; done 
```
```
for i in  10-vpc/ 20-sg/ 30-bastion/ 40-eks/ 50-ecr/  ; do cd $i; terraform plan; cd .. ; done 
```
```
for i in  10-vpc/ 20-sg/ 30-bastion/ 40-eks/ 50-ecr/  ; do cd $i; terraform apply -auto-approve; cd .. ; done 
```
```
for i in 50-ecr/ 40-eks/ 30-bastion/ 20-sg/ 10-vpc/; do cd $i; terraform destroy -auto-approve; cd .. ; done 
```




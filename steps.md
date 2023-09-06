# Create a deployment file.

    vim deployment.yml

    cat deployment.yml

<img width="453" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/4023cfbe-20a4-49dd-bc09-20d7fbc9fecb">

# Dry run the deployment file.

    kubectl apply -f deployment.yml --dry-run=client

  It will run the deployment file without creating a deployment.

  <img width="453" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/7966e7f9-f79f-4bc8-a490-8dc979a3c54e">

# View the deployment file after fixing the errors.

    cat deployment.yml

  <img width="440" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/95c69654-6f99-4038-a8ec-270258d02f0a">

# Create a namespace.

    kubectl create namespace mysql-ns

  <img width="537" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/e4bcf269-33f1-4cdd-a9cd-110323727d22">

# Applying the deployment file.

    kubectl apply -f deployment.yml

  <img width="537" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/37860dc0-5c57-44ff-9a88-433a26cf9ec8">

# View the pods created by deploymwent

    kubectl get pods -n mysql-ns

  <img width="506" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/f2fb71a3-3e43-479f-baf4-8410962b9aa2">

 Status = CrashLoopBackOff as the container is crashing inside the pod (Mysql requires Database and password)

 # Create a configMaps file to store the database value.

     vim configMaps.yml

     cat configMaps.yml

  <img width="496" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/e1cd3339-508f-4ac4-a202-8c6ed45319b6">

# Dry-run configMaps file

    kubectl apply -f configMMaps.yml --dry-run=client

  <img width="680" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/cf202702-9523-44d2-90eb-2598aa1bc387">

# View configMaps file after fixing the errors.

    cat configMaps.yml

  <img width="458" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/039fa57f-8cb3-4e37-9ed7-be342074db63">

# Applying configMaps file

    kubectl apply -f configMaps.yml

  <img width="458" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/ef490279-3198-44c1-af0b-f8ee5ff03342">

# View configMaps

    kubectl get configMaps -n mysql-ns

  <img width="570" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/4193a6b0-f5b5-4ba2-b526-4458c3658cde">

# Now edit the deployment file and view it after editing.

    vim deployment.yml

    cat deployment.yml

  <img width="488" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/63506f2f-e8e4-4d7e-9815-1a8ca9aa2ebd">

# Applying the deployment file after editing.

    kubectl apply -f deployment -n mysql-ns

<img width="531" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/8e67bc93-1319-40f0-81b6-04edbb888462">

# Now create a secrets file to store encoded passwords.

    vim secrets.yml

  <img width="442" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/d9c75ef4-cb60-4f94-b6b8-b76ec398a0b9">

# Apply and view the status of the secrets.yml file

    kubectl apply -f secrets.yml

    kubectl get secrets -n mysql-ns

  <img width="533" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/62f9d9d6-f8c4-41c4-96b0-0ec8d389b229">

# View deployment after change.

    vim deployment.yml    

  <img width="530" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/0643e52f-45ea-4ea8-8765-aece0c48a5cd">


# Apply deployment after changes.

     kubectl apply -f deployment.yml

  <img width="532" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/d79efd8d-928a-47f5-b1a8-35d248c25d0e">

# View status of the pods.

    kubectl get pods -n mysql-ns

  <img width="512" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/7c550653-3827-4d6a-a05f-206f2067f1f4">

# Create persistent volume file

    vim persistentVolume.yml

  <img width="517" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/737838d8-6d01-4e65-93fa-604995a2931b">

# Apply persistentVolume.yml

    kubectl apply -f persistentVolume.yml

  <img width="566" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/d3a6f38c-1b97-484c-8876-91acae8cbd45">

# Status of the persistent Volume

    kubectl get pv -n mysql-ns

  <img width="844" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/8bd4155a-c241-41da-977d-afda106193c8">
 Persistent volume is available and need to be claimed.

# Create persistentVolumeClaim file

    vim persistentVolumeClaim.yml

  <img width="532" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/3f105697-f935-409c-aaa5-0b1c467d0869">

# Applying the persistenVolumeClaim file.

    kubectl apply -f persistentVolumeCLaim.yml 

  <img width="609" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/2445007b-8a92-4b30-aad9-2732ac7e815c">

# Status of persistenVolumeClaim

    kubectl get pvc -n mysql-ns

  <img width="556" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/a8e7bab7-bd4c-45d7-96e2-b0c73aa517e4">


# Edit and view deployment after changes.

    cat deployment.yml

<img width="453" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/fc838ba7-6672-44de-acc7-6c450c0b9695">

# Applying the deployment file after changes.

    kubectl apply -f deployment.yml

<img width="500" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/cf435f3b-3d99-4000-9638-91c293eaec97">

# Go to worker node and check the mysql container

    docker ps

<img width="853" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/cd105faa-2759-4090-a283-c0613210b9ce">

# Enter into the sql container.

    docker exec -it e032ff06ddc3 bash

<img width="623" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/2c528170-c470-4f4a-853f-720051bba80e">

Enter the password encoded in the secrets file

# View database created by configMaps file

    show databases;

<img width="321" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/bd5b1609-33b7-41f6-8567-d353a1209504">

Database my-db has been created.

# Check the volume mounted in persistent volume file

    ls 

<img width="785" alt="image" src="https://github.com/ManishNegi963/mysql_database_with_k8s/assets/124788172/0fa6ec8b-4a7d-4edc-86ce-ceb0e11d036f">

All the file from the container is now also stored in the worker node. 

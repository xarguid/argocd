Argocd conf which produces a mariadb galera cluster.

heiki@heiki-MacBookPro11-3:~/Documents/argocd$ kubectl get mariadb,pods,pvc
NAME                                     READY   STATUS    PRIMARY            UPDATES                    AGE
mariadb.k8s.mariadb.com/mariadb-galera   True    Running   mariadb-galera-0   ReplicasFirstPrimaryLast   8m45s

NAME                   READY   STATUS    RESTARTS        AGE
pod/mariadb-galera-0   2/2     Running   0               8m19s
pod/mariadb-galera-1   2/2     Running   1 (5m35s ago)   8m19s
pod/mariadb-galera-2   2/2     Running   0               8m19s

NAME                                             STATUS   VOLUME                                     CAPACITY   ACCESS MODES   STORAGECLASS   VOLUMEATTRIBUTESCLASS   AGE
persistentvolumeclaim/galera-mariadb-galera-0    Bound    pvc-e81b313a-f521-46c2-9b85-96e44f2cdd47   100Mi      RWO            local-path     <unset>                 8m19s
persistentvolumeclaim/galera-mariadb-galera-1    Bound    pvc-d04b1c9f-66b7-490c-bec5-2804e21a0d27   100Mi      RWO            local-path     <unset>                 8m19s
persistentvolumeclaim/galera-mariadb-galera-2    Bound    pvc-057dd34a-f8d5-4fe0-891d-4c4eb78f8240   100Mi      RWO            local-path     <unset>                 8m19s
persistentvolumeclaim/storage-mariadb-galera-0   Bound    pvc-4b9f0ae9-dc8c-4ba4-86ce-7bb8c7d6ced0   5Gi        RWO            local-path     <unset>                 8m45s
persistentvolumeclaim/storage-mariadb-galera-1   Bound    pvc-6fc52329-9726-41ea-ac31-c07f63889e50   5Gi        RWO            local-path     <unset>                 8m19s
persistentvolumeclaim/storage-mariadb-galera-2   Bound    pvc-deb81a90-112d-41ef-89e2-70b757737af4   5Gi        RWO            local-path     <unset>                 8m19s

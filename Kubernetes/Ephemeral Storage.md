k exec -it nginx-storage -- bash
k exec -it nginx-storage -c busybox -- sh (-c determines which container you want)
k exec -it nginx-storage -c nginx -- bash
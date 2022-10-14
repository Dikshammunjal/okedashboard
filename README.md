# okedashboard

1.kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.3/aio/deploy/recommended.yaml
2.To create token follow below link:
https://github.com/kubernetes/dashboard/blob/master/docs/user/access-control/creating-sample-user.md
create a file named oke-admin-service-account.yaml
Create the service account and the clusterrolebinding in the cluster by entering:
$ kubectl apply -f oke-admin-service-account.yaml

3. kubectl -n kubernetes-dashboard create token admin-user
after this you should get a token

4. Run - kubectl proxy
Starting to serve on 127.0.0.1:8001
keep this running open another terminal now

dikshamunjal@dikshamunjal-mac Downloads % ssh -L 8001:127.0.0.1:8001 -i ssh-key-2022-03-16.key opc@144.24.119.32
144.24.119.32 is the node where kubectl proxy is running

5. http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/


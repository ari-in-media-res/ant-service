An Ambari Stack service package for the Apache Ant java package build tool.

To deploy, copy the entire directory into your Ambari stacks folder and restart Ambari:

```
git clone https://github.com/vedantja/ant-service
sudo mv ant-service /var/lib/ambari-server/resources/stacks/HDP/2.2/services/
sudo service ambari-server restart
```

Then you can click on 'Add Service' from the 'Actions' dropdown menu in the bottom left of the Ambari dashboard. When you've completed the install process, you will be able to use ant on all selected client nodes.

If you want to delete the Ant client from the Ambari services list (apache-ant will remain installed on selected nodes):
```
curl -u $user:$pass -i -H 'X-Requested-By: ambari' -X DELETE http://$host:8080/api/v1/clusters/$cluster/services/ANT

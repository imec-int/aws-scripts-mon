# aws-scripts-mon
amazon's aws reporting script modified to also report docker stats.

This modified version provides options to report some docker stats (right now: mem and CPU usage percentage) about running containers to cloudwatch. The mem percentage is based on the containers' memory limits; if you define container memory limits in e.g. a Docker Compose file, these limits will be used as the denominator to calculate the corresponding container's  memory usage percentage. (By default, resources are unlimited on a Linux host, hence in that case the memory usage percentage of a container will correspond to its total used RAM percentage). 
Furthermore, since there is a limit to 20 metrics in one request, there is also a cap on those. (If more metrics were requested, they are simply not sent).

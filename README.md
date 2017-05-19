# aws-scripts-mon
amazon's aws reporting script modified to also report docker stats.

This modified version provides options to report some docker stats (right now: mem and CPU usage percentage) about running containers to cloudwatch.
Furthermore, since there is a limit to 20 metrics in one request, there is also a cap on those. (If more metrics were requested, they are simply not sent).

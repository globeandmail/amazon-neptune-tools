    NAME
            neptune-export.sh export-pg-from-config - Export property graph from
            Neptune to CSV or JSON using an existing config file
    
    SYNOPSIS
            neptune-export.sh export-pg-from-config
                    [ --alb-endpoint <applicationLoadBalancerEndpoint> ]
                    [ --approx-edge-count <approxEdgeCount> ]
                    [ --approx-node-count <approxNodeCount> ]
                    [ {-b | --batch-size} <batchSize> ]
                    {-c | --config-file} <configFile> [ --clone-cluster ]
                    [ --clone-cluster-instance-type <cloneClusterInstanceType> ]
                    [ --clone-cluster-replica-count <replicaCount> ]
                    [ --cluster-id <clusterId> ]
                    [ {-cn | --concurrency} <concurrency> ]
                    {-d | --dir} <directory> [ {-e | --endpoint} <endpoint>... ]
                    [ {-el | --edge-label} <edgeLabels>... ]
                    [ --exclude-type-definitions ] [ --format <format> ]
                    [ --lb-port <loadBalancerPort> ] [ --limit <limit> ]
                    [ --log-level <log level> ]
                    [ --max-content-length <maxContentLength> ]
                    [ {-nl | --node-label} <nodeLabels>... ]
                    [ --nlb-endpoint <networkLoadBalancerEndpoint> ]
                    [ {-o | --output} <output> ] [ {-p | --port} <port> ]
                    [ {-r | --range | --range-size} <rangeSize> ]
                    [ --region <region> ] [ {-s | --scope} <scope> ]
                    [ --serializer <serializer> ] [ --skip <skip> ]
                    [ --stream-name <streamName> ] [ {-t | --tag} <tag> ]
                    [ --tokens-only <tokensOnly> ] [ --use-iam-auth ] [ --use-ssl ]
    
    OPTIONS
            --alb-endpoint <applicationLoadBalancerEndpoint>
                Application load balancer endpoint (optional: use only if
                connecting to an IAM DB enabled Neptune cluster through an
                application load balancer (ALB) – see https://github.com/aws-samples/aws-dbs-refarch-graph/tree/master/src/connecting-using-a-load-balancer#connecting-to-amazon-neptune-from-clients-outside-the-neptune-vpc-using-aws-application-load-balancer)
    
                This option may occur a maximum of 1 times
    
    
                This option is part of the group 'load-balancer' from which only
                one option may be specified
    
    
            --approx-edge-count <approxEdgeCount>
                Approximate number of edges in graph
    
                This option may occur a maximum of 1 times
    
    
            --approx-node-count <approxNodeCount>
                Approximate number of nodes in graph
    
                This option may occur a maximum of 1 times
    
    
            -b <batchSize>, --batch-size <batchSize>
                Batch size (optional, default 64). Reduce this number if your
                queries trigger CorruptedFrameExceptions.
    
                This option may occur a maximum of 1 times
    
    
            -c <configFile>, --config-file <configFile>
                Path to JSON config file (file path, or 'https' or 's3' URI)
    
                This option may occur a maximum of 1 times
    
    
            --clone-cluster
                Clone Neptune cluster
    
                This option may occur a maximum of 1 times
    
    
            --clone-cluster-instance-type <cloneClusterInstanceType>
                Instance type for cloned cluster (by default neptune-export will
                use the same instance type as the source cluster)
    
                This options value is restricted to the following set of values:
                    db.r4.large
                    db.r4.xlarge
                    db.r4.2xlarge
                    db.r4.4xlarge
                    db.r4.8xlarge
                    db.r5.large
                    db.r5.xlarge
                    db.r5.2xlarge
                    db.r5.4xlarge
                    db.r5.8xlarge
                    db.r5.12xlarge
                    db.r5.16xlarge
                    db.r5.24xlarge
                    db.m5.large
                    db.m5.xlarge
                    db.m5.2xlarge
                    db.m5.3xlarge
                    db.m5.8xlarge
                    db.m5.12xlarge
                    db.m5.16xlarge
                    db.m5.24xlarge
                    db.t3.medium
    
                This option may occur a maximum of 1 times
    
    
            --clone-cluster-replica-count <replicaCount>
                Number of read replicas to add to the cloned cluster (default, 0)
    
                This option may occur a maximum of 1 times
    
    
                This options value must fall in the following range: 0 <= value <= 15
    
    
            --cluster-id <clusterId>
                ID of an Amazon Neptune cluster. If you specify a cluster ID,
                neptune-export will use all of the instance endpoints in the
                cluster in addition to any endpoints you have specified using the
                -e and --endpoint options.
    
                This option may occur a maximum of 1 times
    
    
            -cn <concurrency>, --concurrency <concurrency>
                Concurrency (optional)
    
                This option may occur a maximum of 1 times
    
    
            -d <directory>, --dir <directory>
                Root directory for output
    
                This option may occur a maximum of 1 times
    
    
                This options value must be a path to a directory. The provided path
                must be readable and writable.
    
    
            -e <endpoint>, --endpoint <endpoint>
                Neptune endpoint(s) – supply multiple instance endpoints if you
                want to load balance requests across a cluster
    
            -el <edgeLabels>, --edge-label <edgeLabels>
                Labels of edges to be included in config (optional, default all
                labels)
    
            --exclude-type-definitions
                Exclude type definitions from column headers (optional, default
                'false')
    
                This option may occur a maximum of 1 times
    
    
            --format <format>
                Output format (optional, default 'csv')
    
                This options value is restricted to the following set of values:
                    csv
                    csvNoHeaders
                    json
                    neptuneStreamsJson
    
                This option may occur a maximum of 1 times
    
    
            --lb-port <loadBalancerPort>
                Load balancer port (optional, default 80)
    
                This option may occur a maximum of 1 times
    
    
                This options value represents a port and must fall in one of the
                following port ranges: 1-1023, 1024-49151
    
    
            --limit <limit>
                Maximum number of items to export (optional)
    
                This option may occur a maximum of 1 times
    
    
            --log-level <log level>
                Log level (optional, default 'error')
    
                This options value is restricted to the following set of values:
                    trace
                    debug
                    info
                    warn
                    error
    
                This option may occur a maximum of 1 times
    
    
            --max-content-length <maxContentLength>
                Max content length (optional, default 65536)
    
                This option may occur a maximum of 1 times
    
    
            -nl <nodeLabels>, --node-label <nodeLabels>
                Labels of nodes to be included in config (optional, default all
                labels)
    
            --nlb-endpoint <networkLoadBalancerEndpoint>
                Network load balancer endpoint (optional: use only if connecting to
                an IAM DB enabled Neptune cluster through a network load balancer
                (NLB) – see https://github.com/aws-samples/aws-dbs-refarch-graph/tree/master/src/connecting-using-a-load-balancer#connecting-to-amazon-neptune-from-clients-outside-the-neptune-vpc-using-aws-network-load-balancer)
    
                This option may occur a maximum of 1 times
    
    
                This option is part of the group 'load-balancer' from which only
                one option may be specified
    
    
            -o <output>, --output <output>
                Output target (optional, default 'file')
    
                This options value is restricted to the following set of values:
                    files
                    stdout
                    stream
    
                This option may occur a maximum of 1 times
    
    
            -p <port>, --port <port>
                Neptune port (optional, default 8182)
    
                This option may occur a maximum of 1 times
    
    
                This options value represents a port and must fall in one of the
                following port ranges: 1-1023, 1024-49151
    
    
            -r <rangeSize>, --range <rangeSize>, --range-size <rangeSize>
                Number of items to fetch per request (optional)
    
                This option may occur a maximum of 1 times
    
    
            --region <region>
                AWS Region in which your Amazon Kinesis Data Stream is located
    
                This option may occur a maximum of 1 times
    
    
            -s <scope>, --scope <scope>
                Scope (optional, default 'all')
    
                This options value is restricted to the following set of values:
                    all
                    nodes
                    edges
    
                This option may occur a maximum of 1 times
    
    
            --serializer <serializer>
                Message serializer – either 'GRAPHBINARY_V1D0' or 'GRYO_V3D0'
                (optional, default 'GRAPHBINARY_V1D0')
    
                This options value is restricted to the following set of values:
                    GRAPHBINARY_V1D0
                    GRYO_V3D0
    
                This option may occur a maximum of 1 times
    
    
            --skip <skip>
                Number of items to skip (optional)
    
                This option may occur a maximum of 1 times
    
    
            --stream-name <streamName>
                Name of an Amazon Kinesis Data Stream
    
                This option may occur a maximum of 1 times
    
    
            -t <tag>, --tag <tag>
                Directory prefix (optional)
    
                This option may occur a maximum of 1 times
    
    
            --tokens-only <tokensOnly>
                Export tokens (~id, ~label) only (optional, default 'off')
    
                This options value is restricted to the following set of values:
                    off
                    nodes
                    edges
                    both
    
                This option may occur a maximum of 1 times
    
    
            --use-iam-auth
                Use IAM database authentication to authenticate to Neptune
                (remember to set SERVICE_REGION environment variable)
    
                This option may occur a maximum of 1 times
    
    
            --use-ssl
                Enables connectivity over SSL
    
                This option may occur a maximum of 1 times
    
    
    EXAMPLES
            bin/neptune-export.sh export-pg-from-config -e neptunedbcluster-xxxxxxxxxxxx.cluster-yyyyyyyyyyyy.us-east-1.neptune.amazonaws.com -c /home/ec2-user/config.json -d /home/ec2-user/output
    
                Export data using the metadata config in /home/ec2-user/config.json
    
            bin/neptune-export.sh export-pg-from-config -e neptunedbcluster-xxxxxxxxxxxx.cluster-yyyyyyyyyyyy.us-east-1.neptune.amazonaws.com -c /home/ec2-user/config.json -d /home/ec2-user/output --format json
    
                Export data as JSON using the metadata config in
                /home/ec2-user/config.json
    

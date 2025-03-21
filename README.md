
Working config files specific to nextflow pipelines with parameters for CHPC clusters and partitions. 

Config file naming structure: executor(slurm or local)-cluster_NextFlowPipelineName.config 

When cluster is "all", config file is expected to contain profiles within it to allow submission to each cluster.

Using profiles, allows the main nextflow job to be submitted with one account/partition combo (for example small 2 procesor job on round-np that has longer time limit) and the nextflow spawned jobs to be submitted with a different partition/account combo - IF accessible (i.e. on the same cluster).

Cluster-specific profiles can be copied and modified to avoid requesting resources not available on a cluster, or could be modified in the profiles of all. 

Examples: 
1. "**slurm-all_mag.config**": For nfcore-mag pipeline, contains profiles for all clusters/partition/account combos accessible to us. 

2. "**slurm-lp_mag.config**": For nfcore-mag pipeline, but some processes have memory requirements lower for quicker qos on lonepeak. 

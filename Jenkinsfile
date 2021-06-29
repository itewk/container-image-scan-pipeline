// Load the Ploigos Jenkins Library
library identifier: 'ploigos-jenkins-library@main',
retriever: modernSCM([
    $class: 'GitSCMSource',
    remote: 'https://github.com/ploigos/ploigos-jenkins-library.git'
])

// run the pipeline
ploigosWorkflowExistingContainerImageScan(
    stepRunnerConfigDir: 'ploigos-step-runner-config/',

    pgpKeysSecretName: 'pgp-keys-ploigos-workflow-ref-quarkus-mvn-jenkins-min-fruit',
    workflowServiceAccountName: 'ploigos-workflow-ref-quarkus-mvn-jenkins-min-fruit',

    workflowWorkerImageDefault: 'ploigos/ploigos-ci-agent-jenkins:edge',
    workflowWorkerImageContainerOperations: 'ploigos/ploigos-tool-containers:edge',
    workflowWorkerImageContainerImageStaticComplianceScan: 'ploigos/ploigos-tool-openscap:edge',
    workflowWorkerImageContainerImageStaticVulnerabilityScan: 'ploigos/ploigos-tool-openscap:edge',
    workflowWorkersImagePullPolicy: 'Always',

    registryURL: params.registryRUL,
    imageOrg: params.imageOrg,
    imageName: params.imageName,
    imageTag: params.imageTag 
)

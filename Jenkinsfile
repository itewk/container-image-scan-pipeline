// Load the Ploigos Jenkins Library
library identifier: 'ploigos-jenkins-library@v0.20.0',
retriever: modernSCM([
    $class: 'GitSCMSource',
    remote: 'https://github.com/ploigos/ploigos-jenkins-library.git'
])

// run the pipeline
ploigosWorkflowExistingContainerImageScan(
    stepRunnerConfigDir: 'ploigos-step-runner-config/',

    pgpKeysSecretName: 'pgp-keys-ploigos-workflow-ref-quarkus-mvn-jenkins-min-fruit',
    workflowServiceAccountName: 'ploigos-workflow-ref-quarkus-mvn-jenkins-min-fruit',

    workflowWorkerImageDefault: 'ploigos/ploigos-base:v0.20.0',
    workflowWorkerImageContainerOperations: 'ploigos/ploigos-tool-containers:v0.20.0',
    workflowWorkerImageContainerImageStaticComplianceScan: 'ploigos/ploigos-tool-openscap:v0.20.0',
    workflowWorkerImageContainerImageStaticVulnerabilityScan: 'ploigos/ploigos-tool-openscap:v0.20.0',

    registryURL: params.registryRUL,
    imageOrg: params.imageOrg,
    imageName: params.imageName,
    imageTag: params.imageTag
)

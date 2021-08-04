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

    workflowWorkerImageDefault: 'ploigos/ploigos-base:edge',
    workflowWorkerImageContainerOperations: 'ploigos/ploigos-tool-containers:edge',
    workflowWorkerImageContainerImageStaticComplianceScan: 'ploigos/ploigos-tool-openscap:edge',
    workflowWorkerImageContainerImageStaticVulnerabilityScan: 'ploigos/ploigos-tool-openscap:edge',
    workflowWorkersImagePullPolicy: 'Always',

    stepRunnerUpdateLibrary: true,
    stepRunnerLibSourceUrl: 'git+https://github.com/ploigos/ploigos-step-runner.git@main',

    registryURL: params.registryRUL,
    imageOrg: params.imageOrg,
    imageName: params.imageName,
    imageTag: params.imageTag
)

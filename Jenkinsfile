// Load the Ploigos Jenkins Library
library identifier: 'ploigos-jenkins-library@feature/use-local-container-storage-refactor',
retriever: modernSCM([
    $class: 'GitSCMSource',
    remote: 'https://github.com/itewk/ploigos-jenkins-library.git'
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
    stepRunnerLibSourceUrl: 'git+https://github.com/itewk/ploigos-step-runner.git@feature/continue-sub-steps-on-failure-option',

    registryURL: params.registryRUL,
    imageOrg: params.imageOrg,
    imageName: params.imageName,
    imageTag: params.imageTag
)

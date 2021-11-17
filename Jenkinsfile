// Load the Ploigos Jenkins Library
library identifier: 'ploigos-jenkins-library@feature/params-refactor',
retriever: modernSCM([
    $class: 'GitSCMSource',
    remote: 'https://github.com/itewk/ploigos-jenkins-library.git'
])

// run the pipeline
oscapExistingContainerImageScanPloigosWorkflow(
    stepRunnerConfigDir: 'ploigos-step-runner-config/',

    pgpKeysSecretName: 'pgp-keys-ploigos-workflow-ref-quarkus-mvn-jenkins-min-fruit',
    workflowServiceAccountName: 'ploigos-workflow-ref-quarkus-mvn-jenkins-min-fruit',

    registryURL: params.registryRUL,
    imageOrg: params.imageOrg,
    imageName: params.imageName,
    imageTag: params.imageTag
)
